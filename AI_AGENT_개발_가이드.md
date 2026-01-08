# AI 코드 에이전트 & 어시스턴트를 활용한 개발

## 1. AI 코드 에이전트와 어시스턴트란?

### 1.1. 어시스턴트 (Assistant)

> **정의**: 개발자가 코드를 작성할 때 옆에서 도와주는 **'비서'**입니다.

일반적으로 ChatGPT, Gemini에게 코드 리뷰를 요청하거나 특정 모듈, 서비스 단위의 코드 작성을 요청하는 행위 등은 코드 어시스턴트를 이용하여 진행합니다.

**특징:**

| 특성 | 설명 |
|------|------|
| **수동성** | 개발자가 먼저 타이핑을 하거나 구체적인 질문을 던져야 반응합니다 |
| **제안 위주** | "이 코드는 어때요?"라고 추천하거나 한 줄을 완성해 주는 식입니다 |
| **단순 작업** | 코드 자동 완성, 주석 생성, 간단한 버그 설명 등에 특화되어 있습니다 |
| **컨텍스트 제한** | 대화 세션 내에서만 맥락을 유지하며, 프로젝트 전체를 파악하기 어렵습니다 |

---

### 1.2. 에이전트 (Agent)

> **정의**: Goal을 제시하면 스스로 Plan을 세우고 작업을 완수하는 **'동료'**입니다.

**특징:**

| 특성 | 설명 |
|------|------|
| **자율성** | "로그인 기능을 만들어줘"라고 프롬프트를 입력하면 터미널에서 직접 필요한 라이브러리를 설치하고, 테스트, 배포전략, 브랜치 전략 등을 설정합니다 |
| **도구 사용** | 파일시스템, 쉘 명령어, 브라우저 검색, MCP 연동 등을 통해 확장성 있는 작업을 수행합니다 |
| **자가 수정** | 스스로 에러를 검증하고 테스트하며 코드 리팩토링 과정을 수행합니다. Ralph Loop 기능을 통해 자신의 코드를 수차례 검증하며 작업하는 것도 가능합니다 |
| **프로젝트 인식** | 코드베이스 전체를 분석하고, 기존 패턴을 학습하여 일관된 코드를 생성합니다 |

---

### 1.3. 어시스턴트 vs 에이전트 비교

| 구분 | 어시스턴트 | 에이전트 |
|------|-----------|---------|
| **작업 방식** | 질문-응답 | 목표 지향적 자율 수행 |
| **도구 사용** | 제한적 (대화만) | 파일시스템, 터미널, 브라우저, MCP 등 |
| **컨텍스트** | 대화 세션 내 | 프로젝트 전체 |
| **에러 처리** | 사용자가 수동 수정 | 자동 감지 및 수정 시도 |
| **적합한 작업** | 코드 리뷰, 설명, 간단한 수정 | 기능 구현, 리팩토링, 프로젝트 셋업 |

---

### 1.4. Vibe Coding이란?

> **Vibe Coding**: 자연어로 원하는 것을 설명하면 AI가 코드를 생성하는 개발 방식

2025년 AI 코딩 에이전트의 발전과 함께 등장한 개념으로, 개발자가 코드의 세부 구현보다 **"무엇을 만들고 싶은지"**에 집중하는 개발 패러다임입니다.

**핵심 특징:**
- 자연어 → 코드 변환
- 반복적인 대화를 통한 점진적 개선
- AI와의 협업을 통한 빠른 프로토타이핑

---

### 1.5. AI Agent로 개발된 실제 서비스들

AI 코드 에이전트의 가능성을 보여주는 실제 사례들:

| 플랫폼 | 설명 | 링크 |
|--------|------|------|
| **Lovable** | AI로 풀스택 웹앱을 12분 만에 MVP 생성. Supabase 백엔드 자동 연동 | [lovable.dev](https://lovable.dev) |
| **Bolt.new** | 브라우저에서 바로 실행되는 풀스택 개발 환경. Node.js 런타임 내장 | [bolt.new](https://bolt.new) |
| **v0 by Vercel** | React/Next.js UI 컴포넌트를 프롬프트로 생성. shadcn/ui 기반 | [v0.dev](https://v0.dev) |
| **Replit Agent** | 클라우드 IDE에서 AI가 전체 앱을 자율적으로 구축 | [replit.com](https://replit.com) |

> 💡 **이러한 플랫폼들은 모두 "프롬프트 → 동작하는 앱"이라는 Vibe Coding의 핵심을 구현하고 있습니다.**

---

> 💡 **현 시대에는 "AI 코드 에이전트"를 얼마나 효율적으로 사용하고 명확한 프롬프트 의사전달이 가능한지가 매우 중요한 요소가 되었습니다.**

---

## 2. 대표적인 AI 코드 에이전트 도구

| 도구명 | 특징 및 강점 | 추천 대상 |
|--------|-------------|----------|
| **Cursor** | 입문용으로 가장 추천. VS Code 기반 IDE 형태라 진입장벽이 매우 낮음. Composer 모드를 통해 자연어로 여러 파일을 동시에 수정하고, 변경 사항을 시각적으로 승인(Accept) 가능 | AI 코딩에 처음 입문하는 개발자, 시각적 UI를 선호하는 분 |
| **Claude Code** | Anthropic에서 만든 터미널 전용 에이전트. 코딩 능력과 추론 능력이 매우 뛰어남. 테스트 실행, 린트 오류 수정, Git 커밋까지 터미널에서 한 번에 처리하는 'Vibe Coding'에 최적화 | 터미널 작업이 익숙하고 자율성이 높은 도구를 원하는 파워 유저 |
| **Codex CLI** | OpenAI에서 공개한 경량 오픈소스 CLI 에이전트. 프로젝트의 상태를 agent.md 파일에 기록하며 관리함. 멀티모달(스크린샷 분석) 지원과 샌드박스 환경에서의 안전한 실행이 특징 | 오픈소스를 선호하며 가벼운 터미널 기반 도구를 찾는 개발자 |
| **Gemini CLI** | 구글의 강력한 Gemini 2.5 모델을 터미널에서 사용. 100만 토큰의 대용량 컨텍스트 덕분에 매우 큰 프로젝트 분석에 유리함. 구글 검색 연동 및 무료 사용 한도가 넉넉한 것이 큰 장점 | 대규모 프로젝트를 분석해야 하거나 가성비(무료)를 중시하는 사용자 |
| **Windsurf (Codeium)** | Codeium에서 만든 AI 네이티브 IDE. Cascade 기능으로 멀티파일 편집과 자동 디버깅 지원 | 새로운 AI 네이티브 경험을 원하는 개발자 |

---

## 3. 입문자를 위한 가이드: 왜 'Cursor'인가?

처음 에이전트를 사용하신다면 **Cursor**를 가장 먼저 써보시는 것이 좋습니다.

| 이유 | 설명 |
|------|------|
| **익숙한 환경** | 전 세계에서 가장 많이 쓰는 VS Code를 기반으로 제작되어 설치와 적응이 매우 빠릅니다 |
| **시각적 피드백** | 에이전트가 코드를 어떻게 바꿨는지 빨간색/초록색(Diff)으로 바로 보여주기 때문에, AI가 실수하더라도 사용자가 즉시 바로잡기 쉽습니다 |
| **검증된 성능** | 현재 가장 활발하게 업데이트되고 있으며, 여러 LLM 모델을 전환해가며 사용 가능하여 어떤 AI가 어떤 작업에 좀 더 효율적인지 체험이 가능합니다 |
| **MCP 지원** | Model Context Protocol을 통해 외부 도구 연동이 용이합니다 |

---

## 4. 실제 개발 사례: RMS 프로젝트

> **Cursor를 사용하여 RMS Demo의 모든 Source를 개발했습니다.**

### 4.1. RMS 시스템 구조

```
┌─────────────────────────────────────────────────────────────────────────┐
│                       RMS (Remote Management System)                    │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌──────────────┐         ┌──────────────────────────────────────┐    │
│   │   Frontend   │  HTTP   │            Backend (NestJS)          │    │
│   │  React+Vite  │◄───────►│                                      │    │
│   │  shadcn/ui   │   API   │  ┌────────────┐  ┌────────────────┐  │    │
│   │  Monochrome  │         │  │  Device    │  │  Control       │  │    │
│   │  Dashboard   │         │  │  Controller│  │  Controller    │  │    │
│   └──────────────┘         │  └─────┬──────┘  └───────┬────────┘  │    │
│         ▲                  │        │                 │           │    │
│         │                  │        ▼                 ▼           │    │
│    Toast/UI                │  ┌─────────────────────────────────┐ │    │
│    피드백                   │  │         Service Layer           │ │    │
│                            │  │  (DeviceService, ControlService)│ │    │
│                            │  └────────────────┬────────────────┘ │    │
│                            │                   │                  │    │
│                            │                   ▼                  │    │
│                            │  ┌─────────────────────────────────┐ │    │
│                            │  │      TCP Gateway (Port 32200)   │ │    │
│                            │  │  ┌───────────┐ ┌──────────────┐ │ │    │
│                            │  │  │  Packet   │ │   Session    │ │ │    │
│                            │  │  │  Parser   │ │   Manager    │ │ │    │
│                            │  │  │ Big-Endian│ │  KeepAlive   │ │ │    │
│                            │  │  └───────────┘ └──────────────┘ │ │    │
│                            │  └────────────────┬────────────────┘ │    │
│                            └───────────────────┼──────────────────┘    │
│                                                │                       │
│                                                │ TCP/IP                │
│                                                │ Custom Protocol       │
│                                                ▼                       │
│   ┌────────────────────────────────────────────────────────────────┐   │
│   │                    원격제어장치 (RCS Device)                     │   │
│   │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐           │   │
│   │  │ Port 1   │ │ Port 2   │ │ Port 3   │ │ Port 4   │           │   │
│   │  │ 전원제어  │ │ 전원제어  │ │ 전원제어  │ │ 전원제어  │           │   │
│   │  │ V/A 모니터│ │ V/A 모니터│ │ V/A 모니터│ │ V/A 모니터│           │   │
│   │  └──────────┘ └──────────┘ └──────────┘ └──────────┘           │   │
│   └────────────────────────────────────────────────────────────────┘   │
│                                                                         │
│   ┌────────────────┐                                                   │
│   │    MariaDB     │◄─── Prisma ORM                                    │
│   │  ┌──────────┐  │     - Device (장치 정보)                           │
│   │  │ devices  │  │     - PowerPort (포트 상태)                        │
│   │  │ ports    │  │     - EventLog (이력/알람)                         │
│   │  │ logs     │  │                                                   │
│   │  └──────────┘  │                                                   │
│   └────────────────┘                                                   │
└─────────────────────────────────────────────────────────────────────────┘
```

### 4.2. 핵심 흐름

| 흐름 | 설명 |
|-----|------|
| **장치 연결** | RCS 장치 → TCP 32200 접속 → 서버가 `0xFF` 전송 → 장치 ID 응답 → DB 등록 |
| **상태 폴링** | 서버 → `0x11` 60초마다 → 전압/전류/상태 수신 → DB 업데이트 |
| **개별 제어** | 웹 UI → POST `/control/individual` → `0x21` 패킷 → 포트 ON/OFF |
| **일괄 제어** | 웹 UI → POST `/control/batch` → `0x22` 패킷 → 전체 포트 토글 |
| **Keep-Alive** | 장치 → `0x30` → 서버 → `ACK(0x06)` (3회 미응답 시 세션 종료) |
| **이벤트 알람** | 장치 → `0xA1~A4` (AC OFF, 온도, 전압, 전류) → EventLog 저장 + Toast |

### 4.3. 기술 스택

| 레이어 | 기술 |
|-------|------|
| **Frontend** | React + Vite + TailwindCSS + shadcn/ui |
| **Backend** | NestJS (HTTP API + TCP Server) |
| **Protocol** | Custom TCP/IP, Big-Endian, 43B Header |
| **Database** | MariaDB + Prisma ORM |
| **Monorepo** | pnpm workspace |

---

## 5. AI Agent 활용 개발 과정

### 5.1. 개발 범위

개발 과정에서 일부 추상화 전략이나 type 선언부의 불일치 같은 크리티컬하지만 작은 단위의 작업은 **직접 에디터에서 수정**을 진행했지만, 그 외 **개발환경 초기 세팅부터 API 서버 개발, Front UI 구성 등 모든 영역**에 대해 AI Agent를 활용해 개발하였습니다.

### 5.2. 모델 선택 전략

| 작업 단계 | 사용 모델 | 선택 이유 |
|----------|----------|----------|
| **Backend API 개발** | GPT o3 Codex Extra High | 대용량 Context 이해와 세션 유지 능력이 가장 뛰어남. 프로토콜 정의서 기반 개발에 적합 |
| **Frontend UI 개발** | Claude Sonnet 3.5 | 프론트엔드 UI 개발에서 가장 강력한 성능. 단, AI 모델 특성이 UI에 반영되므로 사전 라이브러리/레이아웃 지정 필요 |

### 5.3. 개발 소요 시간

- **초기 API v1 작업**: 약 **1시간** 소요 → **80% 이상** 기능 구현 완료
- 이후 변경된 프로토콜 정의서에 따라 서비스 단위, 모듈 단위 코드 리팩토링 진행

---

## 6. Cursor 에이전트 활용 상세 가이드

### 6.1. Step 1: `.cursorrules` 설정 - AI의 역할과 규칙 정의

> **`.cursorrules`는 AI Agent에게 "너는 누구이고, 어떤 규칙을 따라야 한다"를 알려주는 설정 파일입니다.**

프로젝트 루트에 `.cursorrules` 파일을 생성하여 AI의 페르소나, 기술 스택, 코딩 규칙을 정의합니다. **이 파일이 없으면 AI는 매번 다른 스타일로 코드를 생성하여 일관성이 깨집니다.**

#### `.cursorrules` 필수 구성 요소

| 섹션 | 목적 | 작성 가이드 |
|------|------|------------|
| **Project Context** | AI의 역할/페르소나 정의 | "You are an expert [분야] Developer..."로 시작. 프로젝트 목적 명시 |
| **Tech Stack** | 사용할 기술 명시 | 패키지 매니저, 프레임워크, ORM, UI 라이브러리 등 구체적 버전까지 |
| **Architecture** | 설계 패턴 강제 | 레이어 구조, 디자인 패턴, 모듈 분리 원칙 |
| **UI/UX Guidelines** | 디자인 규칙 | 컴포넌트 라이브러리, 테마, 컬러 팔레트 |
| **Database** | DB 컨벤션 | 네이밍 규칙, 필수 컬럼, 관계 정의 방식 |
| **Coding Rules** | 코딩 스타일 | 금지 패턴, 필수 패턴, 에러 처리 방식 |
| **File Structure** | 파일 구조 규칙 | 디렉토리 구조, 파일 네이밍, 모듈 분리 기준 |
| **Testing** | 테스트 범위 | 단위 테스트 대상, E2E 범위, 커버리지 기준 |

#### 실제 RMS 프로젝트에서 사용한 `.cursorrules` 전문:

```markdown
# Project Context

You are an expert Full Stack Developer specializing in Node.js, NestJS, 
React, and IoT/TCP communication protocols. You are building a Web-based 
Control System for a Remote Power Control Unit (RCS).

# Tech Stack

- Package Manager: pnpm
- Backend: NestJS (Microservices/TCP + HTTP), Prisma ORM, MariaDB
- Frontend: React (Vite), TailwindCSS, shadcn/ui
- Language: TypeScript (Strict mode)

# Architecture & Design Patterns

- **Monorepo-like Structure:** Ensure backend and frontend can be launched 
  simultaneously (e.g., via Concurrently or Nx).
- **TCP Server:** The NestJS backend acts as a TCP SERVER. The device (RCS) 
  connects to this server as a CLIENT.
- **Hexagonal Architecture:** Separate Protocol logic (TCP parsing) from 
  Business logic (Service layer).

# UI/UX Guidelines

- Use **shadcn/ui** components exclusively.
- **Theme:** Strict Black & White (Monochrome). No colorful accents unless 
  indicating critical errors (Red) or active status (Black/Bold).
- **Layout:** Clean, grid-based dashboard.
- **Feedback:** Use 'Sonner' or 'Toast' for ACK/NAK responses from the device.

# Database (Prisma)

- Use snake_case for DB columns, camelCase for TS fields.
- Store `last_connected_at` for devices.
- Store `raw_packet` in logs for debugging TCP issues.
- EventLog types must include CONTROL, STATUS, EVENT_A1~A4, RESET, FW_UPDATE.

# Coding Rules

- Use `Buffer` methods (`readUInt16BE`, `writeUInt32BE`) for all packet manipulation.
- Create a dedicated `PacketParser` class.
- Use NestJS `Gateway` or `Microservice` strategy for TCP.
- Ensure type safety for all OpCodes using Enums.
- Device handshake, Keep-Alive ACK, and Event dispatch must live in separate 
  hexagonal adapters; services never parse raw Buffers directly.

# Workspace Commands

- Root `pnpm dev` must launch `apps/server start:dev` and `apps/web dev` concurrently.
- Root `pnpm build` runs `server build` first, then `web build`.

# Testing Expectations

- Provide unit tests for PacketParser (header parsing/build) and DeviceSync services.
- Add integration/e2e coverage for the TCP Keep-Alive → ACK flow plus HTTP `/health`.
```

#### `.cursorrules` 작성 Best Practices

| Do ✅ | Don't ❌ |
|-------|---------|
| 구체적인 기술 버전 명시 | 모호한 표현 ("최신 버전 사용") |
| 금지 패턴 명확히 정의 | 규칙 없이 자유롭게 허용 |
| 실제 코드 예시 포함 | 설명만으로 규칙 전달 |
| 에러 처리 방식 지정 | 에러 처리를 AI에게 위임 |
| 파일 위치 규칙 명시 | 파일 구조를 AI가 결정하게 함 |

---

### 6.2. Step 2: `project.mdc` 작성 - 상세 기능 명세서

> **`project.mdc`는 AI Agent가 참조할 "프로젝트 설계 문서"입니다.**

`.cursorrules`가 **"규칙"**이라면, `project.mdc`는 **"무엇을 만들어야 하는지"**에 대한 상세 스펙입니다.

#### `project.mdc` vs `.cursorrules` 역할 구분

| 구분 | `.cursorrules` | `project.mdc` |
|------|---------------|---------------|
| **목적** | AI의 행동 규칙 | 프로젝트 기능 명세 |
| **내용** | 코딩 컨벤션, 금지 패턴 | 기능 요구사항, 데이터 모델 |
| **변경 빈도** | 프로젝트 초기 설정 후 거의 변경 안함 | 기능 추가/변경 시 업데이트 |
| **예시** | "snake_case 사용" | "Device 모델에 lastConnectedAt 필드 추가" |

#### `project.mdc` 필수 구성 요소

```markdown
---
alwaysApply: true  # 항상 AI 컨텍스트에 포함
---

# 1. 프로젝트 개요
- 시스템 목표
- 핵심 기능 목록
- 기술 스택 요약

# 2. 실행 환경
- 설치 명령어
- 환경 변수 (.env)
- 실행 명령어

# 3. 데이터베이스 설계
- 모델 정의 (실제 코드 예시)
- 관계 정의
- 인덱스 전략

# 4. API 명세
- 엔드포인트 목록
- Request/Response 형식
- 에러 코드 정의

# 5. 비즈니스 로직
- 핵심 플로우 설명
- 상태 전이 다이어그램
- 예외 케이스 처리

# 6. 외부 연동 (해당 시)
- 프로토콜 명세
- 패킷 구조
- 타이밍 다이어그램
```

#### 실제 RMS 프로젝트의 `project.mdc` 구조:

```markdown
---
alwaysApply: true
---

# 1. 프로젝트 개요 및 아키텍처

## 1.1. 시스템 개요
목표: 원격제어장치(RCS)에 연결된 4개의 장비 전원을 웹 인터페이스를 통해 
개별/일괄 제어 및 상태 모니터링.

핵심 기능:
- TCP 서버 구동 및 장비(클라이언트) 연결 수용
- 초기 인증(0xFF) 및 Keep-Alive/Status Poll 유지
- 웹 UI 기반 개별 포트(1~4번) 전원 ON/OFF 제어 (OpCode 0x21)
- 전체 포트 일괄 ON/OFF 제어 (OpCode 0x22)
- 제어 이력 및 장애 이벤트 로깅

## 1.3. 실행 & 환경 정리
- `pnpm install` (workspace 루트에서 단 한 번 실행)
- `pnpm dev` → server + web 동시 실행
- `.env` 필수 키:
  ```
  DATABASE_URL="mysql://rcs_user:password@127.0.0.1:3306/rcs"
  TCP_SENDER_IP="10.10.10.10"
  STATUS_POLL_INTERVAL_MS=60000
  HTTP_PORT=3000
  TCP_PORT=32200
  ```

# 2. 상세 기획서 (Functional Specification)

## 2.1. 데이터베이스 설계 (Prisma Schema)

model Device {
  deviceId        String       @id                @map("device_id")
  stationNumber   String       @unique            @map("station_number")
  ipAddress       String                          @map("ip_address")
  status          DeviceStatus @default(OFFLINE)  @map("status")
  statusBitmap    Int?                            @map("status_bitmap")
  lastConnectedAt DateTime?                       @map("last_connected_at")
  createdAt       DateTime     @default(now())    @map("created_at")
  updatedAt       DateTime     @updatedAt         @map("updated_at")
  ports           PowerPort[]
  logs            EventLog[]
  @@map("devices")
}

# 3. 프로토콜 구현 상세 가이드

## Header Structure (43 Bytes, Big-Endian)

| Offset | Field | Length | Description |
|--------|-------|--------|-------------|
| 0 | Sender IP | 16B | 송신측 IP, `0x2D`('-')로 패딩 |
| 16 | Dest IP | 16B | 수신측 IP, 동일 패딩 |
| 32 | Controller Kind | 2B | 항상 "RC" (0x5243) |
| 34 | Station Number | 4B | 장비에서 Echo |
| 38 | Total Length | 4B | OpCode + Data 길이 |
| 42 | OpCode | 1B | 명령 식별자 |

## OpCodes
| OpCode | 명령 | Data 구조 |
|--------|------|-----------|
| 0xFF | Device ID Request | - |
| 0x11 | Status Request | Response: Bitmap(1) + V(2) + A(2) × 4 |
| 0x21 | Individual Control | Port(1) + OnOff(1) |
| 0x22 | Batch Control | OnOff(1) |
| 0x30 | Keep-Alive | Response: ACK(0x06) |
```

---

### 6.3. Step 3: MCP (Model Context Protocol) 활용

> **MCP는 AI Agent가 외부 도구와 데이터 소스에 접근할 수 있게 해주는 프로토콜입니다.**

#### MCP란?

MCP(Model Context Protocol)는 AI 모델이 외부 도구, 데이터베이스, API 등과 상호작용할 수 있게 해주는 표준 프로토콜입니다. Cursor에서 MCP를 활용하면 AI가 더 정확하고 최신의 정보를 기반으로 코드를 생성할 수 있습니다.

#### 주요 MCP 서버들

| MCP 서버 | 기능 | 활용 사례 |
|---------|------|----------|
| **Context7** | 라이브러리 공식 문서 실시간 조회 | 최신 API 문법 확인, 버전별 차이 파악 |
| **Sequential Thinking** | 복잡한 문제를 단계별로 분해 | 대규모 기능 구현, 아키텍처 설계 |
| **Filesystem** | 파일시스템 직접 조작 | 파일 생성/수정/삭제 자동화 |
| **GitHub** | GitHub API 연동 | PR 생성, 이슈 관리, 코드 리뷰 |
| **PostgreSQL/MySQL** | 데이터베이스 직접 쿼리 | 스키마 분석, 데이터 조회 |

#### Context7 MCP 설정 방법

Context7은 AI가 라이브러리의 **최신 공식 문서**를 실시간으로 참조할 수 있게 해줍니다. 이를 통해 **할루시네이션을 방지**하고 **정확한 API 사용법**을 얻을 수 있습니다.

**Cursor에서 Context7 설정:**

1. `~/.cursor/mcp.json` 파일 생성/편집:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp", "--api-key", "YOUR_API_KEY"]
    }
  }
}
```

2. **또는** 원격 서버 방식:

```json
{
  "mcpServers": {
    "context7": {
      "url": "https://mcp.context7.com/mcp",
      "headers": {
        "CONTEXT7_API_KEY": "YOUR_API_KEY"
      }
    }
  }
}
```

#### Sequential Thinking MCP 활용

복잡한 문제를 체계적으로 분해하여 해결하는 MCP 서버입니다.

**설정:**
```json
{
  "mcpServers": {
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    }
  }
}
```

**활용 예시:**
```
"TCP 서버 구현"이라는 큰 목표를 다음과 같이 분해:
1. 인터페이스 정의 → 2. 상수 정의 → 3. 파서 구현 → 
4. Gateway 구현 → 5. 테스트 작성 → 6. 통합 테스트
```

#### MCP 활용 Best Practices

| 상황 | 추천 MCP | 이유 |
|------|---------|------|
| 새 라이브러리 사용 | Context7 | 공식 문서 기반 정확한 API 사용 |
| 복잡한 기능 구현 | Sequential Thinking | 단계별 접근으로 오류 감소 |
| DB 스키마 파악 | Database MCP | 실제 스키마 기반 코드 생성 |
| 대규모 리팩토링 | Filesystem + Sequential | 파일 구조 파악 + 단계별 수정 |

---

### 6.4. Step 4: 프로토콜 명세서 변환

> **PDF 문서를 AI가 이해할 수 있는 형태로 변환해야 합니다.**

#### 문제점

AI Agent는 PDF 파일을 직접 읽기 어렵습니다. 특히 바이트 레벨의 프로토콜 정의서는 표, 다이어그램이 많아서 단순 텍스트 추출로는 정보가 손실됩니다.

#### 해결 방법

1. **pypdf 또는 pdfplumber로 텍스트 추출**
2. **표 형태의 데이터는 마크다운 테이블로 재구성**
3. **바이트 오프셋, 필드 길이 등을 명확히 정리**
4. **실제 바이트 값 예시 포함** (16진수)

#### 변환 예시

**원본 PDF 내용:**
```
프레임 구조
| 필드명 | 길이 | 설명 |
| Sender IP | 16 | 송신측 IP, 미사용 바이트는 '-'로 패딩 |
...
```

**변환 후 (project.mdc에 포함):**
```markdown
## Header Structure (43 Bytes, Big-Endian)

| Offset | Field | Length | Description | Example |
|--------|-------|--------|-------------|---------|
| 0 | Sender IP | 16B | 송신측 IP, `0x2D`('-')로 패딩 | `10.10.10.10----` |
| 16 | Dest IP | 16B | 수신측 IP, 동일 패딩 규칙 | `192.168.1.1----` |
| 32 | Controller Kind | 2B | 항상 "RC" (`0x5243`) | `0x52 0x43` |
| 34 | Station Number | 4B | 장비에서 수신한 값을 Echo | `0x00 0x00 0x00 0x01` |
| 38 | Total Length | 4B | OpCode(1) + Data(N) 길이 | `0x00 0x00 0x00 0x03` |
| 42 | OpCode | 1B | 명령 식별자 | `0x21` |
| 43~ | Data | Variable | 페이로드 | `0x01 0x01` |

### 실제 패킷 예시 (Individual Control - Port 1 ON)
```
52 43 00 00 00 01 00 00 00 03 21 01 01
│  │  │           │           │  │  └─ Status: ON (0x01)
│  │  │           │           │  └─ Port: 1 (0x01)  
│  │  │           │           └─ OpCode: Individual Control (0x21)
│  │  │           └─ Total Length: 3 (OpCode + 2 bytes data)
│  │  └─ Station Number: 1
│  └─ Controller Kind: "RC"
└─ (Header 앞부분 생략)
```
```

---

### 6.5. Step 5: 효과적인 프롬프팅 기법

> ⚠️ **AI Agent에게 단순히 "회원가입 만들어줘!"라고 지시하면 할루시네이션이 발생합니다.**

기존 코드 구조를 파악하지 못한 채 세션 기반인지 토큰 기반인지를 임의로 결정하여 개발하는 문제가 생깁니다.

#### ❌ 나쁜 프롬프트 예시

```
회원가입 기능 만들어줘
```

**문제점:**
- 인증 방식을 AI가 임의로 결정 (세션? JWT? OAuth?)
- 기존 코드 컨벤션 무시
- 파일 위치를 제멋대로 결정
- 에러 처리 방식 불일치

#### ✅ 좋은 프롬프트 예시

```markdown
## 요청: 회원가입 기능 구현

### 1. 기술 스택
- Framework: NestJS
- ORM: Prisma
- Database: MariaDB
- 인증 방식: JWT 토큰 기반 (Access Token + Refresh Token)

### 2. 아키텍처 패턴
- Controller → Service → Repository 패턴 적용
- DTO 검증: class-validator 사용
- 비밀번호 암호화: bcrypt (salt rounds: 10)

### 3. 코드 컨벤션
- 파일명: kebab-case (예: auth.controller.ts)
- 클래스명: PascalCase (예: AuthService)
- 메서드명: camelCase (예: createUser)
- DB 컬럼: snake_case (@map 데코레이터 사용)
- TS 필드: camelCase

### 4. 파일 위치
- Controller: src/auth/auth.controller.ts
- Service: src/auth/auth.service.ts
- DTO: src/auth/dto/signup.dto.ts
- Entity: src/auth/entities/user.entity.ts

### 5. 기존 코드 참고
- 기존 컨트롤러 구조: src/device/device.controller.ts 참고
- 에러 처리: HttpException 사용 (기존 패턴 유지)
- Response 형식: { success: boolean, data: T, message?: string }

### 6. 구현 요구사항
- 이메일 중복 체크
- 비밀번호 최소 8자, 특수문자 포함
- 가입 완료 시 Access Token + Refresh Token 반환
```

#### 프롬프트 필수 체크리스트

| 항목 | 설명 | 미지정 시 문제 |
|------|------|--------------|
| **기술 스택** | 사용할 프레임워크, 라이브러리 | AI가 임의의 라이브러리 설치 |
| **아키텍처** | 레이어 구조, 디자인 패턴 | 일관성 없는 코드 구조 |
| **인증 방식** | 세션/토큰, 구체적인 전략 | JWT vs Session 혼재 |
| **코드 컨벤션** | 네이밍 규칙, 파일 구조 | 기존 코드와 스타일 불일치 |
| **파일 위치** | 생성할 파일의 정확한 경로 | 엉뚱한 위치에 파일 생성 |
| **참고 코드** | 기존 유사 코드 경로 | 프로젝트 패턴 무시 |
| **에러 처리** | 예외 처리 방식 | 에러 핸들링 방식 불일치 |
| **응답 형식** | API Response 구조 | 응답 포맷 불일치 |

---

### 6.6. Step 6: 파일 크기 관리 - ~500줄 원칙

> 💡 **각 파일의 코드를 약 500줄 이하로 유지하는 것이 매우 중요합니다.**

#### 왜 500줄인가?

| 문제 | 설명 |
|------|------|
| **Context Window 제한** | LLM 모델은 한 번에 처리할 수 있는 토큰 수에 제한이 있습니다. 파일이 너무 길면 AI가 전체 맥락을 파악하지 못합니다 |
| **이해도 저하** | 500줄을 넘어가면 AI가 코드베이스 구조를 정확히 이해하기 어려워집니다 |
| **할루시네이션 증가** | 긴 파일에서는 AI가 존재하지 않는 함수나 변수를 참조하는 오류가 빈번합니다 |
| **수정 정확도 감소** | AI가 파일의 일부만 보고 수정하여 다른 부분과 충돌 발생 |

#### 파일 분리 기준

| 줄 수 | 상태 | 조치 |
|------|------|------|
| **~300줄** | ✅ 양호 | 유지 |
| **300~500줄** | ⚠️ 주의 | 분리 검토 |
| **500줄 이상** | ❌ 위험 | **즉시 분리 필요** |

#### 분리 전략

**❌ 비권장: 하나의 거대한 파일**
```
src/
└── auth/
    └── auth.service.ts  (1500줄 - 모든 로직이 한 파일에)
```

**✅ 권장: 책임별 분리**
```
src/
└── auth/
    ├── auth.controller.ts      (~100줄) - HTTP 라우팅만
    ├── auth.service.ts         (~150줄) - 비즈니스 로직 조합
    ├── services/
    │   ├── token.service.ts    (~100줄) - JWT 생성/검증
    │   ├── password.service.ts (~80줄)  - 암호화/검증
    │   └── email.service.ts    (~100줄) - 이메일 발송
    ├── strategies/
    │   ├── jwt.strategy.ts     (~50줄)
    │   └── local.strategy.ts   (~50줄)
    ├── guards/
    │   └── jwt-auth.guard.ts   (~30줄)
    └── dto/
        ├── signup.dto.ts       (~40줄)
        ├── login.dto.ts        (~30줄)
        └── token.dto.ts        (~20줄)
```

#### RMS 프로젝트 실제 파일 구조

```
apps/server/src/
├── tcp/
│   ├── tcp.gateway.ts              (~100줄) - 연결 관리
│   ├── tcp.module.ts               (~30줄)
│   ├── packet/
│   │   ├── packet-parser.ts        (~170줄) - 패킷 파싱/생성
│   │   └── packet-parser.spec.ts   - 테스트
│   ├── services/
│   │   ├── device-session.service.ts    (~80줄)
│   │   ├── keepalive-monitor.service.ts (~100줄)
│   │   └── tcp-message-dispatcher.service.ts (~120줄)
│   ├── interfaces/
│   │   ├── packet.interface.ts     (~40줄)
│   │   └── device-session.interface.ts (~20줄)
│   ├── enums/
│   │   └── opcode.enum.ts          (~20줄)
│   ├── constants/
│   │   └── tcp.constants.ts        (~30줄)
│   └── errors/
│       └── packet-parser.error.ts  (~15줄)
├── device/
│   ├── device.controller.ts        (~100줄)
│   ├── device.service.ts           (~150줄)
│   ├── device.module.ts            (~25줄)
│   └── dto/
│       ├── device.dto.ts           (~60줄)
│       └── event.dto.ts            (~50줄)
└── control/
    ├── control.controller.ts       (~130줄)
    ├── control.service.ts          (~120줄)
    └── dto/
        └── control.dto.ts          (~80줄)
```

---

### 6.7. Step 7: 단계별 작업 분리

> **큰 기능을 한 번에 요청하지 말고, 작은 단위로 나누어 요청하세요.**

#### ❌ 나쁜 예시: 한 번에 모든 것 요청

```
TCP 서버 전체를 만들어줘. 패킷 파싱, 세션 관리, Keep-Alive, 
이벤트 처리, DB 저장까지 전부 구현해줘.
```

#### ✅ 좋은 예시: 단계별 요청

**1단계: 인터페이스/타입 정의**
```
TCP 패킷 구조를 위한 TypeScript 인터페이스를 정의해줘.
- PacketHeader: senderIp, destIp, controllerKind, stationNumber, totalLength, opcode
- ParsedPacket: header, data, raw
위치: src/tcp/interfaces/packet.interface.ts
```

**2단계: 상수 정의**
```
TCP 패킷 관련 상수를 정의해줘.
- HEADER_LENGTH: 43
- 각 필드별 길이
- PADDING_CHAR: '-'
위치: src/tcp/constants/tcp.constants.ts
```

**3단계: 핵심 로직 구현**
```
PacketParser 클래스를 구현해줘.
- parse(buffer: Buffer): ParsedPacket
- build(options: PacketBuildOptions): Buffer
- Big-Endian 방식 사용
- Buffer.readUInt16BE, writeUInt32BE 메서드 활용
위치: src/tcp/packet/packet-parser.ts
기존 인터페이스 참고: src/tcp/interfaces/packet.interface.ts
```

**4단계: 테스트 작성**
```
PacketParser에 대한 단위 테스트를 작성해줘.
- 정상적인 패킷 파싱
- 불완전한 버퍼 예외 처리
- 패킷 빌드 후 파싱 일치 확인
위치: src/tcp/packet/packet-parser.spec.ts
```

---

## 7. 자주 발생하는 문제와 해결책

### 7.1. 할루시네이션 (Hallucination)

| 증상 | 원인 | 해결책 |
|------|------|--------|
| 존재하지 않는 함수 호출 | 파일이 너무 길어 전체를 못 읽음 | 파일 500줄 이하 유지 |
| 없는 라이브러리 import | Context에 package.json이 없음 | 의존성 명시적으로 알려주기 |
| 엉뚱한 타입 사용 | 기존 타입 정의 파일을 못 참조 | 관련 인터페이스 경로 명시 |
| 구버전 API 사용 | 최신 문서 참조 불가 | **Context7 MCP 활용** |

### 7.2. 일관성 없는 코드

| 증상 | 원인 | 해결책 |
|------|------|--------|
| 네이밍 규칙 불일치 | .cursorrules 미설정 | 코드 컨벤션 규칙 파일 작성 |
| 아키텍처 패턴 혼재 | 아키텍처 명시 안 함 | project.mdc에 패턴 정의 |
| 에러 처리 방식 다름 | 기존 코드 참조 안 함 | 참고할 기존 파일 경로 제공 |

### 7.3. 기존 코드와 충돌

| 증상 | 원인 | 해결책 |
|------|------|--------|
| 중복 함수 생성 | 기존 유틸리티 모름 | 기존 유틸리티 파일 경로 알려주기 |
| 타입 재정의 | 공통 타입 파일 모름 | types/ 디렉토리 구조 설명 |
| 설정 충돌 | 기존 설정 무시 | tsconfig, eslint 설정 참조 지시 |

---

## 8. 핵심 정리

### AI Agent 활용 성공 공식

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   명확한 규칙 설정 (.cursorrules)                        │
│              +                                          │
│   상세한 스펙 문서 (project.mdc)                         │
│              +                                          │
│   MCP 활용 (Context7, Sequential Thinking)              │
│              +                                          │
│   구체적인 프롬프트 (아키텍처/컨벤션 명시)                 │
│              +                                          │
│   적절한 파일 크기 (~500줄)                              │
│              +                                          │
│   단계별 작업 분리                                       │
│              =                                          │
│   ✅ 효율적인 AI Agent 개발                              │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### 최종 체크리스트

- [ ] `.cursorrules` 파일에 프로젝트 규칙 정의 완료
- [ ] `project.mdc` 파일에 상세 기능 명세 작성 완료
- [ ] MCP 서버 설정 (Context7, Sequential Thinking 등)
- [ ] 프로토콜/스펙 문서를 AI가 이해하기 쉬운 마크다운으로 변환
- [ ] 프롬프트 작성 시 기술스택, 아키텍처, 컨벤션 명시
- [ ] 파일당 500줄 이하 유지
- [ ] 큰 기능은 작은 단위로 분리하여 요청
- [ ] 작업별 적합한 LLM 모델 선택 (Backend: GPT, Frontend: Claude 등)
- [ ] 기존 코드 참조 경로 명시

---

## 9. 부록

### A. `.cursorrules` 템플릿

```markdown
# Project Context

You are an expert [분야] Developer specializing in [기술스택].
You are building [프로젝트 설명].

# Tech Stack

- Package Manager: [npm/yarn/pnpm]
- Backend: [프레임워크], [ORM], [DB]
- Frontend: [프레임워크], [스타일링], [UI 라이브러리]
- Language: TypeScript (Strict mode)

# Architecture & Design Patterns

- [아키텍처 패턴 설명]
- [레이어 구조 설명]
- [모듈 분리 원칙]

# Coding Rules

- [네이밍 규칙]
- [금지 패턴]
- [필수 패턴]
- [에러 처리 방식]

# File Structure Rules

- Controllers: src/[module]/[module].controller.ts
- Services: src/[module]/[module].service.ts
- DTOs: src/[module]/dto/[name].dto.ts
- Interfaces: src/[module]/interfaces/[name].interface.ts

# Testing Expectations

- Unit tests for [대상]
- Integration tests for [대상]
- E2E tests for [대상]
```

### B. 상황별 프롬프트 템플릿

#### 새로운 API 엔드포인트 추가

```markdown
## 요청: [기능명] API 엔드포인트 추가

### HTTP 스펙
- Method: [GET/POST/PUT/DELETE]
- Path: /api/v1/[resource]
- Request Body: { ... }
- Response: { success: boolean, data: T }

### 기술 요구사항
- Controller: src/[module]/[module].controller.ts에 추가
- Service: src/[module]/[module].service.ts에 로직 구현
- DTO: src/[module]/dto/[name].dto.ts 생성

### 참고 코드
- 기존 엔드포인트 예시: src/device/device.controller.ts의 findAll 메서드

### 주의사항
- 기존 에러 처리 패턴 유지 (HttpException 사용)
- Swagger 데코레이터 필수 (@ApiOperation, @ApiResponse)
```

#### 버그 수정 요청

```markdown
## 요청: [버그 설명] 수정

### 현재 동작
[현재 어떻게 동작하는지]

### 기대 동작
[어떻게 동작해야 하는지]

### 재현 방법
1. [단계 1]
2. [단계 2]

### 관련 파일
- [파일 경로 1]
- [파일 경로 2]

### 수정 범위
- 최소한의 변경으로 수정
- 기존 로직 리팩토링 금지
- 해당 버그만 수정
```

#### 리팩토링 요청

```markdown
## 요청: [대상] 리팩토링

### 현재 문제점
- [문제 1]
- [문제 2]

### 리팩토링 목표
- [목표 1]
- [목표 2]

### 제약 조건
- 기존 public API (함수 시그니처) 유지
- 기존 테스트 통과 필수
- 파일당 500줄 이하 유지

### 적용할 패턴
- [디자인 패턴명]
- [참고할 기존 코드 경로]
```

### C. MCP 설정 파일 예시

**~/.cursor/mcp.json:**
```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp", "--api-key", "YOUR_API_KEY"]
    },
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "--root", "/path/to/project"]
    }
  }
}
```

---

## 10. 참고 자료

### 공식 문서
- [Cursor Documentation](https://docs.cursor.com)
- [Context7 MCP](https://context7.com)
- [Model Context Protocol](https://modelcontextprotocol.io)
- [awesome-cursorrules (GitHub)](https://github.com/PatrickJS/awesome-cursorrules)

### AI App Builder 플랫폼
- [Lovable](https://lovable.dev) - AI 풀스택 앱 빌더
- [Bolt.new](https://bolt.new) - 브라우저 기반 AI 개발 환경
- [v0.dev](https://v0.dev) - Vercel의 AI UI 생성기
- [Replit](https://replit.com) - 클라우드 AI 개발 환경
