[English](README.md) | **한국어** | [中文](README_zh.md)

<div align="center">

# NeoSQL

**ERD 설계부터 SQL 실행, AI 기반 분석, 스키마 변경 관리와 대시보드까지 하나로 연결하는 데이터베이스 개발 플랫폼**

[![License](https://img.shields.io/badge/license-Commercial-blue?style=for-the-badge)](https://neosql.unvus.com/)
[![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Web-lightgrey?style=for-the-badge)](#사용-환경)
[![Projects](https://img.shields.io/badge/projects-Local%20%7C%20Account-success?style=for-the-badge)](#프로젝트-선택)

[홈페이지](https://neosql.unvus.com/) &middot; [다운로드](https://neosql.unvus.com/) &middot; [이슈 및 피드백](#이슈-및-피드백)

</div>

---

문서 작성 기준일: **2026-10-30**

## 개요

NeoSQL은 데이터베이스 구조를 이해하고, 설계하고, 실제 데이터를 다루는 작업을 하나의 환경에서 이어갈 수 있는 데이터베이스 개발 플랫폼입니다. 기존 데이터베이스를 ERD로 시각화하고, 테이블과 데이터베이스 오브젝트를 관리하며, SQL 실행 결과를 편집하거나 대시보드로 구성할 수 있습니다.

내장 **AI Assistant**는 실제 스키마와 실행 컨텍스트를 바탕으로 자연어 SQL 작성, 데이터 조회·분석, 쿼리 튜닝과 오류 진단을 도와줍니다. **MCP(Model Context Protocol)**를 통해 NeoSQL의 데이터베이스 도구와 ERD 작업에 외부 AI 개발 도구를 활용할 수 있습니다.

Windows·macOS용 Desktop 앱과 Web App을 지원하며, **회원가입이나 로그인 없이 로컬 프로젝트로 시작**할 수 있습니다. 계정 프로젝트를 사용하면 팀원과 프로젝트를 공유하고 작업 내용을 동기화할 수 있습니다.

## 주요 기능

### ERD 설계와 스키마 변경 관리

- 실제 데이터베이스의 테이블·컬럼·키·관계를 읽어 ERD를 구성하는 Reverse Engineering
- 테이블·관계 설계, 컬럼·인덱스·외래 키·제약조건 편집
- ERD 변경 사항 추적과 DBMS별 DDL 미리보기·적용
- 같은 DBMS의 스키마 간 테이블·뷰 등 구조 차이 비교와 변경 DDL 검토
- ERD 이미지 내보내기와 갤러리를 통한 모델 공유

### SQL 에디터와 데이터 작업

- 구문 강조, SQL 포맷팅, 스키마 기반 자동완성과 실행 이력 기반 인라인 제안
- 탭별 독립 DB 세션과 SQL 실행 이력 검색·재사용
- 결과 그리드에서 데이터 조회·수정·삭제, 데이터 가져오기·내보내기
- Auto Commit 또는 Manual Commit 모드와 미커밋 트랜잭션 표시
- 실행 계획 확인과 AI를 활용한 쿼리 개선·오류 분석

> 결과 편집, DDL 적용, Commit/Rollback 등은 DBMS와 쿼리의 지원 범위에 따라 달라집니다. DDL이 암묵적으로 커밋되거나 트랜잭션으로 되돌릴 수 없는 DBMS도 있습니다.

### 내장 AI Assistant와 외부 MCP 연동

- 자연어로 SQL을 작성하고, 실제 조회 결과를 바탕으로 데이터를 분석
- 테이블·컬럼·관계와 실행 계획을 참고한 쿼리 튜닝 및 SQL 오류 진단
- AI 대화에서 ERD와 테이블 설계 생성·수정
- OpenAI, Anthropic, Google Gemini, Ollama 등 AI Provider 연결
- Ollama의 자체 호스팅 서버와 Cloud 연결, 서버에서 사용 가능한 모델 조회
- 계정 또는 기기에 저장한 Provider Key 사용과 AI 호출·토큰 사용량 확인
- 외부 MCP 클라이언트에서 메타데이터 조회, SQL 실행, ERD 설계 도구 활용
- 공통·프로젝트별 MCP 설정으로 현재 프로젝트 또는 지정한 프로젝트에 연결

AI가 접근할 연결·스키마와 데이터 조회·변경 정책을 설정하고, 정책에 따라 실행할 SQL과 대상을 확인한 뒤 승인할 수 있습니다. 계정 프로젝트에서는 역할 권한, 민감 컬럼 마스킹과 DDL 승인 기능도 활용할 수 있습니다.

MCP 클라이언트 설정에 DB 접속 비밀번호를 직접 입력할 필요는 없습니다. 다만 AI 기능은 설정과 승인 범위에 따라 스키마 정보나 조회 결과를 선택한 AI Provider로 전송할 수 있으니 주의해 주세요.

### 쿼리 기반 대시보드

- SELECT 결과를 숫자 카드, 표, 막대·선·영역·원형·산점도 등 차트로 시각화
- SQL 에디터의 쿼리를 대시보드 타일로 연결
- 타일 배치·크기 조절, 조회 기간과 자동 새로고침 주기 설정
- 세션·잠금·성능·스토리지·스키마 품질 등을 살펴보는 DBMS별 모니터링 프리셋
- 연결 DB의 시간대를 기준으로 한 기간 조회와 사용자 시간대 표시 옵션

대시보드는 로컬 프로젝트와 계정 프로젝트 모두에서 사용할 수 있습니다. 자동 새로고침은 대시보드 탭이 표시되는 동안 동작하며, 프리셋의 사용 가능 여부는 DBMS와 접속 권한에 따라 달라집니다.

### 데이터 표준화와 DBMS별 상세 관리

- 데이터 사전과 도메인 팩으로 논리명·용어·데이터 타입 표준 관리
- 사전·도메인 가져오기·내보내기, 버전 선택과 원본 대비 변경 확인
- Store에서 데이터 사전·도메인 팩 등 자산 탐색·설치
- DBMS별 뷰·인덱스·시퀀스·루틴·사용자·권한 등 오브젝트 조회 및 지원 범위 내 관리
- PostgreSQL RLS 정책 시뮬레이션, Supabase 연계, 공간 데이터와 사용자 정의 타입 처리
- Databricks SQL Warehouse 선택, Delta 테이블 속성·버전 이력 조회와 버전 복원

### 팀 협업과 프로젝트 동기화

계정 프로젝트에서는 팀원 초대와 역할별 권한을 설정하고, ERD와 프로젝트 설정 등 공유 작업 데이터를 동기화할 수 있습니다. 다른 사용자의 변경 사항을 감지해 작업 화면에서 다시 불러오고 검토할 수 있습니다.

## 사용 환경

### Desktop과 Web

| 구분 | Desktop | Web App |
|------|---------|---------|
| 실행 환경 | Windows, macOS(Apple Silicon·Intel) | 브라우저 |
| 로그인 | 계정 없이 시작 가능 | 로그인 필요 |
| DB 연결 경로 | 앱을 실행하는 PC에서 연결 | 서비스 서버에서 연결 |
| 사내망·로컬 DB | PC에서 접근 가능한 DB에 연결 | 서비스 서버에서 접근 가능한 DB만 연결 |
| 로컬 프로젝트 | 지원 | 미지원 |
| 계정 프로젝트·팀 협업 | 지원 | 지원 |
| 외부 AI 도구 MCP 연동 | 지원 | 미지원 |
| AI Provider Key | 기기 로컬 키·계정 키 | 계정 키 |

> 사내망이나 개발 PC에서만 접근할 수 있는 데이터베이스에는 Desktop 앱을 사용해 주세요.

### 프로젝트 선택

| 구분 | 로컬 프로젝트 | 계정 프로젝트 |
|------|---------------|---------------|
| 사용 조건 | Desktop, 로그인 선택 | Desktop·Web, 로그인 필수 |
| 프로젝트 데이터 | 해당 기기에 저장 | 계정 기반 저장·동기화 |
| 주요 용도 | 개인 작업, 사내망·폐쇄망 DB 작업 | 팀 공유와 여러 기기에서의 작업 |
| ERD·SQL·대시보드·데이터 사전 | 지원 | 지원 |
| 내장 AI | 기기에서 사용 가능한 Provider 연결 필요 | 사용 가능한 Provider 연결 필요 |
| 팀 멤버·역할 권한·DDL 승인·민감 컬럼 마스킹 | 미지원 | 지원 |

로컬 프로젝트의 기본 DB 작업에는 계정 로그인이 필요하지 않습니다. 인터넷이 없는 환경에서도 기기에서 접근 가능한 DB로 작업할 수 있으며, AI는 해당 환경에서 접근 가능한 Provider가 필요합니다. 공개 Store에서 제공되는 항목의 다운로드와 업데이트 등 온라인 기능에는 네트워크 연결이 필요합니다.

로컬 프로젝트와 계정 프로젝트의 타입 전환은 지원하지 않습니다.

## 지원 데이터베이스

| 데이터베이스 | |
|--------------|:-:|
| MySQL | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) |
| MariaDB | ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) |
| PostgreSQL | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) |
| Oracle | ![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white) |
| SQL Server | ![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white) |
| SQLite | ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) |
| H2 | ![H2](https://img.shields.io/badge/H2-0000BB?style=flat-square) |
| Databricks | ![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white) |
| Snowflake | ![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=snowflake&logoColor=white) |
| Google BigQuery | ![Google BigQuery](https://img.shields.io/badge/Google%20BigQuery-669DF6?style=flat-square&logo=googlebigquery&logoColor=white) |

DBMS마다 지원하는 오브젝트, DDL, 결과 편집과 관리 기능의 범위가 다릅니다. PostgreSQL 기반 Supabase를 위한 연계 기능도 제공합니다.

## 주요 활용 시나리오

- **기존 시스템 파악**: 레거시 DB의 테이블과 관계를 ERD로 시각화하고 AI와 함께 구조 분석
- **설계와 변경 검토**: 데이터 사전으로 용어를 맞추고, ERD 변경과 스키마 차이를 DDL로 검토
- **일상적인 SQL 개발**: 쿼리 작성·실행·결과 편집·이력 재사용을 한 화면에서 처리
- **데이터 분석과 모니터링**: 자연어로 데이터를 탐색하고 반복 조회를 대시보드로 구성
- **AI 개발 도구 연결**: 외부 에이전트가 NeoSQL의 DB 컨텍스트와 실행 도구를 활용하도록 MCP 연동
- **개인 작업과 팀 협업**: 로컬 프로젝트로 시작하거나 계정 프로젝트에서 팀원과 모델·설정 공유

## 다운로드

최신 Desktop 앱은 [NeoSQL 홈페이지](https://neosql.unvus.com/)의 다운로드 버튼에서 운영체제에 맞는 설치 파일을 받을 수 있습니다.

| 플랫폼 | 설치 파일 |
|--------|-----------|
| Windows | `.exe` |
| macOS — Apple Silicon / Intel | `.dmg` |

Web App과 제품 안내는 [홈페이지](https://neosql.unvus.com/)에서 확인할 수 있습니다.

## 이슈 및 피드백

버그 리포트, 기능 요청, 사용 중 문의는 이 저장소의 [Issues](https://github.com/unvus/neosql/issues)에서 관리합니다. 앱 안의 버그 신고 기능으로도 스크린샷과 진단 정보를 검토·첨부해 신고할 수 있으며, 로그인이 필요하지 않습니다.

이슈 등록 시 앱 버전, 사용 환경(Desktop/Web, OS), 데이터베이스 종류와 재현 절차를 함께 기재해 주세요. 비밀번호·API Key·개인정보 등 민감한 내용은 제외해 주세요.

## 라이선스

NeoSQL은 상업용 라이선스로 제공됩니다. 사용 범위, 재배포 가능 여부, 유지보수 범위, 배포 조건은 별도 계약 또는 공급 정책에 따릅니다.

라이선스, 도입, 기술 지원, 엔터프라이즈 배포 관련 문의는 [홈페이지](https://neosql.unvus.com/)를 통해 진행해 주세요.
