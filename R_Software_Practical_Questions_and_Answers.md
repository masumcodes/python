# R SOFTWARE PRACTICAL – QUESTIONS AND ANSWERS

## Question 1. Demonstration of R Software Using Different Commands

**Aim:** To demonstrate R software using different commands with the help of the built-in `longley` dataset.

**Program:**

```r
# Load the longley dataset
data("longley")

# Display the dataset
force(longley)

# Display first six records
head(longley)

# Display last six records
tail(longley)

# Display column names
names(longley)

# Display attributes
attributes(longley)

# Display row names
row.names(longley)

# Display class of dataset
class(longley)

# Display structure of dataset
str(longley)

# Display levels
levels(longley)
```

**Conclusion:** Thus, we successfully demonstrated R software using different commands such as `data()`, `force()`, `head()`, `tail()`, `names()`, `attributes()`, `row.names()`, `class()`, `str()` and `levels()`.

---

## Question 2. Demonstration of Data Exploration of Individual and Multiple Variables Using R Objects

**Aim:** To demonstrate data exploration of individual and multiple variables using R objects.

**Program:**

### 1. Display Levels

```r
# Display levels of longley dataset
levels(longley)
```

**Output:**

```text
NULL
```

### 2. Creating a String

```r
# Create a string variable
mystring <- "Hello World"

# Display string
print(mystring)
```

**Output:**

```text
[1] "Hello World"
```

### 3. Creating a Vector

```r
# Create a character vector
Apple <- c("red", "green", "yellow")

# Display vector
print(Apple)

# Display class
print(class(Apple))
```

**Output:**

```text
[1] "red" "green" "yellow"
[1] "character"
```

### 4. Creating a List

```r
# Create a list
list1 <- list(c(2, 5, 3), 21.3, sin)

# Display list
print(list1)
```

**Output:**

```text
[[1]]
[1] 2 5 3

[[2]]
[1] 21.3

[[3]]
function (x) .Primitive("sin")
```

### 5. Creating a Factor

```r
# Create a color vector
Apple_colors <- c("green", "green", "yellow",
                  "red", "red", "red", "green")

# Convert vector into factor
factor_Apple <- factor(Apple_colors)

# Display factor
print(factor_Apple)
```

**Output:**

```text
[1] green green yellow red red red green
Levels: green red yellow
```

### 6. Display Number of Levels

```r
# Display factor levels
levels(factor_Apple)

# Display number of levels
nlevels(factor_Apple)
```

**Output:**

```text
[1] "green" "red" "yellow"
[1] 3
```

### 7. Creating a Bar Plot

```r
# Create variables
x <- c("A", "B", "C", "D")
y <- c(2, 4, 6, 8)

# Create bar plot
barplot(y, names.arg = x, density = 10)

# Another bar plot
barplot(y, names.arg = x, density = 6)
```

### 8. Exploring Dataset

```r
# Load the cars dataset
data_cars <- mtcars

# Find maximum value
max(data_cars$hp)

# Find minimum value
min(data_cars$hp)

# Find mean value
mean(data_cars$wt)

# Find median value
median(data_cars$wt)
```

**Conclusion:** Thus, we successfully demonstrated data exploration of individual and multiple variables using R objects such as strings, vectors, lists, factors and datasets. We also used statistical functions like `max()`, `min()`, `mean()` and `median()`.

---

## Question 3. Perform Arithmetic and Relational Operations Using R

**Aim:** To perform arithmetic and relational operations using R software.

**Program:**

### 1. Arithmetic Operations

```r
# Addition
3 + 5
# Output: 8

# Subtraction
8 - 3
# Output: 5

# Multiplication
7 * 5
# Output: 35

# Division
1 / 2
# Output: 0.5

# Power
4 ^ 4
# Output: 256

# Modulus
5 %% 3
# Output: 2

# Integer division
5 %/% 2
# Output: 2
```

### 2. Arithmetic Operations Using Vectors

```r
# Create two vectors
x <- c(1, 7, 3)
y <- c(9, 4, 5)

# Addition
x + y
# Output: 10 11 8

# Subtraction
x - y
# Output: -8 3 -2

# Multiplication
x * y
# Output: 9 28 15

# Division
x / 2
# Output: 0.5 3.5 1.5

# Power
x ^ y
# Output: 1 2401 243

# Modulus
x %% y
# Output: 1 3 3

# Integer division
x %/% y
# Output: 0 1 0
```

### 3. Relational Operations

```r
# Greater than
3 > 5
# Output: FALSE

# Less than
3 < 5
# Output: TRUE

# Less than or equal to
3 <= 5
# Output: TRUE

# Greater than or equal to
5 >= 3
# Output: TRUE

# Equal to
3 == 5
# Output: FALSE

# Not equal to
3 != 5
# Output: TRUE
```

### 4. Relational Operations Using Vectors

```r
# Create two vectors
x <- c(12, 4, 14)
y <- c(3, 4, 15)

# Greater than or equal to
x >= y
# Output: TRUE TRUE FALSE

# Less than or equal to
x <= y
# Output: FALSE TRUE TRUE

# Equal to
x == y
# Output: FALSE TRUE FALSE

# Not equal to
x != y
# Output: TRUE FALSE TRUE
```

**Conclusion:** Thus, we successfully performed arithmetic and relational operations using R. We used operators such as addition, subtraction, multiplication, division, power, modulus, greater than, less than, equal to and not equal to.

---

## Question 4. Perform Plotting and Statistical Operations Using R Objects

**Aim:** To perform plotting and statistical operations using R software.

**Program:**

### 1. Plotting of Multiple Points

```r
# Create x and y variables
x <- c(1, 2, 3, 4, 5)
y <- c(3, 7, 8, 9, 12)

# Plot multiple points
plot(x, y)
```

### 2. Sequence of Points with Labels

```r
# Plot sequence of points with labels
plot(1:10,
     main = "My Graph",
     xlab = "The X-axis",
     ylab = "The Y-axis")
```

### 3. Multiple Lines

```r
# Create first line
line1 <- c(1, 2, 3, 4, 5, 10)

# Create second line
line2 <- c(2, 5, 7, 8, 9, 10)

# Plot first line
plot(line1, type = "l", col = "blue")

# Add second line
lines(line2, col = "red")
```

### 4. Scatter Plot

```r
# Create variables
x <- c(5, 7, 8, 10, 12, 15, 18, 20, 18, 22)
y <- c(25, 30, 32, 35, 40, 45, 50, 60, 29, 40)

# Create scatter plot
plot(x, y)
```

### 5. Compare Plots

```r
# Create comparison plot
plot(x, y,
     main = "Observation of Cars",
     xlab = "Car Age",
     ylab = "Car Speed",
     col = "red",
     cex = 2)
```

### 6. Pie Chart

```r
# Create values
x <- c(10, 20, 30, 40)

# Create labels
mylabel <- c("Apples", "Banana", "Cherries", "Dates")

# Create colors
colors <- c("blue", "yellow", "green", "black")

# Create pie chart
pie(x, labels = mylabel,
    main = "Pie Chart",
    col = colors)
```

### 7. Bar Charts

```r
# Create categories
x <- c("A", "B", "C", "D")

# Create values
y <- c(2, 4, 6, 8)

# Create bar plot
barplot(y, names.arg = x, density = 10)

# Another bar plot
barplot(y, names.arg = x, density = 6)
```

### 8. Statistical Operations Using Dataset

```r
# Load the built-in cars dataset
data_cars <- mtcars

# Find maximum horsepower
max(data_cars$hp)

# Find minimum horsepower
min(data_cars$hp)

# Find mean of weight
mean(data_cars$wt)

# Find median of weight
median(data_cars$wt)
```

### 9. Sum, Standard Deviation and Variance

```r
# Create a numeric vector
x <- c(10, 20, 30, 40, 50)

# Calculate sum
sum(x)

# Calculate standard deviation
sd(x)

# Calculate variance
var(x)
```

### 10. Summary of Dataset

```r
# Display statistical summary
summary(data_cars)
```

### 11. Frequency Distribution

```r
# Create a vector
x <- c(10, 20, 10, 30, 20, 10, 40)

# Find frequency
table(x)
```

**Conclusion:** Thus, we successfully performed plotting and statistical operations using R objects. We created different graphs such as line plots, scatter plots, pie charts and bar charts. We also performed statistical operations using `max()`, `min()`, `mean()`, `median()`, `sum()`, `sd()`, `var()` and `summary()`.

---

**End of R Software Practicals (Questions 1–4).**
