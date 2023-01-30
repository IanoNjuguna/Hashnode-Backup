# BrokenImport: could not import rsc.io/quote error in GoLang

## Synopsis Of The Error

I encountered this error while learning how to [call the code in an external package](https://go.dev/doc/tutorial/getting-started).  
While following the tutorial, I ran the following code:

```go
package main

import (
    "fmt"
    "rsc.io/quote"
)

func main() {
    fmt.Println(quote.Go())
}
```

I got the following unexpected output after running the `go run .` command:

```bash
package rsc.io/quote
	imports rsc.io/quote: import cycle not allowed
```

Upon running the `go build` command, I got the following output:

```bash
package command-line-arguments
	imports rsc.io/quote
	imports rsc.io/quote: import cycle not allowed
```

## How I Fixed The Error

First and foremost, no error message is a personal attack on your abilities as a developer.

Upon doing my research I learned that for the source code to compile, the `go.mod` file <mark>MUST</mark> exist. This means that you have to initialize your module using the `go mod init hello` command and the output for doing that is:

```bash
go: creating new go.mod: module hello
go: to add module requirements and sums:
        go mod tidy
```

After initializing the module, run the `go mod tidy` command.

### What Does The `go mod tidy` Command Do?

The `go mod tidy` command matches the `go.mod` file with the dependencies required in the source files. To do this:

* It downloads all the dependencies that are required in your source files and updates the `go.mod` file with the dependencies.
    

* It removes all dependencies from the `go.mod` file which are not required in the source files.
    

In this case, it downloads the `rsc.io/quote` package and a `go.sum` file for [authenticating the module](https://go.dev/ref/mod#authenticating).

## Conclusion

Once you run your code using the `go build` command, you'll get the expected output, i.e:

```plaintext
Don't communicate by sharing memory, share memory by communicating.
```

##   
Reference

1. [https://stackoverflow.com/a/64442305/18533523](https://stackoverflow.com/a/64442305/18533523)
    
2. [https://go.dev/doc/tutorial/getting-started](https://go.dev/doc/tutorial/getting-started)
    
3. [https://go.dev/ref/mod#authenticating](https://go.dev/ref/mod#authenticating)