# **ezen_project_helper**

---

## 대한민국 청년 정책 AI Agent

- 프로젝트 기간: 2025/5/26 ~ 2025/6/11
- 참여 인원: 김도현, 백윤지, 박병건, 지세하, 최도경

## 담당 모듈

- **김도현 (Spring Boot)**
    - JWT 토큰 기반 회원 관리 모듈 및 권한 처리 구현
    - Python(RAG) - Spring Boot - React 서버 간 API 연동 및 통신 아키텍처 설계
- **백윤지 (Python, Spring Boot)**
    - Python 기반 RAG 시스템 및 API 서버 총괄 구축
    - Spring Boot 기반 공지사항 게시판 및 정책 목록/검색 기능 개발
- **박병건 (Spring Boot)**
    - Q&A 게시판 기능 개발
    - 프로젝트 전체 RDB 설계 및 구축
- **지세하 (React)**
    - React와 Tailwind CSS 기반의 프론트엔드 UI/UX 설계
    - 전체 페이지 레이아웃 및 재사용 가능한 공통 컴포넌트 시스템 개발
- **최도경 (Python)**
    - 청년 정책 데이터 수집 및 정제 파이프라인 구축
    - 수집된 데이터의 DB 자동 적재(Auto-Commit) 스크립트 개발

---

# **⚙️** 설치 및 실행 방법

## Backend (Python - SpringBoot)

### 1. 저장소 복제

Sourcetree와 같은 GUI 프로그램을 사용 중이라면 해당 프로그램을 이용하여 저장소를 복제하세요.

```powershell
# 1. 원격 저장소를 로컬에 복제합니다.
git https://github.com/hyeonn-06/ezen_project_helper.git
# 2. clone으로 생성된 프로젝트 폴더로 이동합니다.
cd ezen_project_helper
```

### 2. 가상 환경 설정

RAG, LLM 시스템을 구동하기 위해 독립적인 파이썬 가상 환경을 설정합니다.

※ PyCharm으로 실행한다면 해당 과정을 단축 시킬 수 있습니다.

```powershell
# Windows
python -m venv venv
.\venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. 필요 패키지 설치

아래 requirements.txt 파일을 프로젝트 루트 디렉토리에 생성하고 내용을 붙여넣은 뒤, 다음 명령어로 한 번에 설치합니다.

※ PyCharm을 이용한다면 [ 파일-설정-Python 인터프리터 ] 기능을 통해 설치할 수 있습니다.

```
# requirements.txt

# Web Framework
fastapi
uvicorn[standard]

# RAG & LLM Core (LangChain)
langchain
langchain-community
langchain-google-genai
langchain-huggingface
langchain-text-splitters

# VectorDB
chromadb

# NLP & Utilities
konlpy
python-dotenv
pydantic-settings
filelock

# Deep Learning Framework (for HuggingFace Embeddings)
torch

# Web Crawling & RDB
bs4
oracledb
```

```powershell
# 설치 명령어
pip install -r requirements.txt
```

### 4. 환경 변수 설정

프로젝트 루트 디렉토리에 .env 파일을 생성하고 아래와 같이 API 키를 입력합니다.

```python
GOOGLE_API_KEY="여기에_구글_API_키를_입력하세요"
HF_TOKEN="여기에_허깅페이스_토큰을_입력하세요"
```

### 5. Python 서버 실행

```python
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

### 6. Spring Boot

- IntelliJ 또는 Eclipse와 같은 IDE에서 프로젝트를 열면 Gradle이 자동으로 의존성을 설정합니다.
- 메인 애플리케이션 클래스(HelperApplication.java)를 실행하여 서버를 시작할 수 있습니다.

---

## **Frontend (React)**

### 1. 프론트엔드 디렉토리로 이동

```powershell
# 프로젝트 루트 디렉토리에서 React 폴더로 이동합니다.
cd front
```

### 2. 필요 패키지 설치

package.json 파일에 명시된 모든 의존성 라이브러리를 설치합니다.

```powershell
npm install
```

### 3. 프론트엔드 개발 서버 실행

```powershell
npm start
```
