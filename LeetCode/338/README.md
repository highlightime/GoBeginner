# LeetCode 문제풀이

### [338. Counting Bits](https://leetcode.com/problems/counting-bits/)(2021.3.21)_10%,29%

내 답안

```go
var cnt int = 0
func dec2bin(dec int) int {
    if dec >= 1 {
        if dec%2 ==1{
            cnt++
        }
        dec2bin(dec/2)
    }
    return cnt
}
func countBits(num int) []int {
    temp:=[]int{0}
    
    for i:=1;i<=num;i++{
        temp=append(temp,dec2bin(i))
        cnt=0
    }
    
    return temp
}
```









최고답안 1

```go
func countBits(n int) []int {
    arr := make([]int, n+1)
    arr[0] = 0
    prevPow := 1
    for i:=1 ;i<=n; i++ {
        if i & (i-1) == 0 {
            arr[i] = 1
            prevPow = i
            continue
        }
        arr[i] = 1 + arr[i-prevPow]
    }
    return arr
}
```

최고답안 2

```go
func countBits(num int) []int {
    ret := make([]int,num + 1)
    for i:=1; i<= num; i++{
        if i & 1 == 0 {
            ret[i] = ret[i>>1] // if i is even number of 1 is equal to that in the half of i
        }else{
            ret[i] = ret[i>>1] + 1 //if i is odd number of 1 is equal to 1 + that of half of i
        }
    }
    return ret
}
```

