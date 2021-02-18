# LeetCode 문제풀이

### [202. Happy Number](https://leetcode.com/problems/happy-number/)(2021.2.17)_100%,78%



```go
func isHappy(n int) bool {
    var checked []int
    var sum int
    for {
        a := n % 10
        sum += a * a
        n = n / 10
        if n < 1 {
            if sum == 1 {
                return true
            }
            if contains(checked,sum) {
                return false
            }
            checked = append(checked,sum)
            n = sum
            sum = 0
        }
    }
    return false
}
```



### while문 

```go
for {
  sum += 1
  if sum ==1 {
    return 
  }
}
```





### 동적 배열 선언과 요소 추가

```go
var checked []int
checked = append(checked,sum)
```



### 중복 확인 함수 (contains)

```go
if contains(checked,sum) ...


func contains(s []int, e int) bool {
    for _, a := range s {
        if a == e {
            return true
        }
    }
    return false
}
```

