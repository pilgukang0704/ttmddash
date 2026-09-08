# Total Merchandising Dashboard

GitHub Pages로 공유하기 위한 정적 웹사이트 저장소입니다.

## 공개 사이트

https://pilgukang0704.github.io/ttmddash/

## 공개되는 내용

- `docs/index.html`: 메인 아키텍처 화면
- `docs/TMD_Mockup.html`: 통합 대시보드 목업
- `docs/dashboards/`: 메인 화면에서 연결되는 8개 대시보드

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
