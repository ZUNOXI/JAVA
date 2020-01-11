분산프로그래밍 지원 : 1990년대에 설계된 언어로 네트워크를 이용한 프로그래밍을 지원하고, 원격 접속을 위한 다양한 기술셋을 가지고 있다.



멀티스레드 : 사용되는 운영체제에 따라 멀티 스레드의 구현이 다르고, 처리 방식도 달라서 문제가 되었던 부분을 Java는 Thread API를 제공함으로써 운영체제에 종속적이지 않는 독립적인 설계와 JVM에 의해 스케쥴링이 되도록  구현됨





- 자바를 만든 Sun Micro Systems는 2009년에 Oracle에 합병되었다. 



- JavaSE SDK : Java를 컴파일하고, 실행할 수 있는 환경, 디버그 환경을 제공해주는 툴이다.



JRE는 Java의 실행환경만을 가지고 있기때문에 개발을 위한 컴파일러를 갖고 있지 않다. 반드시 JDK를 다운로드하여 개발환경과 실행환경(JRE)이 모두 포함되어 있는 toolkit을 다운로드 해야한다.



- 자바는 객체르 설계하기 위한 클래스 단위로 작성된다. 이때 VM이 실행하는 범위는 오직 main()만을 실행한다.

모든 명령문은 ;으로 종료를 표시한다.



자바의 동작원리는 java파일이 javac라는 컴파일러를 통해 바이트코드로 컴파일이 되어 클래스 파일이 생성된다. 이를 클래스로더가 JVM에 태운다. 이후 JVM은 기계어로 번역하여 컴퓨터와 의사소통한다.



- 컴파일러는 주어진 java 코드의 문법을 체크하고, 코드를 분석하여 생략된 부분의 코드(생성자, java.lang 클래스 경로, Object의 상속 등)를 삽입하고, 기본 상수연산 등을 수행하고 코드의 실행성능을 높이기 위해 최적화 작업을 수행한다. 



- JVM은 컴파일된 bytecode를 읽어서 한문장씩 OS가 실행 가능한 코드로 번역하여 최적화 작업을 함께 실행한다.





* JAVA Statement & Data Type



- 자바 문법



- java 문장은 ; 로 종료되어야 한다.

- 문장들의 묶음은 {...}로 처리한다.

- whitespace : 문장을 깔끔하게 하기 위해 공백을 마음대로 사용할 수 있다.

- 한줄 주석처리는 // , 여러줄 주석처리는 /*  */ , 문서화 주석처리 /** */



* identifiers(식별자)

- 클래스내의 식별자(클래스명, 변수명, 상수명, 메서드 명)을 명명하는 방법이다.

- 유니코드 문자, _, $으로 시작할 수 있으며, 두 번째 글자부터는 숫자를 허용한다.(첫번째 글자로 숫자는 x) 

- java는 대소문자를 구별하며, 길이에 제한이 없다.

- keyword를 사용할 수 없다.



* 클래스 작성시 관습적으로 지켜지는 규칙들

(약속을 통해 코드의 가독성 증가, 유지보수성 증가, 확장성 등을 증가시킨다.)

- class 이름은 첫글자를 대문자로 시작하고, 나머지 글자를 소문자로 명명한다.

- method, variable 이름은 모두 소문자로 한다.

- constant(primitive) 이름은 모두 대문자로 한다.

- 두 단어의 합성으로 이름이 명명될 경우, class, method, variable 명은 두번째 단어의 첫글자를 대문자로 하고, constant는 _ 을 이용하여 두 단어를 붙이게 된다. 



* Java Keyword

Java 문법에서 사용 용도가 정의된 키워드(예약어)이다. 용도가 혼동되기 때문에 아래 키워드들을 식별자로 사용해서는 안된다. 

"abstract / continue / goto / package / synchronized / assert / default / if / private / this / boolean / do / implements / protected / throws / throw / break / double / import / public / byte / else / instanceof / return / transient / case / extends / int / short / try / catch / final / interface / static / void / char / finally / long / strictfp / volatile / class / float / native / super / while / const / for / new / switch "





- 자바 데이터 타입



* Primitive Data Type : 기본적(일반적)인 값을 기억하는 변수의 type

- 논리형 / boolean : true, false

- 문자형 / char : 16비트 유니코드

- 정수형 / byte : 8비트 / short : 16비트 / int : 32비트 / long : 64비트

- 실수형 / float : 32비트 / double : 64비트



* Casting 

- 작은 크기의 타입은 큰 크기의 타입으로 자동 형변환 된다. 

- 정수형은 실수형으로 자동형변환 된다.

- 큰 크기의 타입이 작은 타입으로 변경할 경우, 실수형이 정수형으로 타입변경할 경우는 아래와 같이 변경

[ float fvar = 100; long var = (long)fvar;    //   int a = (int) 3.4;   // char c = (char) 65; ]

- 여러 타입 연산 시 가장 큰 타입으로 결과값을 갖는다.

- byte, short, char 타입의 이항여산 결과는 int 이다.



* Reference Data Type

- 객체의 참조(Reference) 값을 기억하는 변수

- class, interface, 배열등 

[ Member mem;  //  int[]arr = new int[10]; ]





- 조건문



* 조건문 - if

* 조건문

- switch : switch에서 조건값(expr)은 반드시 정수형(int, byte, short, char)이어야 한다.

- case에서 같은 값을 찾아서 실행하고 만약 값이 없다면 default를 실행시킨다.

* 조건문 - 3항 연산식

[ type 변수 = (조건식)? 값1: 값2; ]





- 반복문



* 반복문 - for

* 반복문 - while
