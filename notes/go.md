# Go Properties and Best Practices

- To write good Go code, it's important to have a solid understanding of its properties and best practices
- Further, to write Go well in a collaborative setting, you should understand the conventions that the Go community has adopted over the years
- To make most of how powerful Go can be, you can take a look under the hood to understand some of the mechanics that the creators of Go have put to use
- Lastly, Go is related to other mainstream programming languages and might have borrowed some concepts of them, however, in Go things are done a bit differently – take some time to familiarize yourself with how to use design patterns the Go way

## Conventions

### Formatting

- Everyone can adapt to different formatting styles
- However, it's best if everyone adheres to the same style as it results in less effort and time being spent on the issue
- In Go, the machine takes care of most of the formatting
- `gofmt` (also available as `go fmt`) [the difference being that `gofmt` operates on source file level and `go fmt` works at the package level) formats Go code in a standard style of indentation and vertical alignment, retaining and if necessary reformatting comments
- As an example, given:

```go
type T struct {
    name string // name of the object
    value int // its value
}
```

-  `gofmt` will output:

```go
type T struct {
    name    string // name of the object
    value   int    // its value
}
```

-  For the curious, here's a brief set of formatting rules:
  - **Indentation:** Use tabs for indentation and `gofmt` puts them by default. Use spaces only if you must.
  - **Line length:** Go has no line length limit. If a line feels too long, wrap it and indent with an extra tab.
  - **Parentheses:** Control structures (if, for, switch) in Go do not have parentheses in their syntax. Also, the operator precedence hierarchy is shorter and clearer, so `x<<8 + y<<16` means what the spacing implies, unlike in the other languages.

### Comments

- Go provides C-style `/* block comments */` and C++-style `// line comments`
- Line comments are the norm
- Block comments appear mostly as package comments, but are useful within an expression or to disable large swaths of code
- Comments that appear before top-level declarations, with no intervening newlines, are considered to document the declaration itself
- These “doc comments” are the primary documentation for a given Go package or command
- TODO: Review "[Go Doc Comments](https://go.dev/doc/comment)"

### Naming

- Beyond the importance of good naming as in any other programming language, names in Go have a semantic effect
- The visibility of a name outside a package is determined by whether its first character is upper case

####
####
####
####

## Credits

- The Go Authors, "Effective Go," 2009, [Official Go Documentation](https://go.dev/doc/). [Online]. Available: [https://go.dev/doc/effective_go](https://go.dev/doc/effective_go). [Accessed: 28 Jun. 2024].
- D. Shuralyov, "Idiomatic Go," 28 Sep. 2016, [dimitri.shuralyov.com](https://dmitri.shuralyov.com/). [Online]. Available: [https://dmitri.shuralyov.com/idiomatic-go](https://dmitri.shuralyov.com/idiomatic-go). [Accessed: 28 Jun. 2024].
- 
