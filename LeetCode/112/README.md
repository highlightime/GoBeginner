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



### nil

참조 https://blog.billo.io/devposts/nil_for_go/

Go언어에는 `zero value` 라는 것이 있다. 변수를 선언할 때, 따로 특정 값을 할당하지 않으면 자동으로 부여되는 값을 `zero value` 라고 한다.

string의 경우에는 `""`,

boolean은 `false`,

숫자형은 `0`,

함수, 포인터, 인터페이스, slice, 채널, 맵은 `nil`

이 `zero value`이다.

보면 알다시피 string, boolean, 숫자 모두 `nil` (다른 언어에서의 `null`)이 아닌 다른값들이 `zero value`로 선언되어 있기 때문에, 따로 초기화 하지 않아도 Nil Pointer Exception 이 나지 않는다.