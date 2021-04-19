
# GoFarsi
[![Build Status](https://travis-ci.org/01walid/gofarsi.svg)](https://travis-ci.org/faridgh1991/gofarsi)
[![GoDoc](https://godoc.org/github.com/faridgh1991/gofarsi?status.svg)](https://godoc.org/github.com/faridgh1991/gofarsi)

A Go Lang package for dealing with Farsi text.

This is an initial work on a set of Go functions developed to enhance Farsi web applications.
It all started when I wanted to develop a self-hosted no-dependency and standalone Farsi Captcha in Go (for fun, as I'm discovering Go), and as expected, the Farsi text wasn't rendered as it should:

![Before processing](https://res.cloudinary.com/walid/image/upload/v1429186546/before_pcyoha.png)

So I started playing with Glyphs, unicode, and the special Farsi rules for joining letters. After a bit of work, I got this:

![Before processing](https://res.cloudinary.com/walid/image/upload/v1429186546/after_cmkukt.png)

shouldn't this be a separated package, along with other functionalities? I guess it should!

## Current functionalities
- Glyph representation of the given Farsi texts for images/pdf & etc generation.
- Strip Tashkeel (Arabic Vowels).
- SmartLengh: return the length of the given Farsi String without considering Tashkeel (Arabic Vowels).
- Strip Tatweel
- rune-wise (UTF-8) reverse of the Farsi text, leaving out the Latin one.

## Usage

### Installing
```bash
go get github.com/faridgh1991/gofarsi
```
##### Example Usage
```go
package main

import (
    "fmt"
    "github.com/faridgh1991/gofarsi"
)

func main() {
    fmt.Println(gofarsi.RemoveTashkeel("نًصٌ عَربيُّ"))
    fmt.Println(gofarsi.ToGlyph("تجربة النص العربي"))
}

```
## Documentation
Package docs available on [gopkgdoc](https://godoc.org/github.com/faridgh1991/gofarsi).

## Contributing
Contributions are greatly appreciated. Please fork this repository, make your changes, and open a pull request. More test cases and considerations might be needed, you can run tests using `go test` for the existing functionalities.

This a [SemVer](http://semver.org/)sioned package.
## License
MIT License.
