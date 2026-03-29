# Secondhand_Book_Shop

# 헌책방 (중고 도서 거래 & 지역 서점 연계 플랫폼)

> * **프로젝트 기간:** 2025.03.27 ~ 2025.06.15 (전공종합설계 PBL2)
> * **팀 구성:** 5인 (어쩌다보니 팀)
> * **나의 역할:** 백엔드 개발 및 AWS 인프라 구축 전담

## 프로젝트 소개
'헌책방'은 일반적인 개인 간 중고 도서 거래를 넘어, 지역 헌책방의 오프라인 재고까지 한곳에서 살펴볼 수 있는 통합 플랫폼입니다. 사용자 간의 자율적인 직거래 환경은 물론, 동네 서점의 도서를 쉽게 찾고 예약 구매할 수 있는 편의성을 제공합니다."

## 사용 기술 (Tech Stack)
* **Design & Collaboration:** Figma, Zeplin
* **Frontend:** React Native, Expo
* **Backend:** Python, Flask, SQLAlchemy (ORM)
* **Database:** MySQL (Amazon RDS)
* **Infrastructure:** AWS EC2 (Ubuntu), EBS, Elastic IP, Gunicorn, Nginx, Certbot (HTTPS)
* **External APIs:** Toss 결제 API, Naver 도서 검색 API, Kakao 우편번호 API
* **Tools & Testing:** Postman (API 단독 테스트 및 검증), Git, GitHub

## 나의 역할 및 주요 성과 (Backend Developer)
팀의 백엔드 담당자로서 데이터베이스 설계부터 API 구현, 외부 API 연동, 그리고 AWS 클라우드 배포까지 서버 개발의 전체 사이클을 책임지고 수행했습니다.

**1. 전체 백엔드 아키텍처 및 DB 모델링 설계**
* 전체 백엔드의 파일 및 모듈 구조를 주도적으로 설계하고, 각 도메인에 대한 HTTP API와 도메인 로직을 구현했습니다.
* DB 스키마를 설계하고 SQLAlchemy를 이용해 연동하였으며, 애자일 방식의 프로젝트 진행 중 발생하는 요구사항 변경에 맞춰 테이블 구조와 ORM 매핑을 유연하게 수정 및 대처했습니다.

**2. 핵심 비즈니스 로직 및 외부 API 연동**
* **실시간 채팅:** 개인 간, 개인-업자 간 실시간 채팅 기능을 위해 HTTP API와 WebSocket 이벤트 리스너 구조를 설계하고 구현했습니다. 
* **결제 시스템:** 토스(Toss) 결제 API를 연동하여 예약 구매 및 거래 대금 결제 흐름을 안정적으로 처리했습니다.

**3. 무중단 배포를 위한 AWS 인프라 환경 구축**
* AWS EC2, EBS, RDS(MySQL)를 기반으로 클라우드 인프라를 구성했습니다.
* Elastic IP 및 도메인을 연결하고 Certbot으로 HTTPS를 적용했으며, Gunicorn + Nginx + systemd 조합을 통해 안정적인 WSGI 서버 배포 환경을 구축했습니다.

**4. 클라이언트-서버 연동 최적화**
* 모바일 앱(React Native)의 클라이언트 측 렌더링(CSR) 구조에 맞춰, 프론트엔드에서 데이터를 직관적으로 렌더링할 수 있도록 JSON 응답 구조를 최적화했습니다.
* 원활한 협업을 위해 호출 URI, 입출력 데이터 포맷, 기능 설명, 시나리오별 응답 결과 등을 상세히 기록한 API 명세서를 직접 작성하여 프론트엔드 담당자에게 제공했습니다.
* 디스코드(Discord)를 활용한 실시간 소통으로 프론트엔드-백엔드 간의 API 연동 작업 및 디버깅을 함께 진행하며, 전체적인 데이터 흐름을 풀스택 관점에서 조율했습니다.

## 시작하기 (Database Setup)
본 프로젝트는 MySQL을 사용하며, 원활한 테스트를 위해 초기 데이터가 포함된 SQL 스크립트를 제공합니다.
* MySQL 접속 후 데이터베이스 생성
* `db/init_data.sql` 파일을 임포트하여 테이블 및 테스트 데이터 생성
* .env.example 파일을 복사하여 .env 파일을 생성하고, 본인의 환경에 맞는 DB 접속 정보 및 API 키를 입력합니다.