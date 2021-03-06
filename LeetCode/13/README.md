# LeetCode 문제풀이

### [13. Roman to Integer](https://leetcode.com/problems/roman-to-integer/)(2021.3.6)_36%,21%



같은 풀이지만 map 선언을 하지 않아 하드코딩을 했던 나...

romans['X'] => 10을 찾아준당



```go
romans := map[uint8]int{
	'I': 1,
	'V': 5,
	'X': 10,
	'L': 50,
	'C': 100,
	'D': 500,
	'M': 1000,
}


```



```go
for i := 0; i < len(s); i++ {
		if target, ok := romans[s[i]]; ok {
			res += target
		}
		if i != 0 && prev < romans[s[i]] {
			res -= 2 * prev
		}
		prev = roman_map[s[i]]
	}
```

