# Total Merchandising Dashboard

GitHub Pages로 공유하기 위한 정적 웹사이트 저장소입니다.

## 공개 사이트

https://pilgukang0704.github.io/ttmddash/

## 공개되는 내용

- `docs/index.html`: 메인 보고 화면 (MLB DNA > 자사분석 > 마켓분석 > 상품기획 방향성, 에이전트 13개)
- `docs/dna/`: MLB DNA 큰 방향성, 27FW 카테고리 방향성
- `docs/dashboards/`: 메인 화면에서 연결되는 에이전트 원본 HTML
- `docs/TMD_Mockup.html`: 통합 대시보드 목업
- **모든 페이지는 비밀번호로 암호화(StatiCrypt, AES)되어 있습니다.**
  - 저장소와 사이트에는 암호문만 올라가고, 비밀번호 창에서 입력해야 브라우저 안에서 열립니다.
  - "이 기기에서 30일간 기억"을 켜면 다른 페이지도 다시 묻지 않습니다.
- 트렌드는 용량(암호화하면 100MB 초과) 때문에 자체 공개 사이트 `pilgukang0704.github.io/Trenddashboard/`로 연결합니다.
- `docs/robots.txt`와 noindex 메타로 검색엔진 수집을 막습니다.

`docs/`는 직접 고치지 않습니다. `_build/build.py` → `_build/publish_docs.py` 순서로 다시 만듭니다.
- publish 스크립트는 각 에이전트 폴더에서 최신 원본을 가져와 `_build/_stage`(평문, git 제외)에서 암호화한 뒤 `docs/`에 씁니다.
- 비밀번호는 `_build/.site_password`(git 제외)에 한 줄로 저장합니다. 비밀번호가 없으면 스크립트가 아무것도 만들지 않고 멈춥니다.
- 비밀번호를 바꾸면 publish를 다시 실행하고 push하면 됩니다.

로컬 작업 메모, 미팅 전사문, 빌드 파일과 로그는 `.gitignore`로 제외됩니다.

## 최초 업로드

`trend.html`과 `brand.html`은 브라우저 업로드 한도보다 크므로, GitHub 웹 화면의 **Add file → Upload files**가 아니라 아래 Git 명령으로 업로드해야 합니다.

1. GitHub에서 새 **Public** 저장소를 만듭니다. 예: `total-merchandising-dashboard`
2. 저장소 생성 화면에서 README, `.gitignore`, License는 추가하지 않습니다.
3. 생성된 저장소의 HTTPS 주소를 복사합니다.
4. 이 폴더에서 작성자 정보를 설정하고 첫 커밋을 만듭니다. 이메일 공개가 싫다면 GitHub의 **Settings → Emails**에 표시되는 `noreply` 주소를 사용합니다.

```powershell
git config user.name "GITHUB_ID"
git config user.email "YOUR_GITHUB_EMAIL_OR_NOREPLY_EMAIL"
git commit -m "Initial GitHub Pages setup"
git remote add origin https://github.com/GITHUB_ID/REPOSITORY_NAME.git
git push -u origin main
```

`GITHUB_ID`와 `REPOSITORY_NAME`은 실제 값으로 바꿉니다. 로그인 창이 나오면 GitHub 계정으로 승인합니다.

## GitHub Pages 켜기

1. GitHub 저장소에서 **Settings**를 엽니다.
2. 왼쪽 메뉴에서 **Pages**를 선택합니다.
3. **Build and deployment**의 Source를 **Deploy from a branch**로 선택합니다.
4. Branch는 **main**, 폴더는 **/docs**를 선택하고 **Save**를 누릅니다.
5. 배포가 끝나면 `https://GITHUB_ID.github.io/REPOSITORY_NAME/`에서 확인합니다.

## 이후 업데이트

`docs` 안의 공개 파일을 갱신한 후 다음 명령을 실행합니다.

```powershell
git add docs README.md .gitignore
git commit -m "Update dashboard"
git push
```

GitHub Pages는 서버 코드를 실행하지 않습니다. `weekly.html`의 로컬 서버용 업데이트 버튼은 공개 사이트에서 자동으로 숨겨지며, 나머지 화면은 정적 조회용으로 동작합니다.
