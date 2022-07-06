# 프로세스
## 정의
- 실행중인 프로그램(running program, program in execution)
- 프로세스의 현재 상태는 Program Counter의 값에 의해 결정된다.

## 구조
![process_layout](https://github.com/prograsshopper/learning-for-interview/blob/main/OperatingSystem/images/process/process_layout.png?raw=true)
- 프로세스의 메모리 레이아웃은 아래 그림상에서 확인할 수 있다시피 다양한 섹션으로 분류되며 아래의 섹션을 포함한다.
	- Test Section: 실행가능한 코드
	- Data Section: 글로벌 변수
	- Heap Section: 프로그램이 실행되는 시간동안 동적으로 할당되는 메모리
	- Stack Section: 함수가 발생할때의 일시적인 데이터 저장소 (함수 파라미터, 리턴 주소값, 지역 변수 등)

## 상태
![process_states](https://github.com/prograsshopper/learning-for-interview/blob/main/OperatingSystem/images/process/process_states.png?raw=true)
- New: 프로세스 생성
- Running: Instruction이 실행중인 상태
- Waiting: 이벤트 발생을 기다리는 중인 상태
- Ready: 프로세서가 할당해주길 기다리는 상태
- Terminated: 프로새스가 실행을 마친 상태

## PCB(Process Control Block)
- 각 프로세스는 PCB를 통해 OS로부터 표현된다. Task control block이라고도 한다. 
- PCB가 특정 프로세스에 관해 포함하고 있는 정보중엔 다음과 같은 것들이 있다.
    - Process State
    - Program counter: 이 프로세스를 위해 수행되어야하는 다음 instruction의 주소를 암시한다.
    - CPU registers, CPU-scheduling information. Memory-management information, Accounting information, I/O status information

## 문맥 교환(Context Switch)
![context_switch](https://github.com/prograsshopper/learning-for-interview/blob/main/OperatingSystem/images/process/context_switch.png?raw=true)
- CPU코어상에서 다른 프로세스로 변경하는 것은 현재 실행중인 프로세스의 상태를 저장하고, 다른 프로세스의 상태를 복구하는 것을 필요로 한다. 이 작업을 문맥 교환이라고 한다.
- 컨텍스트 스위치가 발생하면 커널은 오래된 프로세스의 컨텍스를 PCB에 저장하고 새 프로세스의 저장된 컨텍스트를 불러내어 실행할 수 있도록 스케쥴한다. 
