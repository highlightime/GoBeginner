# LeetCode 문제풀이

### [204. Count Primes](https://leetcode.com/problems/count-primes/)(2021.2.23)_100%,31%



### 에라토스테네스의 체

```go
func countPrimes(n int) int {
    var count int
    prime:=make([]bool,n)
    for i:=2;i<n;i++{
        prime[i]=true
    }
  
    for i:=2;i*i<n;i++{
        if !prime[i]{ // 소수가 아니면
            continue
        }
        for j:=i*i;j<n;j+=i{ // 소수면 소수의 곱들을 거른다
            prime[j]=false
        }
    }
  
    for i:=2;i<n;i++{
        if prime[i]{
            count++
        }
    }
    return count
}
```

