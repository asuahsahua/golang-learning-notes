iota is a little confusing.

```go
const (
  a = iota
  b = iota
  c = iota
)
```
results in 0, 1, 2

```go
const (
  a = iota
  b
  c
)
```
also results in 0, 1, 2

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

```go
const (
  a = 2
  b = iota
  c
)
```
results in 2, 1, 2

```go
const (
  a = 2
  b
  c
)
```
results in 2, 2, 2

This is a bit confusing, hm!

Thinking about it, this actually makes perfect sense. Each undefined const in a block inherits the previous value, but iota (greek letter for i) is the [b]i[/b]ndex of the current const. iota is inherited, so it increments like the above. Okay.
