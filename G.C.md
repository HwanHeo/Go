### Garbage Collector
**G.C**는 레퍼런스 카운트가 0인 값을 찾아서 메모리에서 삭제합니다. 
assigned() 함수가 값을 리턴하고 v에 값이 적용된 후 다음 라인이 실행될때 **G.C**는 assigned() 함수에 레퍼런스 카운트가 0인 값을 찾아서 메모리에서 삭제합니다.
```GO
func assigned() *int {
	var a int  // a reference count 1
	var b int  // b reference count 1
	
	a = 3
	p = &a   // a reference count 2
	
	return p
}

// v reference count 1, a reference count 3
v := assigned() 

// v -> a reference count 1, value = 3
fmt.Println(v)
```
