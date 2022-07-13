## 변수 할당

```python
# 변수에 할당된 값의 타입 보기
type()
# 변수에 할당된 값(객체)의 고유한 아이덴티티 값 보기
id()
```

---



## 변수 연산

```python
# 같은 값을 동시에 할당할 수 있음
x = y = 1004
print(x,y)

# 다른 값을 동시에 할당할 수 있음
x, y = 1, 2
print(x,y)
```

---



## 사용자 입력

- 대괄호 부분에 문자열을 넣으면 입력시, 해당 문자열을 출력할 수 있음
- 반환값은 항상 문자열의 형태로 반환

```python
name = input('이름을 입력하세요 :')
print(name)
# 이름을 입력해주세요 : 파이썬
```

---



## 자료형 분류

- 불린형 (Boolean Type)

- 수치형 (Numeric Type)

  - int (정수,integer)

  - float (부동소수점, 실수, floation point number)

    - ```
      # 아래는 참일까? 거짓일까?
      3.14 - 3.02 == 0.12
      False
      값 비교하는 과정에서 정수가 아닌 실수인 경우 주의할 것
      ```

  - complex (복소수,complex number)

- 문자열 (String Type)

- None

---



#### None

- 파이썬 자료형 중 하나
- 파이썬에서는 값이 없음을 표현하기 위해 None 타입이 존재
- 일반적으로 반환 값이 없는 함수에서 사용하기도 함.

```
print(type(None))
# <class 'NoneType'>
a = None
#None
```

---



#### 불린(Boolean)

- True / False 값을 가진 타입은 bool
- 비교 / 논리 연산을 수행함에 있어서 활용됨
- 다음은 모두 False로 변환
  - 0, 0.0 () [] {} '', None

```
bool(0) # False
bool('') # False
bool(1) #True
bool([]) #False
bool(-1) #True
bool([1,2,3]) #True

```

---



## 문자열

**중첩따옴표**

- 따옴표 안에 따옴표를 표현할 경우
  - 작은 따옴표가 들어 있는 경우는 큰 따옴표로 문자열 생성
  - 큰 따옴표가 들어 있는 경우는 작은 따옴표로 문자열 생성

```
print("'안녕하세요'")
#'안녕하세요'
print('"안녕하세요"')
#"안녕하세요"
```

**삼중따옴표**

- 작은 따옴표나 큰 따옴표를 삼중으로 사용
  - 따옴표 안에 따옴표를 넣을 때

```
print(''' '안녕하세요' "반갑습니다"''')
#'안녕하세요' "반갑습니다"
```

---



## 슬라이싱



|       | a    | b    | c    | d    | e    | f    | g    | h    | i    |
| ----- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| index | 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    |
| index | -9   | -8   | -7   | -6   | -5   | -4   | -3   | -2   | -1   |

```
a = 'abcdefghi'
print(::-1)
#ihgfedcba
print(::-2)
#igeca
```

- s[::] ⇒ 'abcdefghi’ => s[0:len(s):1]과 동일 
- s[::-1] ⇒'ihgfedcba’ => s[-1:-(len(s)+1):-1]과 동일

---



## Escape sequence

| 예약문자 |                 |
| -------- | --------------- |
| \n       | 줄 바꿈         |
| \t       | 탭              |
| \r       | 캐리지리턴      |
| \0       | 널(Null)        |
| \\\      | \               |
| \\'      | 단일인용부호(') |
| \"       | 이중인용부호(") |

```
print('철수 \'안녕\'')
# 철수 '안녕'
print('이 다음은 엔터. \n그리고 탭\t탭')
#이 다음은 엔터.
#그리고 탭   탭
```



## String Interpolation %-formatting

- 문자열을 변수를 활용하여 만드는 법

```
name = 'Kim'
score = 4.5

print('hello, %s' %name)
print('내 성적은 %d' %score)
print('내 성적은 %f' %score)
# hello, Kim
# 내 성적은 4
# 내성적은 4.500000
```

## String Interpolation f-string

```
name = 'Kim'
score = 4.5
print(f'hello, {name}! 성적은 {score}')
#hello, Kim! 성적은 4.5
```

---



#### 문자열 특징

- Immutable : 변경 불가능함

```
a = 'my string?'
a[-1] = '!'

TypeError Traceback (most recent call last) 
----> 1 a[-1] = '!’ 
TypeError: 'str' object does not support item assignment

```

- Iterable : 반복 가능함

```
a = '123'
for char in a:
print(char)
```

---

## 자료형 변환(Typecasting)

- 파이썬에서 데이터 형태는 서로 변환할 수 있음 
- 암시적 형 변환(Implicit) 
  - 사용자가 의도하지 않고, 파이썬 내부적으로 자료형을 변환 하는 경우
- 명시적 형 변환(Explicit) 
  - 사용자가 특정 함수를 활용하여 의도적으로 자료형을 변환 하는 경우

---

#### 암시적 형 변환(Implicit Typecasting)

```
True + 3
# 4
3 + 5.0
# 8.0
3 + 4j + 5
# (8+4j)
```

#### 명시적 형 변환(Explicit Typecasting)

```
# 문자열은 암시적 타입 변환이 되지 않음
'3' + 4
# TypeError: can only concatenate str (not "int") to str
# 명시적 타입 변환이 필요함
int('3') + 4
# 7
# 정수 형식이 아닌 경우 타입 변환할 수 없음
int('3.5') + 5
# ValueError: invalid literal for int() with base 10: '3.5'
float('3.5') + 5
# 8.5
```



