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
  * 나눗셈 연산자: \\
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
  * 언패킹: 한 변수의 데이터를 각각의 변수로 반환
  ~~~
  t = [1,2,3[
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
