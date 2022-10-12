# 소프트웨어 개발 보안 구축
---

## chap1. 소프트웨어 개발 보안 설계

- 소프트웨어 개발 보안 설계
  - SW 개발 보안의 개념
    - sw 개발 보안 생명 주기
      - 요구사항 명세 -> 설계 -> 구현 -> 테스트 -> 유지보수
  - SW 개발 보안의 구성 요소
    - 기밀성, 무결성, 가용성을 지키고 서버 취약점을 방지하여 위협으로 부터 위험을 최소화하는 구축방법을 말함.
    - sw 개발 보안 3대 요소 (**기무가**)
      - 기밀성
        - 인가되지 않은 개인, 시스템 접근에 따른 정보 공개 및 노출을 차단하는 특성
      - 무결성
        - 정당한 방법을 따르지 않고는 데이터가 변경될 수 없고, 데이터의 정확성 및 완전성과 고의/악의로 변경되거나 훼손또는 파괴되지 않음을 보장하는 특성
      - 가용성
        - 권한을 가진 사용자나 애플리케이션이 원하는 서비스를 지속해서 사용할 수 있도록 보장하는 특성
    - sw 개발 보안 용어 (**자위취위**)
      - 자산 - 조직의 데이터 또는 조직의 소유자가 가치를 부여한 대상
      - 위협 - 조직이나 기업의 자산에 악영향을 끼칠 수 있는 사건이나 행위
      - 취약점 - 위협이 발생하기 위한 사전 조거느 시스템의 정보 보증을 낮추는데 사용되는 약점
      - 위험  - 위협이 취약점을 이용하여 조직의 자산 손실 피해를 가져올 가능성
    - SW 개발 보안을 위한 공격기법의 이해
      - DoS 공격
        - 시스템을 악의적으로 공격해서 해당 시스템의 자원을 부족하게 해 원래 의도된 용도로 사용하지 못하게 하는 공격
        - 특정 서버에 수많은 접속 시도를 만들어 다른 이용자가 정상적으로 서비스 이용을 못하게 하거나, 서버의 tcp 연결을 소진시키는 공격
        - DoS 공격 종류 (**SU스죽랜티봉**)
          - SYN 플러딩
            - tcp 프로토콜의 구조적 문제를 이용한 공격
            - 서버의 동시 가용 사용자 수를 syn 패킷만 보내 점유해 다른 사용자가 서버를 사용 불가능하게 하는 공격
            - ack를 발송하지 않고 계속 새로운 연결 요청을 하게 돼 서버는 자원할당을 해지 않고 자원만 소비하여 고갈됨.
          - UDP 플러딩
            - 대량의 udp 패킷을 만들어 임의의 포트 번호로 전송해 응답 메시지를 생성하게 해 지속해 자원을 고갈시키는 공격
            - ICMP 패킷은 변조되어 공격자에게 전달되지 않아 대기함.
          - 스머프/스머핑
            - 출발지 주소를 공격 대상 ip로 설정해 네트워크 전체에게 icmp echo 패킷을 직접 브로드캐스팅 해 마비시키는 공격
          - 죽음의 핑
            - icmp 패킷을 정상적인 크기보다 아주 크게 만들어 전송하면 다수의 ip 단편화가 발생, 수신 측에서는 단편화된 패킷을 처리하는 과정에서 많은 부하 발생하거나 재조합 오버플로우가 발생해 정상적 서비스 하지 못하도록 만듦.
          - 랜드 어택
            - 출발지 ip와 목적지 ip를 같은 패킷 주소로 만들어 보냄으로 수신자가 자기 자신에게 응답을 보내게 해 시스템 가용성을 침해함.
          - 티어 드롭
            - ip 패킷의 재조합 과정에서 잘못된 fragment offset 정보로 인해 수신시스템이 문제를 발생하도록 만드는 dos 공격
            - 공격자는 ip fragment offset 값을 서로 중첩되도록 조작해 전송, 이를 수신한 시스템이 재조합하는 과정에서 오류 발생, 시스템의 기능을 마비시키는 공격 방식
          - 봉크/보잉크
            - 프로토콜의 오류 제어를 이용한 공격기법으로 시스템의 패킷 재전송과 재조립이 과부하를 유발
      - DDoS 공격
        - DoS의 또 다른 형태로 여러 대의 공격자를 분산 배치, 동시에 동작하게 함으로써 특정 사이트를 공격함.
        - 취약한 인터넷 시스템에 대한 액세스가 이뤄지면, 침입한 시스템에 소프트웨어를 설치하고 이를 실행해 원격에서 공격을 개시한다.
        - DDoS 공격 구성요소 (**HAMAD**)
          - 핸들러
          - 에이전트
          - 마스터
          - 공격자
          - 데몬 프로그램
        - DDoS 공격 도구
          - Trinoo
          - Tribe Flood Network
          - Stacheldraht
        - DDoS 공격 대응 방안
          - 차단 정책 업데이트
          - 좀비PC IP 확보
          - 보안 솔루션 운영
          - 홈페이지 보안 관리
          - 시스템 패치
        - DDoS 공격의 종류
          - 대역폭 소진 공격(3~4 계층))
          - 서비스 마비 공격 (7계층)
      - DRDoS (Distributed Reflection DoS) 공격
        - 공격자는 출발지 IP를 공격대상 IP로 위조하여 다수의 반사 서버로 요청 정보를 전송, 공격 대상자는 반사 서버로부터 다량의 응답을 받아 서비스 거부가 되는 공격
        - DDoS에 비해 공격 근원지 파악이 어렵고, 공격 트래픽 생성 효율이 DDoS보다 훨씬 크다.
        - 절차
          - 1. 출발지 IP 변조
          - 2. 공격 대상자 서버로 응답
          - 3. 서비스 거부
        - 대응 방안
          - ISP가 직접 차단
          - 반사 서버에 연결을 완료하지 않은 Syn 출처 IP를 조사해 블랙 리스트로 운용, 공격 서버를 사전에 차단.
      - 애플리케이션 공격
        - 주로 HTTP 와 관련된 공격이 주를 이룸.
        - HTTP GET 플러딩
        - Slowloris
        - RUDY
        - Slow HTTP Read DoS
        - Hulk DoS
        - Hash DoS
      - 네트워크 공격
        - 스니핑
        - 네트워크  스캐너, 스니퍼
        - 패스워드 크래킹
        - ip 스푸핑
        - ARP 스푸핑
        - ICMP Redirect 공격
        - 트로이 목마
      - 시스템 보안 위협
        - 버퍼 오버플로우 공격
          - 메모리에 할당된 버퍼 크기를 초과하는 양의 데이터를 입력해 이로 인해 프로세스 흐름을 변경시켜 악성 코드를 실행시키는 공격 기법
            - 스택 버퍼 오버플로우 공격
            - 힙 버퍼 오버플로우 공격
          - 버퍼 오버플로우 공격 대응 방안
            - 스택가드 활용
            - 스택쉴드 활용
            - ASLR 활용
            - 안전한 함수 활용
            - 실행 제한
  
        - 백도어
          - 정상적인 인증 절차를 우회하는 기법
          - 탐지기법
            - 프로세스 및 열린 포트 확인
            - Setuid 파일 검사
            - 백신 및 백도어 탐지 툴 활용
            - 무결성 검사
            - 로그 분석
        - 주요 시스템 보안 공격기법
          - 포맷 스트링 공격
          - 레이스 컨디션 공격
          - 키로거 공격
          - 루트킷
        - 보안관련 용어
          - 스피어피싱
          - 스미싱
          - 큐싱
          - 봇넷
          - apt 공격
          - 공급망 공격
          - 제로데이 공격
          - 웜
          - 악성 봇
          - 사이버 킬체인
          - 랜섬웨어
          - 이블 트윈 공격
          - 난독화
          - Tripwire
          - Ping
          - Tcmpdump
- 서버 인증 및 접근 통제
  - 다중 사용자 시스템과 망 운영 시스템에서 접속자의 로그인 정보를 확인하는 보안절차.
  - 전송된 메시지 무결성 및 송신자를 검증하는 과정이 인증에 해당함.
  - 서버 인증의 기능 (**스피데기**)
    - 스니핑 방지
    - 피싱 방지
    - 데이터 변조 방지
    - 기업 신뢰도 향상
  - 인증 기술 유형 (**지소생특**)
    - 지식기반
    - 소지기반
    - 생체기반
    - 특징기반
  - 서버 접근 통제
    - 사람 또는 프로세스가 서버 내 파일에 읽기, 쓰기, 실행 등 접근 여부를 허가하거나 거부하는 기능.
    - 목적
      - 비인가자로부터 객체의 기밀성, 무결성, 가용성 보장
      - 접근 통제 위해 **식별, 인증, 인가, 책임추적성** 기법 적용
      - 서버 접근 통제 유형 (**임강역**)
        - 임의적 접근 통제 (DAC)
        - 강제적 접근 통제 (MAC)
        - 역할기반 접근 통제 (RBAC)

|정책|DAC|MAC|RBAC|
|:--:|:--:|:--:|:--:|
|권한부여|데이터 소유자|시스템|중앙관리자|
|접근 결정|신분|보안등급|역할|
|정책 변경|변경 용이|고정적|변경 용이|
|장점|구현 용이 <br> 유연함|안정적 <br> 중앙 집중적|관리 용이|

  - 접근 통제 보호 모델 (**벨기비무**)
    - 벨-라파듈라 모델
      - 미 국방부 지원 보안 모델, 보안 요소 중 **기밀성**을 강조하며 강제적 정책에 의해 접근 통제하는 모델
    - 비바 모델
      - 벨-라파둘라 모델의 단점을 보완한 **무결성** 보장 최조의 모델   

- SW 개발 보안을 위한 암호화 알고리즘
  - 암호 알고리즘 개념
    - 데이터의 무결성 및 기밀성 확보를 위해 정보를 쉽게 해독할 수 없는 형태로 변환하는 기법
  - 암호 알고리즘 방식
    - 양방향 암호 방식
      - 대칭 키 암호 방식
        - 암호화와 복호화에 같은 암호키 사용
        - 블록 암호방식
          - 긴 평문 암호화하기 위해 고정 길이 블록을 암호화하는 블록 암호 알고리즘을 반복
        - 스트림 암호 방식
          - 매우 긴 주기의 난수열을 발생시켜 평문과 더불어 암호문을 생성하는 방식
      - 비대칭 키 암호 방식 (공개키 방식)
        - 사전에 개인 키를 나눠 가지지 않은 사용자들이 안전하게 통신하는 방식
        - RSA, ECC, 디피-헬만 등
    - 일방향 암호 방식 (해시 암호 방식)
      - 임의 길이의 정보를 입력받아, 고정된 길이의 암호문을 출력하는 암호 방식
      - 해시 암호화 알고리즘이 적용된 정보는 복호화가 불가능함
      - 해시 함수를 기반으로 하는 일방향 방식은 MAC, MDC가 존재.
  - 암호 알고리즘 상세
  
|구분|대칭 키 암호 방식|비대칭 키 암호 방식|
|:--:|:--:|:--:|
|키|대칭 키(비밀키)|비대칭 키(공개키, 사설 키)|
|암호 알고리즘|공개|공개|
|장점|계산 속도 빠름|암호화 키 사전 공유 불필요 <br> 관리해야할 키 개수가 적음|
|단점|키 분배 및 관리 어려움 <br> 기밀성만 보장|계산 속도 느림|
|알고리즘|DES, AES, SEED|디피-헬만, RSA|


     

---

## chap2. 소프트웨어 개발 보안 구현
