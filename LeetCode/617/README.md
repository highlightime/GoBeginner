# LeetCode 문제풀이

### [617. Merge Two Binary Trees](https://leetcode.com/problems/merge-two-binary-trees/)(2021.3.8)_98%,45%

### prev 기억 

```go
func a(root1 *TreeNode, root2 *TreeNode, prev *TreeNode, dir int) *TreeNode{ 
    if root2==nil{
        return root1
    }
    if root1!=nil&&root2!=nil{
        root1.Val+=root2.Val
        a(root1.Left,root2.Left,root1,0)
        a(root1.Right,root2.Right,root1,1)
    }
    if root1==nil{
        if dir==0 {
            prev.Left=root2
        }
        if dir==1{
            prev.Right=root2
        }
    }
    return root1
}
```





### go 언어의 이점을 활용한 풀이

```go
func mergeTrees(root1 *TreeNode, root2 *TreeNode) *TreeNode {  
    if root1==nil{
        return root2
    }
    if root2==nil{
        return root1
    }
    return &TreeNode{
      Val:   root1.Val + root2.Val,
      Left:  mergeTrees(root1.Left, root2.Left),
      Right: mergeTrees(root1.Right, root2.Right),
	}
}
```

