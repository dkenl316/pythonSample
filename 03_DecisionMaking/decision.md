## 2. 파이썬 기본 문법
 - - - 
### 2.2  분기문

- 참(True) 또는 거짓(False)을 반환하는 조건식의 결과에 따라 다음 실행을 결정 
- - -

#### 2.2.1 if문의 종류 
| 구분           | 설명                       |
|--------------|--------------------------|
| if 문       | 	분기 조건이 만족할 경우에 하나 이상의 문을 가지는 형식이다.       |
| if ... else 문     | 	분기 조건식이 참일 경우와 거짓일 경우에 하나 이상의 문을 가지는 형식이다.   |
| 중첩된 if 문   | 		분기 조건식 내부에 분기 조건식이 다중으로 나타나는 형식이다.      |

- - - 

#### 2.2.2 if 문

- 조건의 결과가 참(True)일 때 실행
```python
condition = 0

# condition 값이 0 일때 출력
if condition == 0:
    print("Condition Code")          # Condition Code 
print("End Program")            # End Program
```
- - -
#### 2.2.3 if ... else 문

- 조건의 결과를 참(True)와 거짓(false) 로 나누어 실행
- elif 를 통해 확장 
```python
condition0 = 0
condition10 = 10

# condition0 값이 0 일때 출력
if condition0 == 0:
    print("Condition0 Code")                    # condition0 Code
elif condition0 == 1:
    print("Condition0값이 1일 경우에 출력")
elif condition10 == 10:         
    print("Condition10값이 10일 경우에 출력")    # 출력되지 않는다. 
else:
    print("Condition Value")

print("End Program")                            # End Program
```
- - -
#### 2.2.4 중첩된 if 문 
```python
conditionOut = 0
conditionIn = 1

# conditionOut 값이 0 일때 출력
if conditionOut == 0:
    if conditionIn == 0:
        print("Condition 값이 0 일때 출력")       
    else:
        print("Condition 값이 0 이 아닌때 출력")    # Condition 값이 0 이 아닌때 출력
else:
    if conditionIn == 0:
        print("Condition 값이 0 일때 출력")
    else:
        print("Condition 값이 0 이 아닌때 출력")

print("End Program")                              # End Program
```
- - - 
##### 자료 출처 
* https://gostart.tistory.com/category/Python%20Language
