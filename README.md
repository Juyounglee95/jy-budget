# 우리집 가계부

GitHub Pages에서 열고, 기록은 Firebase Firestore에 저장하는 부부 가계부예요.
이 저장소에는 프로그램만 있고 가계부 데이터는 없어요.

## 처음 설정 (한 번만)

1. Firebase 프로젝트 만들기
   - https://console.firebase.google.com 에서 프로젝트 추가 (Google Analytics는 꺼도 돼요)
2. 웹 앱 등록
   - 프로젝트 설정 > 일반 > 내 앱 > 웹(</>) 추가, Firebase 호스팅은 체크하지 않아요
   - 나오는 `firebaseConfig` 값을 `index.html` 위쪽 `FIREBASE_CONFIG`에 붙여 넣어요
3. 구글 로그인 켜기
   - Authentication > 시작하기 > 로그인 방법 > Google 사용 설정
   - Authentication > 설정 > 승인된 도메인 > `<GitHub아이디>.github.io` 추가
4. Firestore 만들기
   - Firestore Database > 데이터베이스 만들기 > 위치 `asia-northeast3 (서울)` > 프로덕션 모드
   - 규칙 탭에 `firestore.rules` 내용을 붙여 넣고, 두 사람의 구글 이메일로 바꾼 뒤 게시
5. GitHub Pages 켜기
   - 저장소 Settings > Pages > Source: Deploy from a branch > `main` / `(root)` > Save
   - 잠시 뒤 `https://<GitHub아이디>.github.io/<저장소이름>/` 로 열려요

## 기존 기록 옮기기

1. 예전 가계부(Claude 페이지) 설정 > 백업 파일 내보내기
2. 새 주소에서 로그인 > 설정 > 백업 파일 가져오기
3. 내려받은 백업 파일은 지우거나 저장소 밖에 보관해요

## 알아 둘 것

- 사이트 주소는 누구나 열 수 있지만, 기록은 규칙에 적은 두 계정만 볼 수 있어요.
- `apiKey` 등 Firebase 설정값은 공개돼도 괜찮아요. 실제로 막아 주는 건 Firestore 보안 규칙이에요.
- 카카오톡 같은 앱 안 브라우저에서는 구글 로그인이 막혀요. Safari나 Chrome에서 열고 홈 화면에 추가해 쓰세요.
- 로그인 계정을 바꾸려면 `firestore.rules`의 이메일을 고치고 Firebase 콘솔에서 다시 게시해요.
