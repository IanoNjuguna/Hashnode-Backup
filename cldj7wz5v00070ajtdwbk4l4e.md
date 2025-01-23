---
title: "BrokenImport: could not import rsc.io/quote error in GoLang"
seoTitle: "BrokenImport: could not import rsc.io/quote"
seoDescription: "(no required module provides package "rsc.io/quote")"
datePublished: Mon Jan 30 2023 19:42:49 GMT+0000 (Coordinated Universal Time)
cuid: cldj7wz5v00070ajtdwbk4l4e
slug: could-not-import-rscioquote
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1675108619406/3bcca7ba-c396-4efe-a720-20d767d1faa5.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1675105006936/9cd173e7-3e40-4209-8520-0d4e686d1866.png
tags: go, call-code-in-an-external-package-in-go

---

## Synopsis

I encountered this error while [calling the code in an Golang package](https://go.dev/doc/tutorial/getting-started) in the following code:

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

After running the `go run .` command, I got the following output:

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

For Golang source code to compile, the `go.mod` file <mark>MUST</mark> exist. This means that you have to initialize your module using the `go mod init hello` command and the output for doing that is:

```bash
go: creating new go.mod: module hello
go: to add module requirements and sums:
        go mod tidy
```

After initializing the module, run the `go mod tidy` command.

Alternatively, you can run the `go mod tidy` command as stipulated in the documentation.

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

## Reference

1. [https://stackoverflow.com/a/64442305/18533523](https://stackoverflow.com/a/64442305/18533523)
    
2. [https://go.dev/doc/tutorial/getting-started](https://go.dev/doc/tutorial/getting-started)
    
3. [https://go.dev/ref/mod#authenticating](https://go.dev/ref/mod#authenticating)
    
4. [https://golangbyexample.com/go-mod-tidy/](https://golangbyexample.com/go-mod-tidy/)