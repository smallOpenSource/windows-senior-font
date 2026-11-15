# Noto12pt Font Setup

시니어 사용자들을 위해 Windows 10/11 환경에서 가독성과 접근성을 높이기 위해 시스템 기본 글꼴과 주요 웹 브라우저 글꼴을 **12pt · 굵기 600(SemiBold)** (`Noto Sans` / `Noto Sans KR`)으로 일괄 설정하는 포터블 스크립트입니다.

## 주요 기능

- **단일 포터블 실행 파일**: `Noto12pt-Font-Setup.cmd` 하나에 실행 스크립트와 전용 폰트 2종이 내장되어 있으며, 실행 시 SHA-256 무결성 검증 후 동작합니다.
- **DPI 인식 시스템 글꼴 적용**: Win32 API(`SystemParametersInfoW`, `SystemParametersInfoForDpi`)를 통해 디스플레이 배율(100%~200%)에 맞춘 12pt 픽셀 높이와 굵기(600)를 적용합니다.
- **웹 브라우저 글꼴 자동 설정**: Chromium 기반 브라우저의 `Preferences` 파일에 `Noto Sans` 및 `Noto Sans KR SemiBold`를 적용합니다. 브라우저가 실행 중인 경우 종료 시점을 감지해 자동으로 반영합니다.
- **안전한 백업 및 복원**: 변경 전 기존 설정을 자동 백업하며, 옵션 한 줄로 언제든 원상 복구할 수 있습니다.
- **최소 권한 분리**: 시스템 폰트 설치 단계에서만 UAC 관리자 권한을 요청합니다.

## 사용 방법

### 1. 설치 및 적용
1. `Noto12pt-Font-Setup.cmd`를 실행합니다. (폰트 설치 시 UAC 권한 승인 필요)
2. 실행 중인 브라우저가 있다면 종료 후 자동으로 글꼴 설정이 반영됩니다.
3. 시스템 글꼴 변경 사항을 완전히 적용하려면 **Windows 로그아웃 후 다시 로그인(또는 재부팅)**합니다.

### 2. 명령줄 옵션

| 명령어 | 설명 |
| :--- | :--- |
| `Noto12pt-Font-Setup.cmd` | 전용 폰트 설치 및 시스템·브라우저 12pt 글꼴 설정 적용 |
| `Noto12pt-Font-Setup.cmd /check` | 현재 시스템 및 브라우저의 글꼴 적용 상태 확인 |
| `Noto12pt-Font-Setup.cmd /restore` | 백업된 기존 글꼴 및 브라우저 설정으로 원상 복구 |

## 백업 경로 및 내장 폰트

- **백업 경로**: `%LOCALAPPDATA%\Local-PC-Management\Noto12pt\backup`
- **내장 폰트**:
  - `NotoSans-Accessibility-SemiBold.ttf`
  - `NotoSansKR-Accessibility-SemiBold.ttf`

## 라이선스

내장된 Noto Sans 글꼴은 [SIL Open Font License (OFL)](https://openfontlicense.org/)을 따릅니다.
