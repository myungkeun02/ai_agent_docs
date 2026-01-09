# 📘 Cursor AI Agent 사용 매뉴얼
## (캡처 위치 포함 템플릿)

---

## 0. 문서 정보

| 항목 | 내용 |
|----|----|
| 문서명 | Cursor AI Agent 사용 매뉴얼 |
| 작성 목적 | AI Agent 기반 프로젝트 표준 개발 프로세스 정립 |
| 대상 | 개발자 / 기획자 / 협업 인원 |
| 작성일 | 2026-01-09 |
| 버전 | v1.1 |

---

## 1️⃣ Cursor 실행 및 프로젝트 디렉토리 열기

Cursor IDE를 실행한 뒤 작업할 프로젝트 디렉토리를 연다.  
이 디렉토리는 Git 저장소 루트이거나 실제 개발이 이루어질 최상위 폴더여야 한다.
<img width="2310" height="1221" alt="image" src="https://github.com/user-attachments/assets/d941b9cf-570f-4f43-9448-18403d0fd714" />

**프로젝트 디렉토리 선택**
<img width="1894" height="1100" alt="image" src="https://github.com/user-attachments/assets/741bd8ef-cec6-48d5-b5ff-1a3f1047afd3" />


---

## 2️⃣ 모델 설정 및 Agent 모드 진입

### (Cursor Rules / project.mdc 작성)

### 설명
AI Agent가 프로젝트를 정확히 이해하도록  
모델 선택 후 Agent 모드에서 프로젝트 규칙을 정의한다.
<img width="1193" height="943" alt="image" src="https://github.com/user-attachments/assets/193d5ba9-2a58-4478-b36b-006c3bda5e46" />

### 요청 프롬프트 예시
<img width="1270" height="762" alt="image" src="https://github.com/user-attachments/assets/73d169cd-d4ea-4124-90e4-94c207dfba58" />

보통 한번에 결과물이 잘 나오는 경우가 드물기에 프로젝트에 대한 질문을 AI에게 요청하는것이 좋음
<img width="1271" height="781" alt="image" src="https://github.com/user-attachments/assets/45755604-e52d-4694-8ebd-dcec8ccfd755" />

프로젝트 세팅을 Cursor가 파일시스템에 직접 접근하여 진행하게 된다.
<img width="1273" height="997" alt="image" src="https://github.com/user-attachments/assets/42930f32-7159-45eb-ae7b-0d449805d98f" />


**Rules / project.mdc 생성 결과**
<img width="2295" height="1297" alt="image" src="https://github.com/user-attachments/assets/7318932b-f041-4dd6-bc27-78136d450d77" />


## 3️⃣ Plan 모드 전환 및 개발 계획 수립

### 설명
정의된 프로젝트 규칙을 기반으로  
AI에게 개발 단계(Task)와 마일스톤 생성을 요청한다.

**Plan Mode 전환**
<img width="691" height="475" alt="image" src="https://github.com/user-attachments/assets/3a21d76b-aa80-4e32-93c4-25a8077a4460" />

### 요청 프롬프트 예시
<img width="918" height="268" alt="image" src="https://github.com/user-attachments/assets/081af485-ea4e-4a4b-9db1-83a0e5303695" />

mdc. roles 생성과 동일하게 질문을 요청한다. Plan 모드에서는 질문에 의한 답변을 사용자가 선택하게끔 Questions를 제시해주는데 해당하는 사항을 선택하여 진행한다. (다른 요청사항을 추가하는것 또한 가능하다)
<img width="936" height="455" alt="image" src="https://github.com/user-attachments/assets/c2d5a33e-cdc3-4b70-b0c2-cf66c1353cac" />
<img width="1058" height="552" alt="image" src="https://github.com/user-attachments/assets/c5677120-c56e-4c8f-b368-482149fb1cbd" />


### 📸 캡처 3-2
**개발 플랜(Task) 생성 결과**

<img width="2153" height="1256" alt="image" src="https://github.com/user-attachments/assets/9037ab66-5357-4e4a-8546-47f4caf1057f" />

### 운영 원칙
- ❌ 모호한 답변 금지  
- ✅ Cursor 질문에 의사결정 형태로 응답

---

## 4️⃣ AI Agent에게 개발 위임 (Execution)

### 설명
확정된 개발 계획을 기반으로  
AI Agent에게 실제 개발 작업을 위임한다. Plan 상태에서 Build를 클릭하거나 Agent 모드로 전환해 플랜에 맞춰 로컬에서 작업할것을 요청한다.
<img width="1190" height="1128" alt="image" src="https://github.com/user-attachments/assets/6475dd5d-f418-4b59-9f52-686cb5fc9d4c" />

### 📸 캡처 4-2
**Agent 작업 진행 화면**

<img width="909" height="567" alt="image" src="https://github.com/user-attachments/assets/fd1ac2ea-688a-4cbb-aa03-13a5622789ee" />

### 주의 사항
- ❌ 전체 작업 일괄 위임  
- ✅ Task 단위 순차 진행

## 4 디버깅 및 기능 추가

처음부터 완벽한 프로덕트가 생성되지 않으니 발생하는 에러 Alret를 그대로 복사하여 전달한다.
<img width="2169" height="1345" alt="image" src="https://github.com/user-attachments/assets/3c27888e-7e70-4959-b26c-914b9c0de9d3" />

고쳐내라고 한다.
<img width="832" height="353" alt="image" src="https://github.com/user-attachments/assets/3a67a7f1-787f-4201-8862-8881649feb12" />

고쳐냄
<img width="2096" height="1094" alt="image" src="https://github.com/user-attachments/assets/c9f597e8-ea1d-4a5c-a5d5-1779f733bf7c" />


- project.mdc
- .cursorrules

---

**END OF DOCUMENT**

