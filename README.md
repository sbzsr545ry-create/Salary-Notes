# 월급 배분 노트

월급날 통장에 찍힌 실수령액을 입력하면 이번 달 생활비를 계산하고, 계좌별로 모인 돈과 ISA·개인투자 수익률을 보여주는 개인 가계부 웹앱입니다.

- 설치나 서버 없이 **GitHub Pages**만으로 동작해요.
- 기록은 **각자의 브라우저(localStorage)** 에만 저장돼요. 저장소(repo)에는 금액이 올라가지 않아요.
- 폰에서 "홈 화면에 추가"하면 앱처럼 쓸 수 있고, 오프라인에서도 열려요.

## 배포 방법

1. GitHub에서 새 저장소를 만들어요. 예: `salary-notes` (무료 계정은 **Public**이어야 Pages가 켜져요)
2. 이 폴더의 파일을 모두 올려요. `Add file → Upload files`로 끌어다 놓으면 돼요.
3. `Settings → Pages`에서 Source를 **Deploy from a branch**, Branch를 **main / (root)** 로 두고 Save.
4. 1~2분 뒤 `https://<아이디>.github.io/salary-notes/`에서 열려요.

## 폰에 앱처럼 설치하기

- **iPhone (Safari)**: 공유 버튼 → 홈 화면에 추가
- **Android (Chrome)**: 메뉴 → 홈 화면에 추가 / 앱 설치

## 백업

기록은 브라우저에만 있으므로, 우측 상단 설정 → **백업 파일 저장**으로 한 달에 한 번 JSON 파일을 받아 두세요.
폰을 바꾸거나 다른 기기에서 쓰려면 같은 화면의 **백업 불러오기**로 그 파일을 열면 돼요.

> 백업 JSON 파일에는 실제 금액이 들어 있어요. 저장소에는 올리지 마세요.

## 파일 구성

| 파일 | 역할 |
|---|---|
| `index.html` | 앱 전체 (HTML·CSS·JS 한 파일) |
| `manifest.webmanifest` | 홈 화면 설치 정보 |
| `sw.js` | 오프라인 캐시 |
| `icon*.png`, `icon.svg`, `apple-touch-icon.png` | 아이콘 |
| `.nojekyll` | GitHub Pages가 파일을 그대로 서빙하도록 |

## 수정할 때

- 기본 배분 금액은 앱의 설정 화면에서 바꾸면 돼요. 코드를 고칠 필요 없어요.
- `index.html`을 고쳐서 다시 올렸는데 폰에 옛 화면이 보이면, `sw.js`의 `salary-notes-v1`을 `v2`처럼 올려서 함께 올리세요.
