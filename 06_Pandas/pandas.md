## 3. Pandas 설치 및 활용
 - - - 
### 3.1  Pandas 설치 
- 현재 설치된 라이브러리 확인 
> pip list

- 버전 확인 및 최신 버전 upfrade 
> python.exe -m pip install --upgrade pip

- 라이브러리 설치 
> pip install pandas

- - -
### 3.2 Pandas
- 파이썬 데이터 처리를 위한 라이브러리 
- 데이터 분석 작업에서 많이 활용
```python
import pandas as pd
```

--- 
#### 3.2.1 Pandas 구조 
- 시리즈(Series)
- 데이터프레임(DataFrame)
- 패널(Panel)

--- 

#### 3.2.2 시리즈(Series)
- 1차원 배열의 값과 인덱스를 가짐
```python
    data_list = [17000, 18000, 1000, 5000]
    index_list = ["피자", "치킨", "콜라", "맥주"]
    sr = pd.Series(data_list,
                   index=index_list)
    print(sr)
```

- 값 과 인덱스 출력 
```python
print('시리즈의 값 : {}'.format(sr.values))
print('시리즈의 인덱스 : {}'.format(sr.index))
```
- - - 
#### 3.2.3 데이터프레임(DataFrame)
-  2차원 리스트를 매개변수로 전달
- 행방향 인덱스(index), 열방향 인덱스(column)을 가짐
- 시리즈에 열(columns)이 추가되어  세개의 구성 요소를 가짐

---
#### 3.2.4 데이터 프레임 생성 
- 세 개의 구성 요소를 통한 생성 
```python
values = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
index = ['one', 'two', 'three']
columns = ['A', 'B', 'C']

df = pd.DataFrame(values, index=index, columns=columns)

print('데이터프레임 출력 :')
print('-'*18)
print(df)
```
- 인덱스(index), 값(values), 열(columns) 출력
```python
print('데이터프레임의 인덱스 : {}'.format(df.index))
print('데이터프레임의 열이름: {}'.format(df.columns))
print('데이터프레임의 값 :')
print('-'*18)
print(df.values)
```
- 리스트를 통한 생성
```python
data = [
    ['1000', 'Steve', 90.72], 
    ['1001', 'James', 78.09], 
    ['1002', 'Doyeon', 98.43], 
    ['1003', 'Jane', 64.19], 
    ['1004', 'Pilwoong', 81.30],
    ['1005', 'Tony', 99.14],
]

df = pd.DataFrame(data)
print(df)
```
- 데이터프레임의 열(columns) 지정
```python
df = pd.DataFrame(data, columns=['학번', '이름', '점수'])
print(df)
```
- 딕셔너리(dictionary)를 통한 생성
```python
data = {
    '학번' : ['1000', '1001', '1002', '1003', '1004', '1005'],
    '이름' : [ 'Steve', 'James', 'Doyeon', 'Jane', 'Pilwoong', 'Tony'],
    '점수': [90.72, 78.09, 98.43, 64.19, 81.30, 99.14]
    }

df = pd.DataFrame(data)
print(df)
```
- - - 
#### 3.2.5 데이터프레임 조회
- df.head(n) - 앞 부분을 n개만 보기

```python
print(df.head(3))
```
- df.tail(n) - 뒷 부분을 n개만 보기
```python
print(df.tail(3))
```
- df['열이름'] - 해당되는 열을 확인
```python
print(df['학번'])
```
- - - 
#### 3.2.6 외부 데이터 읽기 
- 판다스는 CSV, 텍스트, Excel, SQL등 다양한 데이터 파일을 읽고 데이터 프레임을 생성 할 수 있음
- - - 
- CSV 읽기
```python
df = pd.read_csv('Ex/example.csv')
print(df)
```
- Json 읽기
```python
df = pd.read_json('Ex/example.json')
print(df)
```
- Excel 읽기
```python
    df = pd.read_excel('Ex/example.xlsx')
    print(df)
```
- - - 
#### 3.2.7 데이터 프레임
* [DataFrame 참고자료](https://wikidocs.net/book/7188)

- - - 
#### 3.2.8 df -> dict() 전환 
```python
df.to_dict(orient='dict', into=)
```
- orient: 출력 dict의 형태를 지정 

````
dict : {열 : {행 : 값, 행 : 값}, 열 : {행 : 값, 행 : 값}
list : {열 : [ 값 ], 열 : [ 값 ] }
series : {열 : Series, 열 : Series}
split : { index : [ 행, 행 ], columns : [ 열, 열 ], data : [ 값, 값 ] }
records : [ { 열 : 값 , 열 : 값 }, { 열 : 값, 열 : 값 } ]
index : { 행 : {열 : 값, 열 : 값}, 행 : {열 : 값, 열 : 값} }
````
- Base_data
```python
df = pd.DataFrame([[1,2],[3,4]], columns=['col1','col2'],index=['row1','row2'])
print(df)
>>
      col1  col2
row1     1     2
row2     3     4
```

- dict
```python
print(df.to_dict(orient='dict'))
>>
{'col1': {'row1': 1, 'row2': 3}, 'col2': {'row1': 2, 'row2': 4}}
```
- list
```python
print(df.to_dict(orient='list'))
>>
{'col1': [1, 3], 'col2': [2, 4]}
```
- series
```python
print(df.to_dict(orient='series'))
>>
{'col1': row1    1
row2    3
Name: col1, dtype: int64, 'col2': row1    2
row2    4
Name: col2, dtype: int64}
```
- split
```python
print(df.to_dict(orient='split'))
>>
{'index': ['row1', 'row2'], 'columns': ['col1', 'col2'], 'data': [[1, 2], [3, 4]]}
```
- records
```python
print(df.to_dict(orient='records'))
>>
[{'col1': 1, 'col2': 2}, {'col1': 3, 'col2': 4}]
```
- index
```python
print(df.to_dict(orient='index'))
>>
{'row1': {'col1': 1, 'col2': 2}, 'row2': {'col1': 3, 'col2': 4}}
```
- - - 
### 참고 자료 
- https://wikidocs.net/book/2155  딥 러닝을 이용한 자연어 처리 입문
