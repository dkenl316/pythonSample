## 2. 파이썬 기본 문법
 - - - 
### 2.1 변수, 타입, print 
#### 2.1.1 string 
- 문자열 
````python
a = 'Hello World'  
print(a)
print(type(a))
````
---
#### 2.1.2 Int
- 정수형 
````python
b = 10 
print(b)
print(type(b))
````
---
#### 2.1.3 Float
- 실수형
```python
c = 3.14159265
print(c)
print(type(c))
```
---
#### 2.1.4 Boolen
- 참 / 거짓 
```python
d = False
print(d)
print(type(d))
```
---
#### 2.1.5 None 
- Null / 값을 가지지 않음 
```python
e = None
print(e)
print(type(e))
```
---
#### 2.1.6 List
- 복합 데이터 유형 []
- (,)를 사용하여 구분
- 각기 다른 유형의 자료도 포함
```python
# 리스트에 값 할당
listValue = [10, 'String', False, 10.5j]
print(listValue)                            # [10, 'String', False, 10.5j]
print(type(listValue))                      # <class 'list'>

# 리스트의 인덱스를 통한 접근
print(listValue[1:2])                       # ['String']
print(listValue[2:])                        # [False, 10.5j]
print(listValue[:2])                        # [10, 'String']

# 리스트의 계산 및 추가 
print(listValue + listValue)                # [10, 'String', False, 10.5j, 10, 'String', False, 10.5j]
print(listValue * 3)                        # [10, 'String', False, 10.5j, 10, 'String', False, 10.5j, 10, 'String', False, 10.5j]

# 리스트에 아이템 추가 
listValue.append('AddString')               
print(listValue)                            # [10, 'String', False, 10.5j, 'AddString']

# 리스트에 아이템 제거
listValue.remove('AddString')
print(listValue)                            # [10, 'String', False, 10.5j]

# 리스트에 리스트 추가 
listValue.append([20, 'Duble String', True, 20.5j])
print(listValue)                            # [10, 'String', False, 10.5j, [20, 'Duble String', True, 20.5j]]
```
---
#### 2.1.7 Set, frozenset 
- Set 수정 o  중복 x 정렬 x 
- frozenset 수정  x
```python
# 셋 데이터 타입속에 하나의 문자 데이터 타입 할당
setString = set('ABBCCCDDDDCCCBBA')
print(type(setString))                          # <class 'set'>
print(setString)                                # {'D', 'C', 'A', 'B'}
setString.add('ABCDEFGHIJKLMN')
print(setString)                                # {'B', 'A', 'D', 'ABCDEFGHIJKLMN', 'C'}

# 셋 데이터 타입에 하나의 요소 할당 
setValue = {'ABBCCCDDDDCCCBBA'}
print(type(setValue))                           # <class 'set'>
print(setValue)                                 # {'ABBCCCDDDDCCCBBA'}
setValue.add('ABCDEF')
print(setValue)                                 # {'ABCDEF', 'ABBCCCDDDDCCCBBA'}

# 셋 데이터 타입에 여러개의 요소 할당
setValues = {'first', 'second', 'third', 'fourth', 'fifth', 'second', 'third'}
print(type(setValues))                          # <class 'set'>
print(setValues)                                # {'second', 'fourth', 'third', 'fifth', 'first'}

# 셋 데이터 타입에 동일한 요소값을 추가 
setValues.add('first')
print(setValues)                                # {'second', 'fourth', 'third', 'fifth', 'first'}

# 셋 데이터 타입에 없는 요소값을 추가 
setValues.add('ABCDEF')
print(setValues)                                # {'ABCDEF', 'second', 'fourth', 'third', 'fifth', 'first'}

# 프로전셋 데이터 타입에 요소값 할당
fsValue = frozenset('ABBCCCDDDDCCCBBA')
print(fsValue)                                  # frozenset({'C', 'B', 'A', 'D'})

# 프로전셋 데이터 타입에 요소값 추가
# 아래 코드는 실행되지 않으며 실행시에는 주석 처리하고 사용하세요 
fsValue.add('ABCDEF')                           # AttributeError: 'frozenset' object has no attribute 'add'
print(fsValue)                                  # frozenset({'B', 'C', 'D', 'A'})
```
---
#### 2.1.8 Tuples
- 복합 데이터 유형 ()
- (,)로 구분 
- 읽기 전용으로 수정 x 
```python
# Tuple 데이터 타입을 할당한다. 
tupleValue = (10, 'String', False, 10.5j)
print(tupleValue)               # (10, 'String', False, 10.5j)
print(type(tupleValue))         # <class 'tuple'>

# Tuple 데이터 인덱스를 통한 값 불러오기 
print(tupleValue[0])            # 10
print(tupleValue[1:2])          # ('String',)
print(tupleValue[1:])           # ('String', False, 10.5j)
print(tupleValue[:2])           # (10, 'String')

# 인덱스를 통하여 수정
# 아래 코드는 작동하지 않습니다. 실행시에는 주석처리하여 사용하십시요 
tupleValue[2] = 'Error'
```
---
#### 2.1.9 Dictionary
- 해시 테이블 유형 {}
- 키와 값이 존재 
- (,)로 구분
```python
# Dictionary 에 값을 할당
dicValue = {'Koran': 100, 'English': 90, 'Mathematics': 95, 'History': 93, 'Physics': 98, 'Chemistry': 97 }
print(dicValue)
# {'Koran': 100, 'English': 90, 'Mathematics': 95, 'History': 93, 'Physics': 98, 'Chemistry': 97}`
print(type(dicValue))               # <class 'dict'>

# Key를 이용한 값 불러 오기 
print(dicValue['Physics'])          # 98

# Key 값 불러오기 
print(dicValue.keys())              # dict_keys(['Koran', 'English', 'Mathematics', 'History', 'Physics', 'Chemistry'])

# Value 값 불러오기
print(dicValue.values())            # dict_values([100, 90, 95, 93, 98, 97])

# Key를 이용한 값의 변경
dicValue['Physics'] = 100
print(dicValue['Physics'])          # 100
```
---
#### 2.1.10 데이터 형식 변환 
|Function|Description|
|---|---|
|int(x)|	x 값을 정수 타입로 변환한다. |
|float(x)|	x 값을 부동 소숫점 타입으로 변환한다.|
|complex(x)|	x 값을 복소수 타입으로 변환한다.|
|str(x)|	x값을 문자 타입으로 변환한다. |
|repr(x)|	x값을 표현식 문자 타입으로 변환한다.|
|eval(str)|	x값이 문자 타입인지를 검증한다.|
|tuple(s)|	s를 튜플 타입으로 변환한다.|
|list(s)|	s값을 리스트 타입으로 변환한다.|
|set(s)|	s값을 셋 타입으로 변환한다. |
|dict(d)|	d값을 딕셔너리 타입으로 변환한다.|
|frozenset(s)|	s 값을 고정 셋 타입으로 변환한다. |
|chr(x)|	x 값을 문자 타입으로 변환한다. |
|ord(x)|	x 문자를 정수 타입으로 변환한다.|
|hex(x)|	x 값을 16진수 문자 타입으로 변환한다.|
|oct(x)|	x 값을 8진수 문자 타입으로 변환한다. |
---
##### 자료 출처 
* https://gostart.tistory.com/205