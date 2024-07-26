# 2024pythonstudy
2024 여름방학동안 진행한 파이썬 스터디

## variables
* 가장 기초적인 프로그래밍 문법 개념
* 데이터(값)을 저장하기 위한 메모리 공간의 프로그래밍 상의 이름
  * name = "chaewon"은 name이라는 변수에 chaewon이라는 값을 넣으라는 의미
* 위처럼 변수를 선언하면 메모리 어딘가에 주소값을 할당받아 저장됨

  ### 변수명 선언
  * 알파벳, 숫자, 밑줄(_)로 선언
      * 한글은 사용할 수 없음
  * 다른 사람이 읽어도 이해할 수 있도록 의미있는 단어로 표기
  * 대소문자 구분
  * 특별한 의미가 있는 예약어(ex. for, if, else..)는 사용할 수 없음

  ### 기본 자료형
  * 정수형: 자연수를 포함해 값의 영역이 정수로 한정된 값
  * 실수형: 소수점이 포함된 값
  * 문자형: 따옴표에 들어가 있는 문자형
  * 논리형(불린형): 참 또는 거짓 표현

  _참고) 동적타이핑(다이나믹 타이핑)_ <br>
  변수의 메모리 공간 확보가 프로그래밍 실행 시점에서 발생하는 것 <br>
  data = 8이라고 선언했을 때, 인터프리터가 정수인지 실수인지 프로그램 실행 시점에 판단 <br>

  ### 연산
  * 덧셈 연산자: +
  * 뺼셈 연산자: -
  * 곱셈 연산자: \*
  * 나눗셈 연산자: /
  * 제곱승: \**
  * 나눗셈 몫: //
  * 나눗셈 나머지: %
  * 증가연산: +=
  * 감소연산 -=

  ~~~
  25 + 30
  30 - 12
  50 * 3
  30 / 5
  3 ** 5
  7 // 2
  7 % 2
  
  a = 1
  a += 1
  a -= 1
  ~~~

  ### 자료형 변환
  * 정수형과 실수형 간 변환
  ~~~
  a = 10
  print(a)
  # 10
  a = float(10)
  print(a)
  # 10.0
  ~~~

  * 숫자형과 문자형 간 변환
  ~~~
  a = '12.5' # 문자형 선언
  b = float(a) # 실수형 변환
  print(a)
  # 12.5
  print(b)
  # 12.5
  print(a+b) # 문자열과 숫자열의 덧셈 불가능하여 에러 발생

  a = str(a)
  b = str(b)
  print(a+b)
  # 12.512.5
  ~~~

  * 자료형 확인
  ~~~
  a = float(1.2)
  type(a)
  # <class 'float'>
  ~~~

## List
* 시퀀스 자료형, 여러 데이터들의 집합
  ### 인덱싱
  * 리스트에 저장되어 있는 값에 접근하기 위해 상대적인 주소(오프셋)를 사용

  ### 슬라이싱
  * 리스트의 인덱스 기능을 사용하여 전체에서 일부를 잘라서 사용
  * 기본 문법: 변수명[시작 인덱스:마지막 인덱스]
  ~~~
  cities = ['서울', '부산', '인천', '대구', '대전', '광주', '울산', '수원']
  cities[0:6]
  # ['서울', '부산', '인천', '대구', '대전', '광주']
  # 마지막 인덱스 -1 까지만 출력
  cities[-1:-5:-2]
  # 수원부터 시작해서 두칸씩
  # ['수원', '광주']
  ~~~

  ### 연산
  * 덧셈 연산
  * 곱셈 연산
  * in 연산: 포함 여부
  ~~~
  color1 = ['red', 'blue', 'green']
  color2 = ['orange', 'black', ' white']
  print(color1+color2)
  # ['red', 'blue', 'green', 'orange', 'black', ' white']
  len(color1) 
  # 3
  ~~~

  ### 리스트 추가 및 삭제
  * append():리스트 마지막 인덱스에 값 추가
  * extend(): 기존 리스트에 새로운 리스트 추가
  * insert(): 리스트의 특정 위치에 값 추가
  * remove(): 리스트의 특정 값 삭제

  ### 패킹과 언패킹
  * 패킹: 한 변수에 여러 개의 데이터를 넣는 것
  * 언패킹: 한 변수의 데이터를 각각의 변수로 할당
  ~~~
  t = [1,2,3]
  a,b,c = t
  print(t,a,b,c)
  # [1,2,3] 1 2 3
  ~~~
  
  ### 이차원 리스트
  * 리스트 안에 리스트를 만들어 행렬 생성
  ~~~
  kor_score = [49,79,20,100,80]
  math_score = [43,59,85,30,90]
  eng_score = [49,79,48,60,100]
  midterm_score = [kor_score,math_score, eng_score]
  midterm_score
  # [[49,79,20,100,80], [43,59,85,30,90], [49,79,48,60,100]]
  ~~~
## Function
* 어떤 일을 수행하는 코드 덩어리
* 반복적인 수행을 한 번만 작성해놓고 필요할 때마다 호출
* 코드를 논리적인 단위로 분리
* 캡슐화: 인퍼페이스만 알면 타인의 코드 사용
  
  ### 함수 선언
 ~~~
 def 함수 이름 (parameter #1,...):
  수행문 1(statements)
  수행문 2(statements)
  return <반환값>
 ~~~

 * def: 'definition'의 줄임말로 함수의 정의를 시작한다는 의미
 * 함수 이름: 일반적으로 다음과 같은 규칙 적용
    * 소문자로 입력
    * 띄어쓰기를 할 경우에는 _기호 사용
    * 작업을 나타내기 위해 동사와 명사 함께 사용
    * 외부에 공개하는 함수일 경우 줄임말을 사용하지 않고 짧고 명료한 이름 사용
 * 매개변수(parameter): 입력값으로 사용하는 변수(1개 이상의 값 적을 수 있음)
 * 수행문: 반드시 들여쓰기한 후 코드 입력

 ### 함수 실행 순서
 ~~~
 def calculate_rectangle_area(x,y):
  return x * y
 x = 10
 y = 20
 result = calculate_rectangle_area(x,y)
 print("사각형의 넓이: ", result)
 #사각형의 넓이: 200
 ~~~
 * x,y에 각각 10,20 값이 할당됨
 * calculate_rectangle_area(x,y) 함수 호출하고, x,y에 할당된 값이 함수의 입력값이 되고 return x * y에 의해 반환값 200이 반환한 값이 result에 저장됨

 ### 프로그래밍의 함수와 수학의 함수
 : 매우 비슷함
* f(x) = 2x + 7, g(x) = x^2이고 x = 2일 때 f(x) + g(x) = f(g(x)) = g(f(x))의 값은?
~~~
def f(x):
 return 2 * x + 7
def g(x):
 return x ** 2
x = 2
result = f(x) + g(x) = f(g(x)) = g(f(x))
print result
~~~

 ### parameter vs argument
 * parameter: 함수의 입력 값 인터페이스
  ~~~
  def f(x):
   return 2 * x + 7
  ~~~
 * argument: 실제 파라미터에 대입된 값
  ~~~
  print(f(2))
  # 11
  ~~~

 ### 함수의 형태
 : 파라미터의 유무, 반환 값 유무에 따라 다름
 | 매개변수 유무/반환값 유무 | 매개변수 없음 | 매개변수 있음 |
 |---|---|---|
 |반환값 없음|함수 내부 명령문만 수행|매개변수를 사용하여 명령문만 수행|
 |반환값 있음|매개변수 없이 명령문을 수행한 후 결과값 반환|매개변수를 사용하여 명령문을 수행한 후 결과값 반환|

~~~
# 파라미터 O, 반환값 O
def a(x):
 return x * x
x = 2
print(a(x))
# 4(반환값)
~~~

~~~
# 파라미터 O, 반환값 X
def a(x):
 print(x ** x)
x = 2
print(a(x))
# 4
# None > a(x)값이 return되지 않아서 아무것도 없어서 null값이 출력
~~~

~~~
# 파라미터 X, 반환값 X
def a():
 x = 2
 print(x ** x)
x = 2
print(a(x))
# 4
# None
~~~

~~~
# 파라미터 X, 반환값 O
def a():
 x = 2
 return x ** x
x = 2
print(a(x))
# 4 > return값이 있기 때문에 4로 return
~~~

## console in/out
### Command Line Interface
* Graphic User Interface(GUI)와 달리 텍스트를 사용하여 컴퓨터에 명령을 입력하는 인터페이스 체계
* Windows - CMD window, Windows Terminal
* Mac, Linux - Terminal

### 콘솔창 입출력(1) - input
* input() 함수: 콘솔창에서 입력을 받는 함수
* 값을 입력받으면 그 값의 자료형은 문자형이 됨
~~~
print ("Enter your name:")
somebody = input()
print("Hi, somebody, "How are you today?")
# Enter your name:
# chaewon kim
# Hi, chaewon kim, "How are you today?
~~~

### 콘솔창 입출력(2) - print
* 콤마(,) 사용할 경우 print문 연결됨
~~~
print("Hello World!","Hello Again!!!")
# Hello World! Hello Again!!!
# 실행 시 두 문장이 연결돼서 출력
~~~

* 숫자 입력받기 - 입력 시 바로 형 변환
~~~
temperature = float(input("온도를 입력하세요:"))
print(temperature)
# 온도를 입력하세요: 102
# 102.0
~~~

### print formatting
* 기본적인 출력 외에 출력 형식 지정 가능
* 일반적으로 % format과 str.format() 함수를 사용
~~~
print("%s %s" % ("Hello", "World"))
print("{} {}".format("Hello", "World"))
print("%d %d" % (1,2))
print("{}          {}".format(1,2))
# Hello World
# Hello World
# 1 2
# 1          2
~~~
 #### %-format
  ~~~
  print("I eat %d apples." % 3)
  print("I eat %s apples." % "five")
  number = 3; day = "three"
  print("I eat %d apples. I was sick for %s days." % (number, day))
  print("Product: %s, Price per unit: %f." % ("Apple", 5.243))
  ~~~
  ~~~
  print("Art: %5d, Price per Uit: %8.2f" % (453, 59.058))
  # %5d: 5칸 띄워라
  # %8.2f: 8칸 띄우고 소수점 둘째자리까지
  ~~~

#### str.format() 함수
"~~~{datatype}~~~".format(argument)
~~~
age = 36; name ='Sungchul Choi'
print("I'm {0} years old.".format(age))
print("My name is {0} and {1} years old."format(name, age))
print("Product: {0}, Price per unit: {1:.3f}.".format(Apple, 5.243))
~~~

#### padding
: 여유 공간을 지정하여 글자배열 + 소수점 자릿수 맞추기
* f-string: 최근에 가장 흔한 기법, 기본적으로 왼쪽 정렬
~~~
name = "Sungchul"
age = 41
print(f"Hello,{name}. You are {age}.")
print(f'{name:20}')
print(f'{name:>20}') # 우로 정렬
print(f'{name:*<20}') # 좌로 정렬하고 나머지칸은 뱔표로
print(f'{name:*>20}') # 우로 정렬하고 나머지칸은 별표로
print(f'{name:*^20}') # 가운데로 정렬하고 나머지칸은 별표로
~~~

## Condition
### 조건문
* 조건에 따라 특정한 동작을 하게 하는 명령어
* 조건을 나타내는 기준과 실행해야 할 명령으로 구성됨
* 조건의 참 거짓에 따라 실행해야 할 명령이 수행되거나 수행되지 않음
* 파이썬에서는 if, else, elif 등의 예약어 사용

### if-else문 문법
~~~
if <조건>:
 <수행명령1-1>
 <수행명령1-2>
else:
 <수행명령2-1>
 수행명령2-2>
~~~
1. if 뒤에는 참과 거짓을 판단할 수 있는 조건문이 와야 하고, 조건문이 끝나면 반드시 콜론(:)
2. 들여쓰기를 사용하여 해당 조건이 참일 경우 수행할 명령 작성
3. 조건 불일치 시 else문 실행(조건에 해당하지 않는 경우 처리해야 할 명령이 있다면)

~~~
print("Tell me your age?")
myage = int(input())
if myage < 30:
 print("Welcome to the Club.")
else:
 print("Get out of here!!!")
~~~

### 조건 판단 방법
* if 다음에 조건을 표기하여 참 또는 거짓 판단
* 참/거짓의 구분을 위해 비교 연산자 활용

비교연산자 | 비교상태 | 설명
---|---|---
x < y|~보다 작음|x가 y보다 작은지 검사
x > y|~보다 큼|x가 y보다 큰지 검사
x == y|같음|x가 y보다 같은지 검사
x is y|같음|x가 y보다 같은지 검사(메모리주소)
x!= y|같지 않음|x가 y보다 다른지 검사
x is not y|같지 않음|x가 y보다 다른지 검사(메모리주소)
x >= y|크거나 같음|x가 y보다 이상인지 검사
x <= y|작거나 같음|x가 y보다 이하인지 검사

~~~
a = 5
b = 5
a == b
# True

a = 1050
b = 1050
a == b
#True

a = 10
b = 10
a = 1050
b = 1050
a is b
# False (할당된 메모리 주소가 다르기 때문에)
~~~
* -5~256까지는 변하지 않는 메모리 주소에 값을 할당

### 조건 참/거짓의 구분
* 숫자형의 경우: 수학에서의 참/거짓과 동일
* 컴퓨터는 존재하면 참,없으면 거짓이라고 판단
~~~
if 1:
 print "True"
else:
 print "False"
~~~

### 논리 키워드 사용: and, or, not
~~~
a = 8, b = 5 일 때
if a == 8 and b ==4 # False
if a > 7 or b > 7 # True
if not (a > 7) # False
~~~

### 삼항 연산자
조건문을 사용하여 참일 경우와 거짓일 경우의 결과를 한 줄에 표현
~~~
value = 12
is_even = True if value % 2 == 0 else False
print(is_even)
# True
~~~

### if-elif-else 문
~~~
score = int(input("Enter your score: "))

if score >= 90: grade 'A'
if score >= 80: grade 'B'
if score >= 70: grade 'C'
if score >= 60: grade 'D'
else: grade = 'F'

print(grade)
~~~

## loop
### 반목문
* 정해진 동작을 반복적으로 수행하게 하는 명령문
* 반복 시작 조건, 종료 조건, 수행 명령으로 구성
* 반복 구문은 들여쓰기와 block으로 구분

### for-loop
* 기본적인 반복문: 반복 범위를 지정하여 반복문 수행
~~~
for i in [1,2,3,4,5]:
 print(i, "Hello")
~~~
* range() 사용
* for 변수 in range(시작 번호, 마지막 번호, 증가값)
~~~
for i in range(0,5)
 print("Hello")
~~~
* range()는 마지막 숫자 앞까지 리스트를 만들어줌
* range(0,5) = [0,1,2,3,4] = range(5)는 같은 의미

### 알아두면 상식
* 반목문 변수명: 임시적인 반복 변수는 대부분 i,j,k
* 0부터 시작하는 반복문
* 무한 loop: 반복 명령이 끝나지 않는 프로그램 오류

### for문의 다양한 반복문 조건 표현
* 문자열을 한 자씩 리스트로 처리 - 시퀀스형 자료
~~~
for i in "abcdefg":
 print(i)
~~~
* 각각의 문자열 리스트로 처리
~~~
for i in ["americano", "latte", "frafuchino"]:
 print(i)
~~~
* 간격을 두고 세기
~~~
for i in range(1,10,2): # 1부터 10까지 2씩 증가시키면서 반복문 수행
 print(i)
~~~
* 역순으로 반복문 수행
~~~
for i in range(10,1,-1): # 10부터 1까지 -1씩 감소시키면서 반복문 수행
 print(i)
~~~

### while문
* 조건이 만족하는 동안 반복 명령문 수행
* for문은 while문으로 변환 가능
~~~
i = 1 # i 변수에 1 할당
while i < 10: # i가 5가 되면 종료
 print(i) # 조건을 만족할 때 i 출력
 i +=1 # i에 1 더하는 것 반복하다가 10이 되면 반복 종료
~~~

### 반복의 제어 - break, continue
#### break
특정 조건에서 반복 종료
~~~
for i in range(10):
 if i == 5: break #i가 5가 되면 반복 종료 
 print(i)
print("EOP")
~~~
#### continue
특정 조건에서 남은 반복 명령 skip
~~~
for i in range(10):
 if i == 5: continue #i가 5가 되면 i 출력하지 않음
 print(i)
print("EOP")
~~~
#### else
반복 조건 만족하지 않을 경우 반복 종료 시 1회 수행
~~~
for i in range(10):
 print(i,)
else:
 print("EOP")
~~~
