# 교수님, 종강하겠습니다 — GitHub Pages 업로드용

1. ZIP을 압축 해제합니다. ZIP 자체를 업로드하지 않습니다.
2. LawschoolGames 계정에서 Public 저장소 lawschoolgames.github.io를 만듭니다.
3. index.html, games.js, ads.txt, README.md와 Arcade 폴더를 저장소 최상위에 업로드합니다. 폴더째 올려 하위 폴더에 들어가지 않도록 합니다.
4. Settings → Pages → Deploy from a branch → main → / (root) → Save를 선택합니다.
5. Actions에서 최신 배포 완료를 확인합니다.
6. https://lawschoolgames.github.io/ 에 게임 목록이 열리고, https://lawschoolgames.github.io/ads.txt 에 게시자 정보가 보이는지 확인합니다.
7. 애드센스에서 메타 태그 방식을 선택하여 소유권 확인 후 검토 요청을 진행합니다.

## 반영된 내용
- 게임 목록 랜딩 페이지와 /Arcade/에서 실행되는 게임 전체, 이용자 이름 입력 및 난이도별 온라인 명예의 전당 코드
- 제공된 Supabase 프로젝트 URL과 공개용 publishable 키
- 애드센스 소유권 확인 메타 태그와 게시자 ID, ads.txt
- 기존 양옆 광고 배치 코드

## 광고 노출 설정
소유권 확인과 광고 게재 승인은 별개입니다. 아직 광고 단위 ID를 받지 않았으므로 광고 노출은 꺼져 있습니다.
사이트 승인 후 애드센스에서 디스플레이 광고 단위 두 개를 생성하고 Arcade/config.js의 adsenseLeftSlot과 adsenseRightSlot에 각각 숫자 ID를 넣습니다. 그 후 adsenseEnabled를 true로 바꿉니다.
기존 구현에 따라 광고는 화면 너비 1840px 이상, 높이 720px 이상에서 표시됩니다.

## 온라인 기록
기존 Supabase 데이터베이스를 그대로 사용합니다. 새 데이터베이스를 만들 필요는 없습니다.
이 ZIP은 Supabase 테이블이나 접근 정책을 변경하지 않습니다. 데이터베이스의 기존 설정이 완료되어 있어야 기록 조회 및 저장이 작동합니다.
config.js에는 공개용 키만 포함되어 있습니다. 비공개 secret 키나 service_role 키를 넣지 마세요.

## 게임 추가
새 게임을 별도 폴더에 넣고 games.js 배열에 title, genre, description, url 항목을 추가하면 카드가 표시됩니다.
루트 index.html은 게임 목록이며 Arcade/index.html은 기존 게임입니다.
기존 Arcade 저장소가 Pages로 서비스 중이면 /Arcade/ 경로를 공유하므로, 기존 저장소에도 Arcade/index.html과 Arcade/config.js의 내용을 각각 index.html, config.js로 반영하면 두 소스를 일치시킬 수 있습니다.

명예의 전당 UI: 난이도 버튼 4개, 점수와 평점 분리, 상위 순위 강조, 페이지 이동 및 모바일 배치 개선. 기존 랭킹 API와 저장 방식을 유지합니다.
