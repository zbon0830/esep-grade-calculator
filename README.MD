# ESEP Grade Calculator

Small Go library that figures out a final letter grade. You add assignment, exam, and essay grades, it averages each type, weights them, and gives you a letter.

Weights: assignments 50%, exams 35%, essays 15%.

Letter grades: A is 90+, B is 80+, C is 70+, D is 60+, and anything under 60 is an F.  C or better is considered passing.

## Setup

You need Go 1.24 or newer (https://go.dev/dl/). No other dependencies.

The code lives in the `grade-calculator/` folder

## Example

```go
gc := NewGradeCalculator()
gc.AddGrade("open source assignment", 95, Assignment)
gc.AddGrade("exam 1", 88, Exam)
gc.AddGrade("essay on ai ethics", 91, Essay)

gc.GetFinalGrade() // "A"
```

## Running tests

```
cd grade-calculator
go test -v ./...
```

For coverage:

```
go test -cover ./...
```

To see which lines are covered in your browser:

```
go test -coverprofile=coverage.out ./...
go tool cover -html=coverage.out
```
