# Conditional Statements in R — Line-by-Line Explained with Comments

## 1. Basic `if` Statement

```r
x <- 10               # assign the value 10 to x

if (x > 5) {          # check if x is greater than 5
  print("x is greater than 5")   # this runs only if condition is TRUE
}                      # end of if block
```

---

## 2. `if ... else`

```r
x <- 3                # assign 3 to x

if (x > 5) {          # condition: is x greater than 5?
  print("x > 5")      # runs if TRUE
} else {              # runs when the if condition is FALSE
  print("x <= 5")     # prints this because x = 3
}                      # end of if-else
```

---

## 3. `else if` Chain

```r
score <- 85                 # assign value 85 to score

if (score >= 90) {          # first condition
  print("A")
} else if (score >= 80) {   # second condition checked if first is FALSE
  print("B")                # this runs because 85 >= 80
} else if (score >= 70) {   # skipped because previous condition was TRUE
  print("C")
} else {                    # runs only if all above are FALSE
  print("D or F")
}                            # end of chain
```

---

## 4. Vectorized `ifelse()`

```r
x <- 1:10                        # create vector from 1 to 10

result <- ifelse(x %% 2 == 0,    # test: is number even?
                 "even",         # value returned when TRUE
                 "odd")          # value returned when FALSE

result                           # show the resulting vector
```

---

## 5. Logical Operators

### Vectorized AND / OR

```r
x > 5 & x < 12      # checks each element: TRUE only if both conditions TRUE
```

### Single-value AND / OR

```r
if (x > 5 && y < 10) {        # && checks only first element of logical vectors
  print("Both conditions are TRUE")
}
```

---

## 6. `switch()` Statement

```r
option <- "blue"              # assign a color string to option

result <- switch(option,      # switch checks which case matches 'option'
  red = "You chose red",      # case 1
  blue = "You chose blue",    # case 2 (this one runs)
  green = "You chose green",  # case 3
  "Unknown color"             # default if no match
)

print(result)                 # print the returned value
```
