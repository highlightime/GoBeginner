# LeetCode 문제풀이

### [160. Intersection of Two Linked Lists](https://leetcode.com/problems/intersection-of-two-linked-lists/)(2021.3.7)_86%,75%



### brute force

```go
func getIntersectionNode(headA, headB *ListNode) *ListNode {
    nodeA,nodeB :=headA,headB
    for nodeA!=nil{
        for nodeB!=nil{
            if nodeA==nodeB{
               return nodeA
            }
            nodeB=nodeB.Next
        }
        nodeA=nodeA.Next
        nodeB=headB
    }
    return nil
}
```



### 뒤에서부터 검사

```go
func getIntersectionNode(headA, headB *ListNode) *ListNode {
    if headA ==nil || headB==nil{
        return nil
    }
    var listA,listB []*ListNode
    nodeA,nodeB :=headA,headB
    
    for nodeA!=nil{
        listA=append(listA,nodeA)
        nodeA=nodeA.Next
    }
    for nodeB!=nil{
        listB=append(listB,nodeB)
        nodeB=nodeB.Next
    }
    
    i,j:=len(listA)-1,len(listB)-1
    for{
        if i==-1 || j==-1{
            return listA[i+1]
        } 
        if listA[i]!=listB[j]{
            if i==len(listA)-1 && j==len(listB)-1{
                return nil
            }
            return listA[i+1]
        }
        i--
        j--
    }
    return nil
}
```

