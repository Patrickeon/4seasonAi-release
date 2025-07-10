# 🚀 4seasonAi-release 자동 배포 가이드

4seasonAI는 **AI 기반 교육 플랫폼**으로, **Svelte + Electron**을 활용하여 제작된 데스크탑 애플리케이션입니다.

macOS / Windows 업데이트 TAG 생성 후 필수 파일 업로드시 4seasonAi 실행시 자동으로 버젼을 체크 하여 업데이트 합니다.

---

## 주요 기능

- ✅ 업데이트

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

## 2. 🖥️ GitHub UI에서 릴리스 생성 및 Git Tag 만들기


UI를 통해 Git Tag를 생성하고, 동시에 릴리스 파일을 업로드할 수 있습니다.

### ✅ 단계별 가이드

1. **GitHub 저장소 접속**  
   `https://github.com/Patrickeon/4seasonAi-release`

2. 상단 메뉴에서 ➡️ **Releases** 탭 클릭  
   또는 브라우저 주소창에 아래 주소 입력

3. 우측 상단의 **[Draft a new release]** 버튼 클릭

4. **Tag version** 입력  
예: `v0.0.0`  
👉 이미 존재하는 태그가 없으면 여기서 새로 생성됩니다.

5. **Target** 브랜치 선택 (기본값: `main` 또는 `master`)

6. **Release title** 입력  
예: `4seasonAI v0.0.0`

7. **Release description** 입력 (선택 사항, 변경사항이나 안내 문구 등)

8. 아래 영역에 배포 파일을 드래그하거나 선택하여 업로드:

9. ✅ **Publish release** 버튼 클릭

10. 최종 업로드된 파일리스트 체크
```text
release/4seasonAI Setup 0.0.0.exe
release/4seasonAI Setup 0.0.0.exe.blockmap
release/4seasonAI-0.0.0-arm64-mac.zip
release/4seasonAI-0.0.0-arm64-mac.zip.blockmap
release/4seasonAI-0.0.0-arm64.dmg
release/4seasonAI-0.0.0-arm64.dmg.blockmap
release/latest.yml
release/latest-mac.yml
```

---

🎉 완료! Git Tag가 자동으로 생성되며, 릴리스가 올라가면서 `electron-updater` 기반의 자동 업데이트도 활성화됩니다.
