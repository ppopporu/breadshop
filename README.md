🍞 옷장 속의 작은 빵집

경기도 안산시 단원구 선부동에 위치한 옷장 속의 작은 빵집의 모바일 주문 웹앱입니다.

<br>


✨ 주요 기능
기능	설명
👤 회원가입 / 로그인	이름·전화번호·이메일로 가입, 판매자(admin) 계정 분리
🛒 빵 주문	상품 선택, 수량 조절, 수령지 선택(부곡이웃교회 / 꼬르륵)
📋 주문 관리 (판매자)	주문 승인 / 취소(사유 입력) / 배송완료 처리
🚚 배송 현황 (주문자)	주문접수 → 주문완료 → 배송 중 → 배송완료 4단계 진행 바
🍞 상품 관리	빵 이름·가격·사진 첨부 추가/삭제
💳 계좌 정보	판매자 계좌 설정, 주문 후 입금 안내 자동 표시
🗺️ 지도 연동	카카오맵 · 네이버맵 연결
🔥 Firebase DB	Firestore 무료 영구 저장 (Spark 플랜)

<br>


🚀 GitHub Pages 배포 방법

1단계 — GitHub 저장소 생성

1. github.com 로그인
2. 우측 상단 + → New repository
3. Repository name: breadshop (또는 원하는 이름)
4. Public 선택 → Create repository

2단계 — 파일 업로드

# 방법 A: Git 명령어 사용
git init
git add index.html README.md
git commit -m "첫 배포: 옷장 속의 작은 빵집"
git branch -M main
git remote add origin https://github.com/[내 아이디]/breadshop.git
git push -u origin main

# 방법 B: GitHub 웹에서 직접 업로드
# 저장소 페이지 → "uploading an existing file" 클릭 → index.html 드래그 업로드


3단계 — GitHub Pages 활성화

1. 저장소 → Settings 탭
2. 왼쪽 메뉴 Pages 클릭
3. Source: Deploy from a branch
4. Branch: main / / (root) 선택 → Save
5. 약 1~2분 후 https://[내 아이디].github.io/breadshop/ 접속 가능

<br>


🔥 Firebase 설정 (최초 1회)

앱 최초 접속 시 Firebase 설정 화면이 나타납니다.

1. Firebase 프로젝트 생성
- console.firebase.google.com 접속
- Google 계정 로그인 → 프로젝트 만들기
- 이름 입력 (예: breadshop) → 계속 → 완료

2. Firestore 데이터베이스 생성
- 왼쪽 메뉴 Firestore Database 클릭
- 데이터베이스 만들기 → 테스트 모드 선택
- 위치: asia-northeast3 (Seoul) → 완료

3. 보안 규칙 설정
Firestore Database → 규칙 탭 → 아래 코드로 교체 후 게시:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}


4. 앱 등록 및 설정 코드 복사
- ⚙️ 프로젝트 설정 → 내 앱 → </> 웹 클릭
- 닉네임 입력 후 앱 등록
- firebaseConfig 객체 전체 복사
- 앱 화면의 입력란에 붙여넣기 → Firebase 연결하기 클릭

<br>


👤 계정 정보
구분	아이디	초기 비밀번호
판매자(관리자)	admin	admin
주문자	회원가입 후 이메일 사용	가입 시 설정

⚠️ 첫 로그인 후 설정 → 비밀번호 변경에서 관리자 비밀번호를 변경하세요.

<br>


📦 배송 상태 흐름

주문 접수 (주문중)
    ↓ 판매자 [✅ 승인]
주문 완료 + 배송 중 🚚
    ↓ 판매자 [🏁 배송완료 처리]
배송 완료 🏁


<br>


🛠 기술 스택

- Frontend: Vanilla HTML / CSS / JavaScript (단일 파일)
- Database: Firebase Firestore (무료 Spark 플랜)
- Hosting: GitHub Pages (무료)
- Font: 맑은 고딕 (Malgun Gothic)

<br>


📁 파일 구조

breadshop/
├── index.html   ← 앱 전체 (단일 파일)
└── README.md    ← 이 파일


<br>


📌 Firebase 무료 한도 (Spark 플랜)
항목	무료 한도
저장 용량	1 GiB
일일 읽기	50,000건
일일 쓰기	20,000건
일일 삭제	20,000건

소규모 빵집 주문 시스템에 충분한 용량입니다. 신용카드 없이 영구 무료로 사용 가능합니다.
