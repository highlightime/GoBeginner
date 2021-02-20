# LeetCode 문제풀이

### [112. Path Sum](https://leetcode.com/problems/path-sum/)(2021.2.20)_94%,23%



```go
func hasPathSum(root *TreeNode, targetSum int) bool {
    if root == nil {
        return false
    }
    
    nextTarget := targetSum - root.Val
    if root.Left == nil && root.Right == nil && nextTarget == 0 {
        return true
    }
    
    return hasPathSum(root.Left, nextTarget) || hasPathSum(root.Right, nextTarget)
}
```



### 리턴 값이 불리안에다 || or 문제라면

true 값만 설정해줘도 된다.



### && 로 묶을 수 있는 if 문이라면 무조건 묶자 생각보다 차이 많이 난다

```go
if root.Left == nil && root.Right == nil && nextTarget == 0 {
        return true
}
```

