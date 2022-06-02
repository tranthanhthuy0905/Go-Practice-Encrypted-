# Go-Practice 101

*Go is a **compiled** language*

### Features:
- Strong and statically typed (Type ir vars not change over time, defined in compile time)
- Simplicity, fast compile times, Garbage collected (not cleaning memory)
- Built-in concurrency
- Compile to standalone binaries (Go library bundled into binary to run application) - Compile to executable binary file

### Commands:
- ```go run file``` - compile to the executable binary file in a temporary directory, run it then delete it
- ```go build filePath``` - compile to the executable binary file in main
- ```go install filePath``` - compile to the executable binary file in bin folder

### Variables:
- Declaration: 
``` 
Way 1: var i int 
    i = 20 
Way 2: var i int = 20
Way 3: i := 20 - self-figure out the type => Create a new variable 
Way 4: in the package level 
    var i float32 = 12.24
    func main() {}

    Grab several vars:
    var(i1 = 1, i2 = 1, i3 = 1, i4 = 1)
```
To print **_value and type_** of variables, ```fmt.Printf("%v, %T", i, i)``` // 20, int <br/>
=> Compile error: If local var defined but not used, compile error <br/>
**Can't Redeclare but Shadow** <br/>
**_Shadowing_** - innermost-scope variables will be used if similar var name

- Naming: 
<br/>NOT ```user-name```
<br/>Case sensitive: 
    - Email: (Capitalized var) exported among packages
    - password: (normalize) only inside package
    - CONSTANT

- Scope: No private scope but block scope is the innermost, package scope is outside

### Data Types:
1. Boolean Type: bool (default- false)
```var n bool  true
m := 1 == 0
```

2. Numeric Type: int (default - 0), float32 (default - 0), float64, string (default - "")
- Convert int to float: i = float32(j)
- Convert float to int: i = int(j)
- Convert int to string: i = string(j) => *Search the ith element in the table*
- Convert strictly int to string:
```
import ("strconv")
i = strconv.Itoa(j)
```
3. Text Type: string (default - "")