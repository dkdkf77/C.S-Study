# Process Synchronizing Part.2

Dekker's Algorithm

- 두개의 프로세스 일때 ME을 보장하는 최초의 알고리즘 !

![스크린샷 2021-08-26 오후 10.42.32.jpeg](Process%20Synchronizing%20Part%202%2079a3cce9e9054ca3aa83a5090bde501d/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-26_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_10.42.32.jpeg)

Peterson's Algorithm

- dekker's algorithm 보다 쉽게 다가감
- 깃발 을 드는 것은 똑같은데 양보를 함

    ![스크린샷 2021-08-26 오후 10.44.43.jpeg](Process%20Synchronizing%20Part%202%2079a3cce9e9054ca3aa83a5090bde501d/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-26_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_10.44.43.jpeg)

    N - Process Mutual Exclusion

    - 다익스트라
        - 최초로 프로세스 n개의 상호배제 문제를 소프트웨어적으로 해결
        - 실행 시간이 가자아 짧은 프로세스에 프로세서 할당하는 세마포 방법, 가장 짧은 평균 대기시간 제공

            ![스크린샷 2021-08-26 오후 10.46.57.jpeg](Process%20Synchronizing%20Part%202%2079a3cce9e9054ca3aa83a5090bde501d/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-26_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_10.46.57.jpeg)

    SW Solutions

    - 문제점
        - 속도가 느림
        - 구현이 복잡한
        - ME primitive 실행 중 preemption 될 수 있음
            - 공유 데이터 수정 중은 interrrupt를 억제 함으로서 해결 가능
                - overhead 발생
            - busy waiting
                - inefficient