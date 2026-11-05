# 3차 미니프로젝트 가이드 자료 (루키즈 6기)

## 프로젝트 개요

| 항목 | 내용 |
|------|------|
| 기간 | 2026년 11월 5일(목) ~ 11월 13일(금) – 개발 6일 |
| 산출물 제출 · 발표 | 2026년 11월 13일(금) |
| 참여 | 4개 조 / 조별 발표 30~40분 |

### 주요 목적
이번 프로젝트는 기능을 많이 만드는 것이 아니라, 아래 3가지를 **끝까지 동작하게** 만드는 것이 목적입니다.
Backend와 Frontend는 복잡하지 않게 구성합니다.

1. **LLM 연동** – LangChain RAG + FastAPI
2. **안전한 백엔드** – OWASP Top 10 기준 점검 및 조치
3. **배포** – Docker, Docker Compose, GitHub Actions, AWS EC2 (선택: Kubernetes – Minikube 또는 GCP GKE)

## 파일 안내

| 파일/폴더 | 설명 |
|-----------|------|
| `0.3차프로젝트_가이드.md` | **먼저 읽기** – 목적, 요구사항, 일정, 제출물 |
| `0.개발산출물문서템플릿/` | 개발 산출물 템플릿 9종 |
| `1-1.프로젝트_평가표.md` | 평가 기준 및 배점 |
| `1.발표자료에포함되어야할내용들(예시).md` | 발표 자료 구성 예시 |
| `2.프로젝트발표순서.md` | 발표 일시 및 조별 순서 |
| `3.프로젝트발표타임테이블(예시).md` | 조별 발표 시간 배분 예시 |
| `1.`~`3.개발산출물_샘플_*` | 2025년 3차 프로젝트 결과물 (**보안 미학습 팀 결과물 – 보안 부분은 참고 금지**) |

## 개발 산출물 (9종)

| # | 문서 | 주요 내용 |
|---|------|-----------|
| 1 | 프로젝트 계획서 | 목적, 팀 구성, 일정, 주요 기능, 보안 요구사항 |
| 2 | 시스템 아키텍처 설계서 | 구성도, 기술 스택, 데이터 플로우, 보안 아키텍처 |
| 3 | 데이터베이스 설계서 | ERD, 공통·업무 테이블, Vector DB, Flyway |
| 4 | API 설계서 | 공통 규격, 인증 API, 업무 API, AI API, 내부 API |
| 5 | Backend 개발 명세서 | 구조, 설정, 주요 클래스, 보안 구현, AI 모듈 연동 |
| 6 | Frontend 개발 명세서 | 페이지·컴포넌트, 상태 관리, API 연동, 프론트엔드 보안 |
| 7 | AI 모듈 연동 명세서 | 환경별 모델, RAG, Vector DB, AI 보안 |
| 8 | 컨테이너 배포 가이드 | Dockerfile, Compose, 환경 변수·비밀정보, EC2, CI/CD, (Kubernetes) |
| 9 | 보안 점검서 | OWASP 점검표, 취약점 재현 → 조치 → 재확인 |

## 기술 스택

| 구분 | 기술 |
|------|------|
| Frontend | React 19.3.x, React Router, Zustand, Vite |
| Backend | Spring Boot 4.0.x, Spring Security 7.x, JPA, Java 17 |
| AI Module | Python 3.12, uv 0.12.23, FastAPI, LangChain, Tavily(웹 검색, 필요 시) |
| Database | MariaDB, Vector DB (FAISS 또는 Chroma), Flyway |
| Infra | Docker, Docker Compose, GitHub Actions, AWS EC2, (Minikube / GCP GKE) |

### LLM · 임베딩 모델 (Key는 강사가 제공)

| 구분 | 개발·테스트 | 배포 |
|------|-------------|------|
| LLM | Groq | OpenAI |
| 임베딩 | Ollama bge-m3 | OpenAI text-embedding-3-small |

> 임베딩 모델이 다르므로 배포 환경에서는 문서를 다시 적재(인덱싱)합니다. 자세한 내용은 가이드 3.4절을 참고하세요.

## 평가 배점 (총 100점)

| 영역 | 배점 |
|------|------|
| BackEnd 구현 | 20 |
| FrontEnd 구현 | 15 |
| 보안(Security) | 15 |
| 설계 및 문서화 | 10 |
| AI 연동 구현 | 20 |
| 배포(Deploy) | 20 |
| (선택) Kubernetes 가산 | +3 (총점 100 상한) |
