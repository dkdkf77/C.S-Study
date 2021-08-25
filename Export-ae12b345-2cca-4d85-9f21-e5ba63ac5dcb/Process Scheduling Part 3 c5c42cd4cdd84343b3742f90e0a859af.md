# Process Scheduling Part.3

SPN (shortest - process-Next)

- 비 선점 스케줄링
- 스케줄링 기준
    - 실행시간 (burst time 기준)
    - burst time( 실행 시간) 이 가장 작은 프로세스를 먼저 처리
        - SJF(Shortest Job First) Scheduling
        - 이마트 5개 이하 계산대 코너 같은 느낌?
    - 장점
        - 평균 대기시간 최소화
        - 시스템 내 프로세스 수 최소화
            - 스케줄링 부하 감소, 메모리 절약 → 시스템 효율 향상
        - 많은 프로세스들에게 빠른 응답 시간 제공
    - 단점
        - starvation(무한 대기) 현상 발생 - 실행 시간이 긴 프로세스는 자원을 할당 받지 못 할수 있음
        - 정확한 실행시간을 알 수 없음
            - 실행시간 예측 기법이 필요

                ![스크린샷 2021-08-25 오후 11.18.49.png](Process%20Scheduling%20Part%203%20c5c42cd4cdd84343b3742f90e0a859af/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-25_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_11.18.49.png)

                P2 = stavation 현상을 격는다 

SRTN (Shortest Remaining Time Next)

- spn 의 변형
- 선점 스케줄링
    - 잔여 실행 시간이 더 적은 프로세스가 등장 되는 순간 뺏긴다
    - 장점
        - spn의 장점 극대화
    - 단점
        - 프로세스 생성시, 총 실행 시간 예측이 필요함
        - 잔여 실행을 계속 추적해야 함
        - context switching overhead

HRRN ( High - Response - Ratio- Next)

- spn의 변형
    - Spn + Aging concepts + 비선점 스케줄링
- aging concepts
    - 프로세스의 대기 시간(WT)을 고혀하여 기회 제공
    - 오래된 것 을 고려하여 기회를 제공
- 스케줄링 기준
    - Response ratio 가 높은 프로세스 우선

- response ratio = WT+BT / BT(응답률)
    - SPN의 장점 + Starvation 방지
    - 실행 시간 예측 기법 필요

        ![스크린샷 2021-08-25 오후 11.26.02.jpeg](Process%20Scheduling%20Part%203%20c5c42cd4cdd84343b3742f90e0a859af/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-25_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_11.26.02.jpeg)