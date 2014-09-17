## Introduction

In this lab you will do a very basic hello world example.  In order to do this lab you will need golang installed (version 1.2 was used to create the labs).  This lab is designed simple to test your environment.  You are welcome to use an editor, however these labs are setup from the commandline perspective.

## Steps

#### 1: make a project dir

`mkdir hello`

#### 2: create a project structure

bin, src, pkg are the common base folders in the project directory.  At a minimum you will need to create the `src` folder

#### 3: set GOPATH

change directory to the project directory and set the GOPATH to the current dir
export GOPATH=`pwd`

#### 4: create a package

`mkdir -p src/acme.com/hello`

#### 5: edit hello.go

`vi src/acme.com/hello/hello.go`

```
func main() {
	
	fmt.Printf("Hello, world.\n")

```

#### 6: install the package

`go install acme.com/hello`

#### 7: execute the program

`./bin/hello`
