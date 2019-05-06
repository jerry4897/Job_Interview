# Job_Interview

### OOP의 특징
#### 1. 추상화
      사물의 공통된 특징(추상적 특징)을 파악해서 하나의 개념으로 만드는 수단. (ex, 현대차와 벤츠 -> 자동차)
#### 2. 캡슐화
      설계원리로서 높은 응집도와 낮은 결합도를 유지할 수 있도록 한다.(약한 결함)
      정보은닉을 통해 위의 조건을 만족 시킨다.(필요가 없는 정보는 외부에서의 접근을 차단시킨다.)
#### 3. 상속
#### 4. 다형성
      오버로딩(컴파일 시점)
      오버라이딩(런타임 시점)

### Program vs Process
#### Program
      - 보조 기억장치(HDD,SSD)에 존재하는 코드와 데이터의 묶음. (정적인 개념)
#### Process
      - 메모리에 적재되고 CPU를 할당받아 실행중인 프로그램의 인스턴스(독립된 개체). (동적인 개념)
      
### Process vs Thread
#### Process
      - 프로세스는 최소 1개의 스레드를 갖고 있다.
      - 각각의 프로세스는 독립된 메모리 영역(Code, Stack, Heap, Data)을 갖으며 별도의 주소 공간에서 실행된다.
      - 다른 프로세스의 변수나 자료구조에 접근할 수 없다. (IPC 사용시 접근 가능. Inter-Process Communication)
### Thread
      - 프로세스 내에서 실행되는 여러 흐름의 단위.
      - 프로세스 내에서 각각의 독립된 Register, Stack을 할당받고 (Code, Heap, Data)는 공유한다. (주소공간이나 자원들을 공유)
      
### Multi Process vs Multi Thread
#### Multi Processing
      - 하나의 응용 프로그램을 여러 개의 프로세스로 구성하여 각 프로세스가 하나의 작업을 처리하도록 하는 것.
      - 장점 : 하나의 프로세스가 죽어도 다른 프로세스가 일을 처리할 수 있다.
      - 단점 : Context Switching에 의한 오버헤드. 프로세스 간의 복잡한 통신 기법(IPC)
#### Multi Threading
      - 
               

### RTOS ( Real Time Operating System )
  - 실시간 응용 프로그램을 위해 개발된 운영체제.
  - 운영체제의 기능중 CPU시간 관리 부분에 에 초점을 맞추어 설계되었다.
  - 프로그래머가 프로세스 우선 순위에 더 많은 제어가 가능.
  - 시스템 코드의 Critical Section을 최소화하여, 응용 프로그램의 처리 요청을 정해진 시간 안에 처리 해줄 수 있다.
  
### MVC ( Model, View, Controller )
  - Model       : 애플리케이션의 데이터, 비즈니르 로직.
  - View        : 텍스트, 체크박스 같은 사용자 인터페이스.
  - Controller  : 데이터와 비즈니스 로직 사이의 상호동작 관리.
  - 사용자 인터페이스와 비즈니스 로직을 분리하여 서로 영향 없이 쉽게 고칠 수 있는 어플리케이션 개발이 가능하다.
  
### SIC - SIC/XE 머신
| | SIC | SIC/XE |
|:-----:|:-----:|:----:|
|메모리|1Byte = 8bit, 1Word = 3Byte|동일|
|주소|15bit|20bit|
|실수|표현 불가|표현 가능|
|명령어|포맷 없음|명령어 포맷 추가됨.|
|주소계산방식|Indexed Addressing + Direct Addressing|Relative Addressing + Direct Addressing|

### Malloc vs New
#### malloc / free
  - C, C++ 사용 가능
  - stdlib.h 파일에 포함되어 있다. 따라서 사용시 함수 콜이 발생한다.
  - Heap 메모리에 할당
  - 타입의 크기를 정확히 알아야 한다. (sizeof() 사용.)
  - malloc 함수의 타입은 void*로 사용 시 알맞게 type casting 해야 한다.
  - 객체에는 사용 불가.
  - realloc을 통한 재할당이 가능하다.
#### new / delete
  - C++ 사용 가능
  - 라이브러리가 아닌 C++의 키워드이기 때문에 함수 콜 발생 X.
  - Heap 메모리에 할당
  - 메모리 할당과 동시에 초기값 지정(초기화) 가능.
  - 생성자를 자동으로 호출한다. (생성자는 객체를 자동으로 초기화 시켜준다.)
  
        재할당이 빈번히 일어날 경우 malloc을 이용하여 realloc을 쓰는 형태가 더 효율적이다. 
        new의 경우 '할당 -> 복사 -> 해제'하여야 한다.

#### Realloc과 메모리 접근
        realloc은 동적으로 할당한 메모리를 재할당하는 함수이다. 
        기존에 malloc을 이용하여 10개 int 메모리를 동적할당 하였고 시작 메모리가 10이라고 가정한다.
        이 메모리를 realloc하여 20개의 int 메모리를 할당할 경우 기존의 메모리 주소에서 추가로 10의 공간이 남아있다면 
        시작 메모리는 그대로 10이지만 그렇지 않을 경우 시작 메모리는 새롭게 할당된다.
### Stack vs Heap
#### Stack
  - 프로그램이 사용하는 메모리 영역.
  - 지역변수와 같이 임시적인 자료나 함수(매개 변수)에서 자주 사용. 초기화 되지 않은 클래스도 해당.
  - Linux에선 메모리상 높은 곳에서 낮은 곳으로 쌓이고, Window에서는 낮은 곳에서 높은 곳으로 쌓인다.
  - 주로 컴파일 시에 스택의 크기가 결정된다.
#### Heap
  - 프로그램에서 사용자가 직접 할당하고 헤제하는 메모리 영역.
  - 동적할당시 사용된다.
  - 스택과 반대로 메모리가 쌓인다.
  - 런타임 시간에 크기가 결정된다.
  - 상대적으로 스택보다 큰 메모리 공간을 갖는다.

### Vector
      - 런타임에 크기가 결정되는 배열과 비슷한 자료구조. (배열은 컴파일 타임에 크기 결정)
      - 저장할 데이터 수가 가변적일 경우 효율적이다.(push_back)
      - 데이터를 중간에 삽입 삭제 하는 경우 비효율적이다.
      - 랜덤 접근이 가능하다.
      - 데이터를 순차적으로 저장하기 때문에 많은 데이터를 저장할 경우 검색이 빠르지 않다.(검색을 자주할 경우 set, map이 유리)
      
### List
      - 랜덤 접근이 불가능한 단점이 있지만 중간에 요소를 삽입, 삭제하기에 유용하다.
      
### Static, Extern
#### static
      정적 변수.(정적 데이터 영역에 할당)
      자동으로 0으로 초기화.
      내부 정적 변수 : 함수 내부의 변수가 static으로 생성될 경우, 함수가 종료되어도 기존 값이 유지된다.(프로그램 실행시간 동안 유지)
      외부 정적 변수 : 해당 파일 내부에서 전역변수로 쓰이지만, 외부 파일에서는 참조 불가능.
#### extern
      파일 외부에서 참조가 가능한 전역변수이다. 프로그램 전체에서 사용이 가능하다.
      자동으로 0으로 초기화.
      정적 데이터 영역에 할당된다.
      
### 프림 vs 크루스칼
#### 프림
      시작점 기준으로 현재 집단에서 가장 가까운 노드를 추가시키면서 MST를 만든다.
#### 크루스칼
      전체 간선 중에서 가장 weight가 작은 간선들을 추가시키면서 MST를 만든다.(간선을 정렬해야 한다.)
그래프가 dense한 경우 프림이, 반대의 경우 크루스칼이 유리.

### Staic
      static 메서드는 정적메서드로 코드가 읽히기 전에 미리 메모리상에 자리를 잡고 있다.(생성자 호출전에 미리 값이 결정)
