iota is a little confusing.

```go
const (
  a = iota
  b = iota
  c = iota
)
```
results in 1, 2, 3

```go
const (
  a = iota
  b
  c
)
```
also results in 1, 2, 3

```go
const (
  a = iota + 50
  b
  c
)
```
results in 50, 51, 52

```go
const (
  a = iota + 50
  b = iota
  c
)
```
results in 50, 1, 2

```go
const (
  a = iota + 50
  b = iota + 50
  c = iota
)
```
results in 50, 51, 2

```go
const (
  a = iota + 50
  b = iota + 50
  c = iota + 50
)
```
results in 50, 51, 52

How confusing!
