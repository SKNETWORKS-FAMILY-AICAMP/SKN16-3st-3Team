# SKN16-3rd-3Team
 LLM을 연동한 내외부 문서 기반 질의 응답 시스템

**기간:** 2025.09.16 ~ 2025.09.17    
**팀원:** 강동기, 박태규, 신지윤, 안주영, 이현민

---

## 1. 프로젝트 개요

### 프로젝트 소개
>**교통사고 전문 챗봇 '챗문철'**   
RAG 기술을 활용하여 교통사고 발생 시 법률 상담을 제공하는 챗봇 서비스

   
### ✅ 프로젝트 배경

![변호사 수임료](https://github.com/user-attachments/assets/338b7417-3990-40d1-aa23-321ef8778bd6)
#### 높은 법률 자문 비용:   
* 변호사 선임 비용에 대한 경제적 부담으로 법률 서비스 이용의 어려움
  
#### 다양해지는 사고 유형 및 급증하는 위험:   
* 낮아지는 운전면허 취득 문턱, 초보 운전자 증가   
* 고령 운전자 및 어린이보호구역 사고 급증   
* 급발진 등 예측 불가능한 사고 발생
  
#### 법률 정보에 대한 낮은 접근성:   
* 교통사고 위험은 높아지지만, 정확한 법률 및 처리 절차에 대한 인지 부족

### ✅ 프로젝트 목표

#### 경제적 장벽 해소:
* 무료 상담을 통해 누구나 부담 없이 법률 서비스를 이용할 수 있는 환경 조성
  
#### 맞춤형 법률 정보 제공:   
* 다양한 사고 유형에 따른 맞춤형 대처 방안 제시
* 과실비율 계산 및 벌금·형사처벌 예측 기능을 통해 사건 결과를 사전에 가늠할 수 있도록 지원

#### 법률 정보의 대중화:   
* 24시간 언제 어디서든 이용 가능한 챗봇으로 법률 정보 접근성 극대화

#### 한문철 변호사 패르소나 적용
* 실제 교통사고 전문 변호사 한문철의 화법·논리 전개 방식을 모사한 AI 에이전트

---

## 2. 기술 스택
| 카테고리 | 기술 스택 |
| :--- | :--- |
| **사용 언어** | ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) |
| **LLM** | ![OpenAI](https://img.shields.io/badge/OpenAI-412991?logo=openai&logoColor=white) ![ChatGPT](https://img.shields.io/badge/ChatGPT-74AA9C?logo=openai&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-0092B9?logo=langchain&logoColor=white) |
| **벡터 데이터베이스** | ![ChromaDB](https://img.shields.io/badge/ChromaDB-5542D0) |
| **임베딩 모델** | ![OpenAI Embeddings](https://img.shields.io/badge/OpenAI_Embeddings-412991?logo=openai&logoColor=white) |
| **인터페이스(UI)** | ![Gradio](https://img.shields.io/badge/Gradio-FF7C00?logo=gradio&logoColor=white) |
| **형상 관리** | ![Git](https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white) ![Google Drive](https://img.shields.io/badge/Google_Drive-4481ED?logo=googledrive&logoColor=white) |

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
```bash
git clone https://github.com/Your-Username/ChatMoonCheol-Project.git
cd ChatMoonCheol-Project
pip install -r requirements.txt
```
### API 키 설정
```bash
# .env 파일 생성
OPENAI_API_KEY="your_openai_api_key_here"
```
### 시스템 실행
```bash
python src/app.py
```
---

## 5. 시스템 아키텍처 및 처리 흐름

### ✅ 시스템 아키텍처
ChatMoonCheol은 RAG(Retrieval-Augmented Generation) 기반 구조로 설계됨
<img width="2654" height="3840" alt="system architecture" src="https://github.com/user-attachments/assets/54700883-d95c-43f3-8e7f-edd7cea6ed9f" />

### ✅ 시스템 플로우
📌 구성요소
1. **질문 입력**   
사용자가 자연어로 질문이나 요청을 입력

2. **UI 인터페이스**   
Gradio UI를 통해 입력을 시스템으로 전달

3. **입력 처리**   
사용자의 입력을 전처리하여 텍스트/이미지 등 유형에 따라 분류

4. **문서 검색 (RAG DB & Database)**   
RAG DB와 Database를 통해 의미 유사도가 높은 문서나 데이터를 검색

5. **AI 처리 (Image AI / AI 응답생성)**   
이미지 관련 요청은 Image AI에서 처리   
텍스트 관련 요청은 AI 응답생성 모듈에서 답변 초안 작성

6. **분석기**   
AI 응답과 데이터 검색 결과를 분석·보완하여 답변의 정확성과 품질을 향상

7. **최종 응답 생성**   
분석된 결과를 종합해 최종 응답을 생성

8. **사용자 응답 출력**   
사용자 화면에 구조화된 최종 답변을 전달

![systemflow](https://github.com/user-attachments/assets/071d904f-a884-4e82-b9b9-20459cb43572)
> **전체 구조 요약:**   
사용자 입력 → 인터페이스(UI) → 메인 처리 → (AI/DB 활용) → 분석 → 응답 생성 → 사용자 응답

---

## 6. 수집한 데이터 및 전처리 요약
