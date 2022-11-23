## GitHub 잘 활용하기

<br />

## 프로젝트와 폴더에 대한 문서

### README.md 를 활용한 문서화

### 문서 만드렁보기

마크다운 문법

- [markdownguide.org](https://www.markdownguide.org/cheat-sheet/)
- [GitHub 제공 가이드](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

<br />

## 풀 리퀘스트와 이슈

### Pull request

변경사항을 merge하기 전 리뷰를 거치기 위함

- 팀원들의 동의를 거친 뒤 대상 브랜치에 적용

<br />

#### 풀 리퀘스트 사용해보기

(1) 새로운 브랜치 생성 후 변경사항을 커밋해 푸시<br />
(2) GitHub 레포지토리 페이지에서 `Compare & pull request` 버튼 클릭<br />

- 또는 `~ branches`에서 `New pull reqest` 클릭<br />

(3) 메시지 작성 후 `Create pull reqest` 클릭<br />

<br />

#### 풀 리퀘스트 검토 후 처리하기

(1) GitHub 레파지토리 페이지에서 `Pull Request` 탭 클릭<br />
(2) 대상 풀 리퀘스트 클릭하여 내용 검토

- 의견이 있을 시 코멘트 달기
- 반려해야 할 시 `Close pull reqest`
- 승인할 시 `Merge pull reqest`

<br />

### Issue

버그나 문제 제보, 추가할 기능 등의 이슈 소통.

예시

- [네이버 지도 API 예제](https://github.com/navermaps/maps.js)
- [Flutter](https://github.com/flutter/flutter)

<br />

#### 이슈 작성해보기

(1) GitHub 레파지토리 페이지에서 `Issue` 탭 클릭<br />
(2) 필요시 label 또는 milestone 생성<br />

- milestone: 이슈의 주제 묶음 (특정 목표 등)<br />

(3) 이슈 작성<br />

- 필요시 label, milestone, asignee 지정

(4) 이슈 확인 후 처리

- 코멘트 달기
- 관련 개발 착수 (브랜치명이나 커밋 footer에 이슈 번호 반영)
- 해결 뒤: `Close issue`

<br />

## 오픈소스에 참여하기

프로젝트별 '참여 가이드' 확인하기.(ex. [React GitHub](https://github.com/facebook/react))<br />

#### 프로젝트 fork 해보기<br />

- 원하는 유명 프로젝트 내 레파지토리로 포크해보기<br />

<br />

#### 코드 기여하기

- 코드 수정 후 pull request<br />

<br />

#### 오픈소스 주인 관점

- 풀 리퀘스트 코멘트/반려/수락<br />

<br />

## GitHub에 블로그 만들기

### `GitHub Pages` 사용하기

> [소개페이지](https://pages.github.com/)

계정별 무료 웹 호스팅

<br />

### 나의 GitHub Page 만들기

(1) 레파지토리 생성<br />

- 레파지토리명: `(내 아이디).github.io`로 지을 것!
- 로컬로 클론

(2) 최상위 디렉토리에 `index.html` 작성<br />

- VS Code 팁: `!` 입력하고 엔터 누르면 기본 HTML 템플릿 생성
- 내용 작성 뒤 push

(3) `https://(내아이디).github.io`에서 사이트 확인<br />

- 시간이 어느 정도 걸림
