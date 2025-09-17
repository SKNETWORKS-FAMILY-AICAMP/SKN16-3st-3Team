# SKN16-3rd-3Team
 LLM을 연동한 내외부 문서 기반 질의 응답 시스템

**기간:** 2025.09.16 ~ 2025.09.17  
**팀원:** 강동기, 박태규, 신지윤, 안주영, 이현민

---

## 1. 프로젝트 개요

### 프로젝트 소개
>**교통사고 전문 챗봇 '챗문철'**

### 프로젝트 필요성
~~

### 프로젝트 목표
~~

---

## 2. 기술 스택
| 카테고리 | 기술 스택 |
| :--- | :--- |
| **사용 언어** | ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) |
| **LLM** | ![OpenAI](https://img.shields.io/badge/OpenAI-412991?logo=openai&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-0092B9?logo=langchain&logoColor=white) |
| **벡터 데이터베이스** | ![ChromaDB](https://img.shields.io/badge/ChromaDB-5542D0) |
| **데이터베이스** | ![SQLite](https://img.shields.io/badge/SQLite-003B57?logo=sqlite&logoColor=white) |
| **인터페이스(UI)** | ![Gradio](https://img.shields.io/badge/Gradio-FF7C00?logo=gradio&logoColor=white) |
| **형상 관리** | ![Git](https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white) |

---

## 3. 프로젝트 구조

```
SKN16_3rd_3Team/ 
├── src/                       # 메인 소스 코드
│   ├── app.py                 # Gradio UI 및 애플리케이션 실행
│   ├── core.py                # 메인 시스템 로직
│   ├── database.py            # 데이터베이스 관리
│   ├── rag_system.py          # RAG 시스템
│   └── analyzer.py            # 대화 분석기
│
├── assets/                    # 아바타 등 정적 파일
├── data/                      # DB, 벡터 저장소 등 데이터 저장용
│   └── .gitkeep               # 빈 디렉토리 추적
│
├── .env.example               # 환경변수 예시
├── .gitignore                 # Git 추적 제외 목록
├── requirements.txt           # 의존성 패키지
└── README.md                  # 프로젝트 설명

```
---

## 4. 설치 및 실행

### 환경설정
```
git clone https://github.com/Your-Username/ChatMoonCheol-Project.git
cd ChatMoonCheol-Project
pip install -r requirements.txt
```
### API 키 설정
```
OPENAI_API_KEY="sk-명
```
### 시스템 실행
```
python src/app.py
```
---

## 5. 시스템 아키텍처 및 처리 흐름

### 시스템 아키텍처
~~사진
~~설명
### 시스템 플로우
![systemflow](https://github.com/user-attachments/assets/071d904f-a884-4e82-b9b9-20459cb43572)
~~설명
