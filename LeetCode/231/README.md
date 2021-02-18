# LeetCode 문제풀이

### [231. Power of Two](https://leetcode.com/problems/power-of-two/)(2021.2.18)_100%,100%



## 모범답안

```go
func isPowerOfTwo(n int) bool {
    return n > 0 && ((n & (n-1)) == 0)
}
```



### 비트 연산자로 풀기

```go
n & (n-1) == 0 // 의미?
```

