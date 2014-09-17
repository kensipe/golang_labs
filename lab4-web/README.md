## Introduction

In this lab you will create a web application in golang.

## Steps

#### 1: create a handler for the code below which displays to the browser the passed in value

http://localhost:8080/strangeloop will bring Hello strangeloop and
http://localhost:8080/ken will bring Hello Ken

```
import (
	"fmt"
	"net/http"
)

func main() {
	http.HandleFunc("/", handler)
	http.ListenAndServe(":8080", nil)
}```

** NOTES: ** you will need to research: `func handler(w http.ResponseWriter, r *http.Request) {`