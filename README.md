# Study for Go Beginner

### Go tutorial

Go의 경우, 지정된 경로에서 go 코드를 작성해야한다

> Go PATH
>
> Mac : usr/local/go OR **~/go**
>
> (bin pkg src 이 있는 디렉토리, src가 없다면 src 파일 만들기)
>
> Windows : C:\Go



1. 소스코드가 들어갈 디렉토리 만들기 in ~/go/src/

```
mkdir temp.com
```



2. tracking dependencies 위한 새 모듈 init

```
cd temp.com
go mod init temp.com
```



3. 소스코드 작성하기 - main.go

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```



4. 실행하기

```
go run .
```





원하는 모듈, 코드를 다운받는 방법

> NodeJS -> npm, python->pip 이지만, 
>
> Go -> 모든 것을 다운로드 경로별로 디렉토리가 만들어져 관리됨
>
> jsonpackage 따위는 없답니다..!



Mac 에서 vscode .code 명령어 실행

> command + shift + p
>
> Shell Command : install 'code' command in PATH 검색해 install
>
> 현재 경로에서 vscode를 열 수 있다.

```
. code
```





### Import

```go
import "fmt"
//or
import (
  "fmt1"
  "fmt2"
)
```





### Variables and Constants

> constant 는 변경 불가

```go
const a string = "hi"
a = "bye" // 불가능
```



> var 는 변경 가능

```go
var name string = "y"

name = "z" // 가능
```



> 축약형 :=
>
> 타입은 첫번째 값을 기준으로 자동으로 찾아줌
>
> func 안에서만 됨

```go
name := "y"  
```

### array
```go
name []
```





### func 

> return 타입을 뒤에 적어줌
>
> 파라미터의 타입을 뒤에 적어줌

```go
func multiply(a int,b int) int{
  return a * b
}
```



> return 값들을 2개이상 받을 수 있다!

```go
func lenAndUpper(name string)(int,string){
  return len(name),strings.ToUpper(name)
}
```



> ... : arguments 여러개 받기

```go
func repeat(words ...string){
  fmt.Println(words)
}
func main(){
  repeat("kim","lee","park")
}
```



> return 값을 함수 선언시에 나타내면 return 문을 생략할 수 있다.

```go
func lenAndUpper(name string)(leng int, upper string){
  leng = len(name)
  upper = strings.ToUpper(name)
}
```



> defer : func가 끝나고 나서 code를 실행할 수 있다

```go
func lenAndUpper(name string)(leng int, upper string){
  defer fmt.Println("fin")
  leng = len(name)
  upper = strings.ToUpper(name)
}
```





### 반복문

> for 이용

```go
func superAdd(numbers ...int){
  for i:=0;i<len(numbers);i++{
    total+=numbers[i]
  }
}
```



> range 이용

```go
func superAdd(numbers ...int) {
  for _, number := range numbers{ //_는 index
    total+=number
  }
}
```





### 조건문

if 뿐만을 위한 변수 생성 가능

```go
func canIDrink(age int)bool{
  if koreanAge := age+2; koreanAge < 18 {
    return false
  }
  return true
}
```





### Switch

```go
func canIDrink(age int)bool{
  switch koreanAge := age+2; koreanAge{
    case 10:return false
    case 18:return true:
  }
  return false
}
```



### Pointers 

> C 와 동일

```go
func main(){
  a := 2
  b := &a
  *b =20
  fmt.Println(a)
  a = 15
  fmt.Println(*b) //a의 주소값을 참조하기 떄문에 a가 바뀔때 같이 바뀐다
}
```



### Arrays

```go
func main(){
  names := []string{"kim","lee","park"}
  names = append(names,"seo")
  fmt.Println(names)
}
```





### Maps

```go
func main(){
  infos :=map[string]string{"name":"lemon","age":"12"}
  //    map[key_type]value_type
  for keys, value := range infos{
    fmt.Println(value)
  }
}
```





### Struct

> constructor method 가 없다.
>
> Java : constructor(), python: __ init __

```go
type person struct{
  name string
  age int
  favFood []string
}

func main(){
  favFood := []string{"a","b"}
  kim :=person{name:"kim",age:18,favFood:favFood}
}
```













