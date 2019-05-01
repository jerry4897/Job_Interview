# Job_Interview

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
