```
m := make(map[int]int)
nums := []int{2, 2, 1, 1, 1, 2, 2}  
n[nums[0]] = 1

// to check value and key map
// var value, isExist = n[nums[0]]

for i := 1; i < len(nums); i++ {  
	_, exists := n[nums[i]]  
		if exists {  
			n[nums[i]]++  
		} else {  
			n[nums[i]] = 1  
		}  
}
```