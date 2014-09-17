## Introduction

In this lab you will create a program which will prompt a user for their age and it will return the age of that user in dog years.  The main benefit of this lab is to understand how to:

* work with stdio
* convert string values into numeric values

## Steps

#### 1: complete the following code

```
func main() {

	fmt.Println("Enter Age:")

	reader := bufio.NewReader(os.Stdin)
	age, _ := reader.ReadString('\n')
	age = strings.TrimSpace(age)
	dogyears, _ := strconv.Atoi(age)

	fmt.Print("the age: ", age, " is ", dogyears , " in dog years"  )

}
```

** NOTE: ** in order to do this lab you will need to 

1. create a buffered reader around `os.Stdin`. (look at bufio)
2. read a string from the buffer
3. convert the string to an int (look at strconv)
4. calculate the value in dog years (age * 7)