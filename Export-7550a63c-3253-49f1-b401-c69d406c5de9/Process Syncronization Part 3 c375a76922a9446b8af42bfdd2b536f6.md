# Process Syncronization Part.3

Synchronization Hardware

- TestAndSet(TAS) instruction
    - Test 와 Set 을 한번에 수행하는 기계어
    - machine instruction
        - Atomicity,indivisible
        - 실행 중 interrrupt 를 받지 않음
    - Busy Waiting
        - inefficient

        ![스크린샷 2021-08-26 오후 10.55.26.jpeg](Process%20Syncronization%20Part%203%20c375a76922a9446b8af42bfdd2b536f6/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-26_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_10.55.26.jpeg)

- 왜 조건 위배 인가? - 한명이 계속 적으로 못 들어가는 경우가 생긴다

![스크린샷 2021-08-26 오후 10.57.51.jpeg](Process%20Syncronization%20Part%203%20c375a76922a9446b8af42bfdd2b536f6/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-26_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_10.57.51.jpeg)

HW Solution

- 장점
    - 구현이 간단
- 단점
    - 아직도 비지 웨이팅이 존재
- 비지 웨이팅 문제를 해소한 상호배제 기법
    - semaphore
        - 대부분의 os들이 사용하는 기법
-