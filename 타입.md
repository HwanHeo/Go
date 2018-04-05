## 숫자 
정수, 실수, 복소수를 지원합니다.
### 정수
- int
  - 32비트 시스템에서는 `int32`, 64비트 시스템에서는 `int64`
- int8
  - `8bit`, `1byte`
- int16
  - `16bit`, `2byte`
- int32
  - `32bit`, `4byte`
- int64
  - `64bit`, `8byte`

### 실수
실수는 소수점을 사용하거나 지수 표기법으로 표기할 수 있습니다. 변수에 저장될 때는 부동소수점 방식을 사용합니다. 지수 표기법은 e 또는 E를 사용하고 +, -로 소수점의 위치를 지정합니다
```
var num1 float32 = 0.1
var num2 float32 = .327
var num3 float32 = 132.327

var num4 float32 = 1e7
var num5 float64 = .12345E+2
```
컴퓨터는 2진수를 사용해서 2진수로는 실수를 정확히 표현할 수 없습니다. 수학적으로 실수는 무한히 많은데 실수를 유한 개의 비트로 표현하기 위해서는 근사값으로 표현해야 하기 때문입니다. 이런 문제를 부동소수점 반올림 오차라고 합니다. 실수는 연산한 값을 == 로 직접 비교하면 안됩니다.

## 문자열 
문자열은 back quote(``) 혹은 ""로 묶어주어야 하며 한글, 영어, 한자 등 **UTF-8**로 표현할 수 있는 문자를 사용할 수 있습니다.  문자 대신 유니코드를 문자코드로 저장이 가능합니다.

```
var message string = "Hello, World"
message := "Hello, World\n"
```

### 문자열 길이 
```
var ko string = "안녕"
var en string := "Hello"

fmt.Println(len(ko)) // 6
fmt.Println(len(en)) // 5
```
문자열 변수에 문자열의 길이를 구할 때는 len 함수를 사용합니다. 여기서 "안녕"의 문자열의 길이는 2가 아닌 6입니다
한글, 한자, 일본어 등  2byte가 넘는 문자열은 **UTF-8**로 encoding 되었을때 글자당 2로 인식된다. 2byte가 넘는 문자열의 길이를 구하면려면 unicode/utf8 패키지에 RuneCountInString 함수를 사용해야 합니다
```
var ko string = "안녕"

fmt.Println(uft.RuneCountInString(ko)) // 2
```

### 문자열 연산
문자열을 비교할 때는 == 연산자를 사용합니다. 
```
var hello string = "Hello, " 
var world string = "World" 

fmt.Println(hello == world) // false
```
문자열을 합치고 싶은 경우 + 연산자를 통해 문자를 붙일수 있습니다
```
var hello string = "Hello, " 
var world string = "World" 
fmt.Println(hello + world) // Hello, World
```

### 문자출력
```
var hello string = "Hello" 
fmt.Printf("string: %c", hello[0])
```

## 불리언
참과 거짓을 표한하는 true와 false를 사용할 수 있습니다. 변수의 크기는 1byte 입니다. bool은 논리연산자와 같이 사용할 수 있습니다. `&&`, `||`, `!`

```
var t bool = true
fmt.Println(t)// true

var num1 int = 1
var num2 int = 2
var result bool = num1 > num2

fmt.Println(result)// false
```
