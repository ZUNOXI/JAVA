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

* 반목문 - do while

* 반복문 - for~each



* break : 반복중인 루프를 벗어나기 위해 사용 / continue : 아랫부분의 문장들을 무시하고, 반복중인 루프를 계속 처리한다.





- 1차원 Array(배열)



* 자바에서는 배열도 객체이다. 

* arraycopy()메소드 사용하여 배열 복사 가능



- 다차원 Array(배열)



* 2차원 Array는 행과 열이 각각의 객체로 생성되므로 행의 생성과 열의 생성을 따로 분리할 수 있다. 그러므로 각각 다른 2차원 배열 생성이 가능하다.



- Operations



* 클래스내에 객체가 가져야 할 기능 정의시에 Operation(메서드)를 사용한다.





4. class design





* JVM Memory 구조

- Java 언어는 메모리 관리를 개발자에게 위임하지 않고, GC(Garbage Collection)라는 쓰레드를 생성하여 사용하지 않는 객체를 제거 하도록 설계하였다. Java 개발자는 메모리 관리를 고민할 필요 없이 객체를 생성만 하여 사용하면 된다. 

- Java의 VM은 구현한 벤더마다, 버전마다 메모리 관리 기법이 다르고, GC의 관리 방법도 다르다. 그러나 대략적으로는 아래와 같은 모습을 가진다.





- classLoader : 하드디스크에 있는 번역된 class 파일을 메모리로 읽어온다.

- classarea(Method area) : 메모리로 읽어온 클래스의 정보를 기억하는 곳

- heap : 클래스의 객체를 생성하여 기억하는 곳

- stack : 메서드 수행 시마다 프레임이 할당되어 메서드 수행에 필요한 변수나, 중간 결과 값을 임시기억 하는 곳, 메서드 종료 시 할당 메모리 자동 제거



* Garbage Collection : Heap영역(class영역 포함)에 생성된 객체들의 메모리 관리를 담당하는 프로그램, 더 이상 사용되지 않은 객체들을 점검하여 제거한다. 자동적인 실행, CPU가 한가하거나 메모리가 부족할 때 JVM에 의해서 실행된다. 

- System.gc()를 호출하여 실행을 유도할 수는 있으나 바로 수행된다는 보장은 없다.

- JVM에 따라 다양하게 구현, 실행되며 성능에 영향을 주기 때문에 Java version에 따라 더 좋은 성능의 Garbage Collection 기법 사용한다.





* Constructor(생성자)

- 생성자는 객체 생성시 자동 호출되는 특별한 기능으로 주로 객체 초기화 작업을 수행한다.

- Default Constructor(기본생성자) : class constructor가 하나도 정의되지 않았을 경우 컴파일 시 컴파일러에 의해 삽입된다.

[Member m = new Member();  이 코드가 에러가 나지 않으려면 클래스 안에 public Member(){}와 같은 기본생성자도 함꼐 정의를 해주는것이 바람직하다.

- Constructor Overloading : 아규먼트가 다른 다양한 형태로 생성자를 정의하여 다양한 형태로 객체를 생성할 수도 있도록 함으로서 객체의 생성을 편리하게 한다.



* This variable

- 객체 생성 시 그 객체의 레퍼런스를 저장하기 위한 this 레퍼런스가 자동 생성된다. 메서드(생성자) 수행 시에 현재 수행중인 객체의 레퍼런스 정보를 가지고 있는 this를 사용할 수 있다. 메서드(생성자)내에서 변수를 사용할 경우, VM은 로컬에 그 변수가 있는지 확인하고 없을 경우 자동으로 this가 레퍼런스하고 있는 객체를 접근하여 변수를 확인하고 있을 경우 사용한다. 





5. Method



* method는 객체가 가져야 할 기능을 구현한다.



* Variable LifeCycle

- Member variable : class 내에 정의되는 variable이다/ 메모리 영역 중 heap에 생성된다/ static(class) variable : class가 메모리에 로딩시에 메모리 할당이 이루어지며, 자동초기화 된다. class 제거시 제거된다./ instance variable : 객체 생성시 자동으로 초기화 되며, 객체 제거시 제거된다.

- default 초기화 : 정수형 : 0 / 실수형 : 0.0 / boolean : false / char : \u0000 / reference type : null

- local variable : method나 constructor{} 내에 정의되는 variable이다. / 메모리 영역 중 stack에 생성한다. / method나 constructor 호출 시에 생성되었다가 수행 종료 시 사라진다. / 자동으로 초기화 되지 않기 때문에 반드시 초기화 하여 사용해야 한다.





6. Access Modifier



* 클래스 정의 시 접근 단계를 정의하기 위하여 Access Modifier(접근제한자)를 이용한다. 접근 제한자는 다음과 같이 4단계가 있다.

- private : 같은 클래스 내에서만 사용할 수 있다.

- (default) : 아무것도 정의하지 않았을 경우, 같은 클래스, 같은 패키지 내에서만 사용할 수 있다.

- protected : 패키지가 다르면 사용할 수 없으나, 상속받았다면 사용할 수 있다.

- public : 어디서나 사용할 수 있다. 



* Usage Modifier

- static : 객체 생성없이 사용하고자 할 경우에 사용합니다.

- final : 변경할 수 없음을 의미합니다.

- abstract : 미완성임을 의마합니다.





7. Encapsulation

* 클래스 설계 시 데이터와 기능을 클래스라는 틀에 넣어서 설계하고, 중요한 데이터나 복잡한 구현을 숨기고, 사용에 꼭 필요한 기능만을 공개하여 정의하는 기법 

- 중요하거나 상세한 구현은 숨긴다.(private 이용)

- 접근에 필요한 기능만을 public 하게 공개한다.

- setter, getter를 통해 접근, 제어한다. (attribute : private, method : public)

- 중요한 데이터의 은닉과 보호

- 복잡하고 상세한 구현을 숨김

- 캡슐화를 적용하게 되면, 필요한 기능만 공개되어 있기때문에 사용이 편리해지고, 코드의 유지보수를 용이하게 만든다.





8. API(Application Programming Interface)

*객체지향에서 class 단위로 미리 구현되어 제공되는 프로그램은 API라 한다. class 단위의 library이다.

* API 종류

- 표준 API : Java와 함꼐 구현되어 제공되는 프로그램

- 벤더 API : 기업에서(프로젝트에 사용하기 위해) 미리 작성해 놓은 프로그램

- 사용자정의 API : 개발자가 미리 작성하여 사용하는 프로그램



*package

- java 에서는 작성된 많은 class들을 분리하여 관리하기 위해 package를 사용하낟. 파일관리의 폴더와 유사하다. 반드시 class 파일 내에 자신 첫 라인에 package를 명시하고 있어야 하며, 한번만 정의해서 사용할 수 있다.





