## Introduction

Starting with lab 1 and using information we learned in the data structures in functions section, this lab we will create a function in a `pkg` and will create a test for it.

This lab assumes you have a solution for lab 1 as a starting point.

## Steps

#### 1: make a package for string

`mkdir src/acme.com/string`

#### 2: create a string.go file

`vi src/acme.com/string/string.go`

> make sure to have this file in the acme.com/string package

Create a string reversing function with the following signature
```
func Reverse(s string) string {
}
```

**NOTES:** 
	b := []byte(s) is a way of creating a byte array from a string in golang.

#### 3: change the hello.go to use this new function

Add the following code to the hello.go main function.

```
fmt.Println("strangeloop", " reversed is: ", Reverse("strangeloop"))
```

#### 4: Create a string reverse test

testing in golang is accomplished by creating a file with a `_test.go` extension to the name of the go file primarily under test.  In our example, if we are testing `string.go`, you would create a `string_test.go` file.  Here is an example:

```
import (
	"testing"
)

func Test(t *testing.T) {
	var tests = []struct {
		s, want string
	}{
		{"Hello", "olleH"},
		{"¶","¶"},
		{"",""},
	}

	for _, c := range tests {
		got := Reverse(c.s)
		if got != c.want {
			t.Errorf("Reverse(%q) == %q, want %q", c.s, got, c.want)
		}
	}
}
```

#### 5: Test the code

From `$GOPATH` type: `go test acme.com\string` or from the `$GOPATH/src/acme.com/string` directory type `go test`

#### 6: Fixing the code

It may have been misleading :), but it is a good example of what can happen in the real world.  The code we used `b := []byte(s)` works for ascii, but a byte isn't large enough to handle unicode chars.  To fix our program, use a slice of runes with the following code: `b := []rune(s)`
