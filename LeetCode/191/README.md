# LeetCode 문제풀이

### [191. Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)(2021.3.5)_100%,100%

### 비트연산자를 이용한 풀이 

- & 와 &&를 혼동하여 잘못쓰지 않도록

```go
func hammingWeight(num uint32) int {
    cnt :=0
    const test uint32 = 00000000000000000000000000000001
    for i:=0;i<32;i++{
        if num & test == test{
            cnt++
        }
        num = num >>1
    }
    return cnt
}
```



### uint32 는 이진수니까 십진수 다루듯 하면 안 됨

- %2, /2

```go
func hammingWeight(num uint32) int {
    count := 0
    for num != 0 {
        if num % 2 == 1 {
            count++
            num--
        }
        num /=2
    }
    return count
}
```

