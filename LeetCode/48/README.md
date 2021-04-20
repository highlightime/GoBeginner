# LeetCode 문제풀이

### [48. Rotate Image](https://leetcode.com/problems/rotate-image/)(2021.4.19)_100%,14%



1. 전치행렬(대각선으로 접기)로 바꾼 후,
2. 세로로 반 접는다.



```go
func swap(a *int, b *int){ 
    var temp int 
    temp = *a 
    *a = *b 
    *b = temp 
} 


func rotate(matrix [][]int)  {
    for i:=0;i<len(matrix);i++{
        for j:=i+1;j<len(matrix);j++{
            swap(&matrix[j][i],&matrix[i][j])
        }
    }

    for i:=0;i<len(matrix);i++{
        for j:=0;j<len(matrix)/2;j++{
            swap(&matrix[i][j],&matrix[i][len(matrix)-1-j])
        }
    }
}
```

