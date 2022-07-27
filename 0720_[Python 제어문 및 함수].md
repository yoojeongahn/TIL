# [Python 제어문 및 함수]

.

#### 제어문(조건문/반복문)

특정 상황에 따라 코드를 선택적으로 실행하거나 계속하여 실행하는 제어가 필요함

.

###### 조건문

참/거짓을 판단할 수 있는 조건식과 함께 사용

```python
if 조건 == True:
    # 코드
else:
    # 코드
```

복수 조건문(elif 활용), 중첩 조건문(if문 속 if문), 조건 표현식(true if 조건 else false)

.

###### 반복문

특정 조건을 만족할 떄까지 같은 동작을 계속 반복하고 싶을 때 사용

- <u>while 문</u>  : 종료 조건에 해당하는 코드를 통해 반복문을 종료시켜야 함

- <u>for 문</u> :반복가능한 객체를 모두 순회하면 종료

- <u>반복 제어</u> : break, continue, for-else
1. while문
- 조건식이 참인 겨우 반복적으로 코드를 실행, 무한 루프를  하지 않도록 <mark>종료 조건</mark> 반드시 필요

- 복합연산자 : 연산과 할당을 합쳐 놓은 것 ex)  a += 1

- ```python
  while 조건:
      코드
      복합연산
  ```
2. for 문
- 처음부터 끝까지 모두 순회하므로 별도의 종료 조건이 필요하지 않음

- ```python
  fruits = ['apple','mange',banana']       chars input()
  for fruit in fruits:                     for char in chars:
      print(fruit)                             print(char)
  
  dict에서는 key값을 순회
  grade = {'john':80,'eric':90}         grade = {'john':80,'eric':90}
  for student in grades:                for student in grades:
      print(student)                      print(student,grades[student])
  ```

- ```python
  Dictionary 순회
  grades = {'john':80,'eric':90}        for student, grade in grades:
  print(grades.keys())                       print(student, grade)
  print(grades.values())
  print(grades.items())
  ```

```
- enumerate 순회 : 인덱스와 객체를 쌍으로 담은 열거형(enumerate) 객체 반환

- ```python
enumerate 순회 : 인덱스와 객체를 쌍으로 담은 열거형(enumerate) 객체 반환
members = ['민수', '영희', '철수']

for idx, number in enumerate(members):
    print(idx, number)
```

- 

- ```python
  List Compreshension
  code for 변수 in iterable
  
  cubic_list = []
  for number in range(1, 4):
      cubic_list.append(number**3)
  print(cubic_list)
  
  cubic_list = [number ** 3 for number in range(1,4)]
  print(cubic_list)
  ```
3. 반복문 제어
   
   - break - 반복문을 종료
   
   - continue - 이후의 코드 블록은 수행하지 않고, 다음 반복을 수행(skip)
   
   - for-else - 반복문을 실행한 후 else문 실행 
   
   - pass - 아무것도 하지 않음

.

#### 함수

함수를 왜 사용할까?  분해, 추상화

분해 - 기능을 분해하고 재사용 가능하게 만듬 (ex. len(), sum()), 간결하고 이해하기 쉽다!

추상화 - 복잡한 내용을 모르더라도 사용할 수 있도록 재사용성, 가독성, 생산성(print( ))

.

함수의 종류

- 내장 함수 - 파이썬 개발자(기본적으로 포함됨)

- 외장 함수 - 다른 개발자 만든/ import 문을 통해 사용(외부 라이브러리)

- 사용자 정의 함수 - 사용자가 직접 만든 함수

.

함수의 기본 구조

선언과 호출(define & call), 입력(input), 문서화(docstring), 범위(scope), 결과값(output)

-선언

```python
def function_name(parameter):
    code block
    return 
```

-함수의 결과값

Void function(return 값이 없는 경우, None을 반환)

Value returning function(return문을 통해 값 반환)

print vs return ( print를 사용하면 출력은 되나 변수 저장 X)

튜플을 활요하여 두 개 이상의 값 반환

.

-함수의 입력

Parameter : 함수를 <u>정의</u>할 때, 함수 내부에서 사용되는 변수

Argument : 함수를 <u>호출</u> 할 때, 넣어주는 값

   필수 argument

   선택 argument

   <mark>가변 인자(*args)</mark> - 패킹, 언패킹 과정에서 asterisk *를 넣어 나머지 인자를 묶을 수 있다.

   가변 키워드 인자(**kwwags) - 딕셔너리로 묶여 처리되며 parameter에 **를 붙여 표현

.

Python의 범위(Scope)

global scope/variable , local scope/variable

이름 검색 규칙 LEGB(Local, Enclosed, Global, Built-in Scope 순으로 검색)

.

함수의 응용

map(function, iterable)  ex) map(str, numbers)   map(int,input().split())

filter(function, iterable) 

```python
def odd(n):
    return n % 2
numbers = [1, 2, 3]
result = filter(odd, numbers)
print(list(result), type(result)) # [1,3] <class 'filter'>
```

zip(*iterables)

lambda 함수 : 재사용X, 함수를 정의해서 사용하는 것보다 간결하게 사용

재귀 함수(recurisive function) : 자기 자신을 호출하는 함수

base case 도달할 때까지 함수를 호출함 최대 재귀 깊이 1000번(stack overflow)

반복문 재귀 함수 비교

.

모듈(다양한 기능을 하나의 파일로.py)/ 패키지(다양한 파일을 하나의 폴더로)

라이브러리(다양한 패키지를 하나의 묶음으로) vs 프레임워크

파이썬 패키지 관리자(pip)  패키지의 활용 공간(가상환경)

import module / from module import *  / from package import module

.

사용자 모듈과 패키지

패키지

가상환경 
