# PDF Reader

A super lightweight, simple Go library which enables reading PDF files.

This repository is the maintained fork of:
- https://github.com/joehewett/pdf, which is a fork of
- https://github.com/ledongthuc/pdf, which was a fork of
- https://github.com/rsc/pdf


## Install:

`go get -u github.com/joehewett/pdf`


## Read plain text

```golang
package main

import (
	"bytes"
	"fmt"

	"github.com/joehewett/pdf"
)

func main() {
	r, err := pdf.Open("test.pdf")
	if err != nil {
		panic(err)
	}

	var buf bytes.Buffer
	b, err := r.GetPlainText()
	if err != nil {
		panic(err)
	}

	buf.ReadFrom(b)

	fmt.Println(buf.String())

	return
}
```
