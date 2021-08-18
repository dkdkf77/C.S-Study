# Process Management

프로세스(process)

작업 / 프로그램 

- 실행 할 프로그램 + 데이터
- 컴퓨터 시스템에 실행 요청 전의 상태

프로세스

- 실행을 위해 시스템(커널)에 등록된 작업
- 시스템 성능 향상을 위해 커널에 의해 관리 됨

프로세스의 정의

- **실행중인 프로그램**
    - 커널에 등록되고 커널의 관리하에 있는 작업
    - 각종 자원들을 요청하고 할당 받을 수 있는 개체
    - 프로세스 관리 블록을 할당 받은 개체
    - 능동적인 개체
        - 실행 중에 각종 자원을 요구, 할당, 반납하며 진행

- process control block
    - 커널 공간 내에 존재
    - 각 프로세스들에 대한 정보를 관리

자원의 개념 

- 커널의 관리 하에 프로세스에게 할당 / 반납 되는 수동적 개체
- 자원의 분류
    - HW resources
    - SW resources

process control block 이란??

os가 프로세스 관리에 필요한 정보 저장

프로세스 생성 시, 생성 됨

pcb가 관리하는 정보 

- PID
- 스케줄링 정보
- 프로세스 상태
- 메모리 관리 정보
- 입출력 상태 정보
- 문맥 저장 영역
- 계정 정보

- PCB 정보는 OS별로 서로 다름
- PCB 참조 및 갱신 속도는 OS의 성능을 결정 짓는 중요한 요소 중 하나

Created State

- 작업(job)을 커널에 등록
- pcb 할당 및 프로세스 생성

Ready State

- 프로세서 외에 다른 모든 자원을 할당 받은 상태
    - 프로세서 할당 대기 상태
    - 즉시 실행 가능 상태
- Running 상태 dispatch

Running State

- 프로세서와 필요한 자원을 모두 할당 받은 상태
- preemption = running state → ready states

- Block , Sleep
    - Running State → asleep state

Blocked . Asleep State

- 프로세서 외에 다른 자원을 기다리는 상태
    - 자원 할당은 system call에 의해 이루어 짐
- Wake -up
    - Asleep state → ready state

Suspended State

- 메모리를 할당 받지 못한 상태
    - memory image를 swap device에 보관
    - 커널 또는 사용자에 의해 발생

- Swap-out , Swap - in

Terminated / Zombie State

- 프로세스 수행이 끝난 상태
- 모든 자원 반납 후
- 커널 내에 일부 pcb정보만 남아 있는 상태
    - 이후 프로세스 관리를 위해 정보 수집

인터럽트(Interrrupt)

- 예상치 못한, 외부에서 발생한 이벤트
- I/O interrupt 등 다양하다

인터럽트 발생 → 프로세스 중단 → 인터럽트 처리 → 인터럽트 발생 장소, 원인 파악 
→인터럽트 서비스 할 것인지 결정 → 인터럽트 서비스 루틴 호출 

Context Switching(문맥 교환)

- context
    - 프로세스와 관련된 정보들의 잡합
        - CPU resister context → in cpu
        - code & data, stack, pcb ⇒ in memory
- context sacing
    - 현재 프로세스의 register context를 저장하는 작업
- context restoring
    - register context를 프로세스로 복구하는 작업
- contxet switching
    - 실행 중인 프로세스의 context를 저장하고, 앞으로 실행 할 프로세스의 context를 복구 하는 일
        - 커널의 개입으로 이루어짐

context switch overhead

- context switching 에 소요되는 비용
    - os마다 다름
    - os의 성능에 큰 영향을 줌
- 불필요한 context switching 을 줄이는 것이 중요
    - 예, 스레드 사용 등