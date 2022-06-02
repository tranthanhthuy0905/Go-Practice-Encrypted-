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

- Scope: No private scope but block scope is the innermost, package scope is outside

### Data Types:
1. Boolean Type: bool (default- false)
```var n bool  true
m := 1 == 0
```

2. Numeric Type: int (default - 0), int8, int16, float32 (default - 0), float64
<br/>Arithmetic among different-type var cause errors
- Convert int to float: i = float32(j)
- Convert float to int: i = int(j)
<br/>complex64, complex8 (1 + 2i). => **complex(realVal, imagVal)

3. Text Type: string (default - "")
```s:= "Something"
Printf(s[2]) => 105
Printf(string(s[2])
```
- Convert int to string: i = string(j) => *Search the ith element in the table*
- Convert strictly int to string:
```
import ("strconv")
i = strconv.Itoa(j)
```
- Convert string to a collection of char byte: ```b:=[]byte(s)```

### Constant: Value not change
<br/> const myConstant  // Not exported
<br/> const MyConstant  // Exported

1. Typed constant:
const myConstant int = 123 
<br/> => Can ALSO Shadow a constant

2. Untyped constant:
<br/>const myConstant = 123  // self-define the type 
<br/> Flexible type: int, int8, int16

3. Enumerate constant:
``` 
const(
    a = iota  // 0
    b = iota  // 1
    c         // 2
)
const _ = iota // ignore the first initialization of iota
const bitshift = 1 << (10 * iota)>>
var i int = 1
fmt.Println(i == b) /// true
var j int8 = 0
fmt.Println(j == a) /// true
```
<br/> Block scope