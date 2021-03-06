![goreporter](./logo.png)

# goreporter

[![Build Status](https://travis-ci.org/wgliang/goreporter.svg?branch=master)](https://travis-ci.org/wgliang/goreporter)
[![GoDoc](https://godoc.org/github.com/wgliang/goreporter?status.svg)](https://godoc.org/github.com/wgliang/goreporter)
[![License](https://img.shields.io/badge/LICENSE-Apache2.0-ff69b4.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)

A Golang tool that does static analysis, unit testing, code review and generate code quality report. This is a tool that concurrently runs a whole bunch of those linters and normalises their output to a report:

<!-- MarkdownTOC -->

- [Supported linters](#supported-linters)
- [Supported template](#supported-template)
- [Installing](#installing)
- [Credits](#credits)
- [Quickstart](#quickstart)
- [Example](#example)
	- [Summary](#summary)
	- [UnitTest](#unittest)
	- [SimpleCode](#simplecode)
	- [DeadCode & CopyCode](#deadcodeandcopycode)
- [Report-example](#report-example)
- [Credits](#credits)

<!-- /MarkdownTOC -->

## Supported linters

- [unittest](https://github.com/wgliang/goreporter/tree/master/linters/unittest) - Golang unit test status.
- [deadcode](https://github.com/tsenart/deadcode) - Finds unused code.
- [gocyclo](https://github.com/alecthomas/gocyclo) - Computes the cyclomatic complexity of functions.
- [varcheck](https://github.com/opennota/check) - Find unused global variables and constants.
- [structcheck](https://github.com/opennota/check) - Find unused struct fields.
- [aligncheck](https://github.com/opennota/check) - Warn about un-optimally aligned structures.
- [errcheck](https://github.com/kisielk/errcheck) - Check that error return values are used.
- [copycode(dupl)](https://github.com/mibk/dupl) - Reports potentially duplicated code.
- [gosimple](https://github.com/dominikh/go-tools/tree/master/cmd/gosimple) - Report simplifications in code.
- [staticcheck](https://github.com/dominikh/go-tools/tree/master/cmd/staticcheck) - Statically detect bugs, both obvious and subtle ones.
- [godepgraph](https://github.com/kisielk/godepgraph) - Godepgraph is a program for generating a dependency graph of Go packages.
- [misspell](https://github.com/client9/misspell) - Correct commonly misspelled English words... quickly.

## Supported template

- html template file which can be loaded via `-t <file>`.

## Installing

There are two options for installing goreporter.

- 1. Install a stable version, eg. `go get -u github.com/wgliang/goreporter/tree/version-1.0.0`.
   I will generally only tag a new stable version when it has passed the Travis regression tests. 
     The downside is that the binary will be called `goreporter.version-1.0.0`.

- 2. Install from HEAD with: `go get -u github.com/wgliang/goreporter`.
   This has the downside that changes to goreporter may break.

## Quickstart

Install goreporter (see above).

Run it:

```
$ goreporter -p [projtectRelativelyPath] -d [reportPath] -e [exceptPackagesName] -r [json/html]  {-t templatePathIfHtml}
```

## Example

```
$ goreporter -p ../goreporter -d ../goreporter -t ./templates/template.html
```
you can see result detail:[Example-Report](http://fiisio.me/pages/goreporter-report.html)

### Summary
![summary](./doc/summary.jpeg)

### UnitTest
![unittest](./doc/unittest.jpeg)

### SimpleCode
![simplecode](./doc/simplecode.jpeg)

### DeadCode & CopyCode
![deadcodeandcopycode](./doc/deadcodeandcopycode.jpeg)

## Report-example

[Example-Report](http://fiisio.me/pages/goreporter-report.html)

## Credits

Templates is designed by liufeifei

Logo is desigend by [xuri](https://github.com/Luxurioust)
