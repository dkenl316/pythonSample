## 2. 파이썬 기본 문법
 - - - 
### 2.3  반복문

 - 동일한 내용을 반복해서 실행 
- - -
#### 2.3.1 반복문의 종류

|    구분    | 설명 |
|:--------:|----|
|  while   | 	명령문을 실행하기 전 반복 조건문의 결과를 구하고, 참 일 동안 명령문 또는 그룹을 반복한다. |
|   for    | 	명령문을 실행하기 전 반복 조건문의 결과를 구하고, 참 일 동안 명령문 또는 그룹을 반복한다. |
| 중첩된 반복문  | 	반복문 내부에 하나 이상의 반복문이 존재하는 반복문의 형태이다.  |

- - - 
#### 2.3.2 반복문의 제어
 |      구분      | 설명 |
|:------------:|----|
|    break     | 	반복문을 종료하고 반복문 바로 다음 명령문을 실행할때 사용한다. |
| continue     | 	반복문의 나머지 부분을 건너 뛰고, 반복하기 전 상태에서 반복 조건문의 결과를 구할때 사용한다. |
|     pass     | 	반복문의 나머지 코드를 실행하지 않고 건너뛸 경우에 사용한다.   |
- - -
#### 2.3.3 While 문 

- 반복 조건문이 참(True)값일 경우 또는 명령문 그룹 반복 실행 
- 반복 조건문 값이 거짓(false)일 경우 종료
```python
condition = 0

while(condition < 10):
    print("The Condition is :", condition)
    condition += 1

print("End Program")
```
- - -
#### 2.3.4 무한 루프 
- 무한 루프에 주의
```python
while 1:
    newString = input("Please enter a letter: ")
    print("The character you entered is ",  newString )
```
- - -

#### 2.3.5 while ~ else 문 
```python
condition = 0

while(condition < 10):
    print("The Condition is :", condition)
    condition += 1
else:
    print("While 문 실행 후 추가 실행")

print("End Program")
```
- - -
#### 2.3.6 for 문 

 - 반복 조건의 값을 소진하여 명령문 반복
```python
indexSequence = ["One", "Two", "Three", "Four"]

for index in indexSequence:
    print(index)

print("End Program")
```
- - - 
#### 2.3.7 인덱스를 이용한 for 문 
```python
indexSequence = ["One", "Two", "Three", "Four"]

for index in range(len(indexSequence)):
    print("This index is : ", index, ", This Sequence Value is : " , indexSequence[index])

for index in range(10, 15):
    print("This index is : ", index)
print("End Program")
```
- - -
#### 2.3.8 for ~ else 문 
```python
for index in range(1, 10):
    print(index)
else :
    print("For 문 실행 후 추가 실행")

print("End Program")

```
- - - 
#### 2.3.9 중첩된 반복문 
- 반복문 내에 반복문을 사용
```python
for indexOut in range(1, 3):
    print("Index Out Loop : ", indexOut)
    for indexIn in range(10, 13):
        print("  Index Out : ", indexOut, "Index In : ", indexIn )
```
- - - 
#### 2.3.10 break 문 
 - 반복문 내부에 사용
 - 반복문을 종료 
```python
for index in range(1, 10):
    print(index)
    if index == 5:
        break;

print("End Program")
```
- - - 
#### 2.3.11 continue 문
- continue 이후 블럭의 실행 하지 않고 처음으로 이동하여 실행 
```python
for index in range(1, 10):
    print("Continue before statement : ", index)
    if index == 5:
        continue
    print("Continue after statement : ", index)
print("End Program")
```
- - -
#### 2.3.12 pass 문 
- 구문적으로 필요 하지만 다음 블록을 실행이 필요가 없을 때
- 일반적으로 오류 제어에 사용
```python
for index in range(1, 10):
    print("Pass before statement : ", index)
    if index == 5:
        pass
        print("Pass after statement : ", index)
print("End Program")
```
- - -
