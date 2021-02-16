# LeetCode 문제풀이

### [268. Missing Number](https://leetcode.com/problems/missing-number/) (2021.2.16)_89%,21%

```go
func missingNumber(nums []int) int {
    var a []int = make([]int, len(nums)+1)
    for i:=0;i<len(nums);i++{
        a[nums[i]]=1;
    }
    
    for i:=0;i<=len(nums);i++{
        if a[i]<1 {
            return i
        }
    }
    return 1
}
```



### 동적 배열 선언 (slice)

```go
 var a []int //슬라이스의 길이는 0입니다. 
 var a []int = make([]int, 5) // int형에 길이가 5인 슬라이스에 공간 할당
 var b = make([]string, 5) // 자료형 생략 가능
 c := make([]float64, 5, 10) // var 생략 가능
```



### slice 에 배열 추가

```go
var add []int
add := append(a, 6, 7, 8)

a := []int{1, 2, 3}
b := []int{4, 5, 6}
a = append(a, b...) 
```



### 정적 배열 선언

```go
var a [5]int = [5]int{32, 29, 78, 16, 81}
var d := [...]string{"apple", "lg", "samsung", "kt"}
```

