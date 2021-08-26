# Process Synchronization part.4

- Spinlock
    - 정수 변수
    - 초기화,p(),v() 연산으로만 접근 가능
        - 위 연산들은 indivisible 연산
            - OS support
            - 전체가 한 instruction cycle에 수행 됨

        ![스크린샷 2021-08-26 오후 11.02.12.jpeg](Process%20Synchronization%20part%204%201387c37350934b1fa877c5ca17fa3c2e/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-26_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_11.02.12.jpeg)

        S = 물건의 갯수 p는 물건을 빼는 것 V는 물건을 넣는 것 

        ![스크린샷 2021-08-26 오후 11.04.39.jpeg](Process%20Synchronization%20part%204%201387c37350934b1fa877c5ca17fa3c2e/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-26_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_11.04.39.jpeg)

        스핀락의 문제 

        - 멀티프로세서 시스템에서만 사용 가능
        - 비지 웨이팅