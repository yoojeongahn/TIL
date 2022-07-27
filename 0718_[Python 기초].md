# [Python 기초]

.

프로그래밍 언어

- 컴퓨터는 기계어로 소통(0과 1, 2진법)
- 기계어로 코딩하기엔 쉽지 않기에 사람과 기계 모두 이해할 수 있는 언어
- 특징: 사람이 이해할 수 있음. 기본적인 규칙과 문법이 존재

.

소스 코드: 프로그래밍 언어로 작성된 프로그램

번역기(interpreter): 사람이 작성한 소스코드를 컴퓨터가 이해할 수 있는 기계어로 번역

.

파이썬의 특징

- 알고리즘 코딩 테스트에 유리(변칙적인 유형에 대응이 쉽다)
- 사람친화적 언어(하이레벨 언어) vs C++(조금 더 기계적, 더 빠름)
- AI, 데이터 분석, 웹 프로그래밍, 업무 자동화 등 파이썬 활용 분야 증가
- Easy to learn(직관적, 문법이 간결)
- 인터프리터 언어- 소스 코드를 기계어로 변환할 때 통역하듯이 1줄씩 변환
- 객체 지향 언어

.

파이썬 개발 환경

IDE - 통합 개발 환경(VS, 파이참) Jupyter - 문법학습을 위한 최적의도구 IDLE

.

자료형 분류

- 참/거짓(불린형, Boolean Type) - 논리연산자 not, and, or 순으로 우선순위가 높음

- 수치형(Numeric Type) - int(정수형), 진수 표현, float(실수형) #부동 소수점 유의

- 문자열(String Type)
  
  중첩 따옴표(작은따옴표가 들어 있는 겨우는 큰따옴표로 문자열 생성)
  
  삼중 따옴표(복합적으로 사용할 경우)
  
  역슬래시 \n 줄바꿈 \t 탭 \o 널(null) \\ (\) \’ 단일인용부호(’) \”이중인용부호(”)
  
  문자열 덧셈 = 문자열 연결
  
  문자열 순회 a = '123' for i in a: print(i)
  
  String interpolation(문자열을 변수를 활용)
  
  print(’hello, %s’ % name) print(’hello, {}! 성적은 {}. format(name, score))
  
  print(f’hello, {name}! 성적은 {score}’)

- None

.

컨테이너(자료 구조)

- 여러 개의 값(데이터)을 담을 있는 것(객체)으로, 서로 다른 자료형을 저장할 수 있음

- 순서가 있는/없는 데이터로 분류
  
  시퀀스형 - list/tuple/range/str 비시쿼스형 - set/dictionary (튜플/레인지 불변형)
  
  list - 여러 개의 값을 순서가 있는 구조로 저장
  
     파이썬에서는 어떠한 자료형도 저장 가능, 리스트도 넣을 수 있음
  
     순서가 있는 스퀀스로 인덱스를 통해 접근 가능
  
  tuple - 불변 자료형이지만 인덱스 접근 가능 a = (1, 2, 3, ) tuple_a = (1,)
  
  range - range(n) range(n,m) range(n,m,s)
  
     슬라이싱 연산자, 뒤 인덱스에 해당 문자는 미포함
  
     print([1, 2, 3, 5][1:4]) #[2, 3, 5] print([1, 2, 3, 5][0:4:2]) #[1, 3]
  
  set - 중복되는 요소가 없이, 순서에 상관없는 데이터들의 묶음
  
     print({1, 2, 3}) print(len(set(list)))- 중복 제거
  
     합집합 print(A | B) 교집합 print(A & B) 차집합 print(A - B)
  
  dictionary - key-value 쌍으로 이뤄진 자료형, key는 변경 불가능한 데이터
  
     dict = {’a: ‘apple’, ‘b’: ‘banana’, list=[1, 2, 3]}
  
  .

형 변환 - 파이썬에서 데이터 형태는 서로 변환할 수 있음(암시적/명시적)

  암시적 : bool, numeric type print(True+3) #4 print(3+5.0) #8.0

  명시적 : int( str, float → int) float( str, int → float) str( int float list tuple dict → str)

  input( ) - 문자열(str)로 저장됌. map(int, input( ).split( ))
