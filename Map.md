## Map
**Go** 언어는 기본 자료형으로 **맵**을 지원합니다. **맵** 키-값 형태로 자료를 저장하고 레퍼런스 타입입니다.

### 선언
`[]`안에는 키의 자료형을 지정하고 그 뒤에 값의 자료형을 지정합니다. **맵**은 **make** 함수를 통해 사용할 수 있습니다. 
```Go
// key: string, value: int
var a map[string]int = make(map[string]int)
var b  = make(map[string]int)
c :=  = make(map[string]int)

// 초기값 선언
a := map[string]int {"Hello": 1, "World": 2}
b := map[string]int {
        "Hello": 1,    
        "World": 2,    // 여러줄일 경우 마지막에도 콤마 사용
}
```

### 데이터 저장, 조회
**맵**에 데이터를 넣으려면 `[]`안에 키를 지정하고 값을 대입합니다. 값을 조회 할 때도 `[]` 안에 키를 지정해서 값을 확인할 수 있습니다. **맵**에서 존재하지 않는 키를 조회했을 때는 **Zero Values**가 적용됩니다. **맵**에 데이터가 있는지 검사할 때는 값을 조회한 뒤 리턴값을 활용합니다. 리턴값에 두 번째 변수를 정의하면 값이 존재할 경우`true` 존재하지 않을 경우 `false`를 리턴합니다.

```Go
values := make(map[string]string]
values["Hello"] = "World"
values["Chicken"] = "Sauce"

if value, exist := values["Chicken"]; exist {
	fmt.Println(value)
}
```

### 데이터 순회, 삭제
**맵**에 데이터는 **배열**, **슬라이스**와 같이 `for range`반복문으로 순회가 가능합니다. **맵**에서 값을 삭제 하려면 `delete`함수를 통해 제거할 수 있습니다.
```Go
values["Hello"] = "World"
values["Chicken"] = "Sauce"
for _, value := range values {
        if value == "Sauce" {
                delete(values, "Chicken")
        }

	fmt.Println("Value: ", value)
}
```
