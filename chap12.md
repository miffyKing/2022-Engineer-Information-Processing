# 제품 소프트웨어 패키징

---
중요한 문제만 공부하면 고득점 가능

---

## chap1. 제품 소프트웨어 패키징 하기

---

### 사용자 중심의 패키징 수행

- 제품 소프트웨어 패키징
  - 개발이 완료된 제품 소프트웨어를 고객에게 전달하기 위한 형태로 포장하는 과정
  - 제품 소프트웨어 패키징 적용 특성
    - 전체 내용을 포함
    - 버전관리 / 릴리즈 노트
    - 고객 중심
    - 모듈화
- 제품 소프트웨어 패키징을 위한 모듈 빌드.
  - 패키징은 모듈들을 통해 수행되므로, 최초 소스 개발 시 해당 모듈 단위 및 모듈화를 통해 제품 소프트웨어 패키징을 수행함.
  
  - **모듈화**
    - 모듈을 이용하여 소프트웨어의 성능을 향상시키거나 시스템의 디버깅, 시험, 통합 및 수정을 용이하도록 하는 모듈 중심의 소프트웨어 설계 기법
    - **결합도를 최소화**, 모듈 내 요소들 간의 **응집도 최대화**
      - Loose Coupling, Strong Cohesion
    - 모듈화 장점
      - **개발 편의성**
        - 프로그램 효율적 관리
        - 전체 소프트웨어 이해도 증가
        - 소프트웨어 시험,통합, 수정 시 용이
        - 모듈의 재사용 가능, 개발 유지보수 용이
        - 오류 파급 효과 최소화
      - **복잡성 감소**
        - 기능의 분리가 가능, 인터페이스 단순
        - 복잡도 감소로 인한 성능 향상
  - 제품 소프트웨어 모듈 빌드 기법
  - 사용자 중심의 패키징 작업
    - 시스템 환경
    - 직관적 UI
    - 관리 서비스
    - 안정적 배포
### 버전을 고려한 제품 릴리즈 노트 작성
- 릴리즈 노트
  - 최종 사용자인 고객에게 개발 과정에서 정리된 제품의 릴리즈 정보를 제공하는 문서
  - 릴리즈 노트 중요성
    - 정보제공
    - 관리의 용이성
  - 릴리즈 노트 작성 항목 (**헤개목이 재수사소 노면연**)
    - 헤더 > 문서이름, 제품이름, 버전번호 등
    - 개요 > 제품 및 변경에 대한 간략한 전반적 개요
    - 목적 > 릴리즈 버전의 새로운 기능 목록, 릴리즈 노트의 목적, 버그 수정 등 설명
    - 이슈 요약 > 버그의 간단한 설명, 릴리즈 추가 항목 요약
    - 재현 항목 > 버그 발견에 따른 재현 단계
    - 수정,개선 내용 > 수정, 개선의 간단한 설명 기술
    - 사용자 영향도 > 버전 변경에 따른 최종 사용자 기준의 기능 및 응용 프로그램상의 영향도
    - 소프트웨어 지원 영향도 > 버전 변경에 따른 소프트웨어의 지원 프로세스 및 영향도
    - 노트 > 소프트웨어 및 하드웨어 설치 항목, 제품, 문서를 포함 업그레이드 항목
    - 면책 조항 > 회사 및 표준 제품 관련 메시지, 불법 복제 방지, 중복 등 참조 고지
    - 연락 정보 > 사용자 지원 문의 연락처
  - 릴리즈 노트 예외 케이스
    - 테스트 단계에서의 베터 버전 출시
    - 긴급 버그 수정 시
    - 자체 기능 향상을 포함한 모든 추가 기능의 향상
    - 사용자 요청에 따른 특이 케이스 발생
  ### 패키징 도구를 활용한 설치, 배포 수행
- 제품 소프트웨어 패키징 도구
  - 배포를 위한 패키징 시 디지털 콘텐츠의 지적 재산권을 보호,관리 기능 제공. 안전한 유통, 배포 보장
  - 패키징 도구 활용 고려사항
    - 암호화/보안 고려
    - 이기종 연동 고려
    - 사용자 편의성 고려
    - 적합한 암호화 알고리즘 적용
- 제품 소프트웨어 저작권 보호의 이해와 필요성
  - 저작권 보호 기술
    - 콘텐츠 복제 제한적 허용
    - 종량제
    - 암호화/보안 기능
  - 저작권 보호 측면의 패키징 도구 활용
    - 디지털 저작권 관리 (**DRM**)
      - 중앙의 클리어링 하우스에서 컨텐츠 제공자, 분배자, 패키징 배포 및 키 관리, 라이선스 발급 관리 수행
      - 저작권 관리 구성 요소
        - 콘텐츠 제공자
        - 콘텐츠 분배자
        - 패키저
        - 보안 컨테이너
        - DRM 컨트롤러
        - 클리어링 하우스
      - 암호화/보안 기능 중심 패키징 도구 기술 활용
        - **패키징 도구 구성** (**암키식저 파정크인**)
          - 암호화
          - 키 관리
          - 식별 기술
          - 저작권 표현
          - 암호화 파일 생성
          - 정책 관리
          - 크랙 방지
          - 인증
        - **패키징 도구 구성 세부 기술** -> 너무 양이 방대한데 책으로 외우자
          - 암호화
            - 공개키 기반구조
            - 대칭 및 비대칭 암호화
            - 전자 서명
          - 식별 기술
            - DOI
            - URI
          - 저작권 표현
            - XrML
            - MPEG-21
          - 암호화 파일 생성
            - Pre-packaging
            - On-the-fly Packaging 
          - 정책 관리
            - XML
            - CMS
          - 크랙 방지
            - 코드 난독화
            - Secure DB
          - 인증
            - SSO
---

## chap2. 제품 소프트웨어 매뉴얼 작성 및 버전 등록

---
### 제품 소프트웨어 매뉴얼 작성 및 버전 등록
- 제품 소프트웨어 설치 매뉴얼 기본작성 항목 (**목이주구**)
  - 목차 및 개요
  - 문서 이력 정보
  - 설치 매뉴얼 주석
  - 설치 도구의 구성
- 제품 소프트웨어 사용자 매뉴얼 작성 프로세스 (**작사구검**)
  - 작성 지침 정의
  - 사용자 매뉴얼 구성요소 정의
  - 구성요소 별 내용 작성
  - 사용자 매뉴얼 검토
- 버전 관리 도구를 활용한 제품 소프트웨어 소스 및 자료 백업 (**전차증**)
  - 전체 백업 > 백업 받고자 하는 데이터 전체에 대해 백업하는 방식
  - 차분 백업 > 마지막 전체 백업 이후 변경된 모든 데이터를 백업하는 방식
  - 증분 백업 > 정해진 시간을 기준으로 그 이후에 변경된 파일만을 백업하는 방식