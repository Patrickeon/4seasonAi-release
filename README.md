# 🚀 4seasonAi-release 자동 배포 가이드

4seasonAI는 **AI 기반 교육 플랫폼**으로, **Svelte + Electron**을 활용하여 제작된 데스크탑 애플리케이션입니다.

macOS / Windows 업데이트 TAG 생성 후 필수 파일 업로드시 4seasonAi 실행시 자동으로 버젼을 체크 하여 업데이트 합니다.

---

## 주요 기능

- ✅ 업데이트

---

---

## 📦 1. 빌드(Build)
✅ 기본 조건
- Node.js (최소 18.x 권장)
- Electron-builder
- cross-env
- Git CLI

이 프로젝트는 electron-builder를 사용하여 플랫폼별 앱을 빌드합니다.

## 🛠️ 빌드 명령어
- Window 전용 빌드
```text
npm run dist --win
```

- Mac 전용 빌드
```text
npm run dist --mac
```

- Mac, Window 전용 빌드
```text
npm run dist -- --mac --win
```

## 📁 배포용 릴리스 파일 목록 (Git Tag 또는 GitHub Release에 포함해야 할 파일들)

> 빌드 디렉토리: `release/`

### ✅ Windows (x64 or arm64)
- `release/4seasonAI Setup 0.0.0.exe`  
- `release/4seasonAI Setup 0.0.0.exe.blockmap`
- `release/latest.yml`

### ✅ macOS (ARM64)

> `.zip`과 `.dmg` 중 하나만 업로드해도 되지만, **dmg 우선** 권장

- `release/4seasonAI-0.0.0-arm64-mac.zip`  
- `release/4seasonAI-0.0.0-arm64-mac.zip.blockmap`  
- `release/4seasonAI-0.0.0-arm64.dmg`  
- `release/4seasonAI-0.0.0-arm64.dmg.blockmap`  
- `release/latest-mac.yml`

✅ **Tip**: 자동 업데이트를 지원하려면 반드시 `latest.yml`과 `latest-mac.yml` 파일이 릴리스에 포함되어야 합니다.

📝 **버전 예시**:  
Git 태그는 앱 버전과 동일하게 설정해주세요. 예: `v0.0.0`

---
