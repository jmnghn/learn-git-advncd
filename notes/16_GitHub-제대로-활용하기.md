## GitHub 제대로 활용하기

<br />

## SSH로 접속하기

### SSH 프로토콜을 통한 인증

- 공개키 암호화 방식을 활용한다
- username과 토큰을 사용할 필요 없다
- 컴퓨터 자체에 키를 저장한다

<br />

### SSH 키 등록하기

- 계정의 `Settings` - `SSH and GPG keys`
- 해당 페이지의 가이드 참조

(1) SSH키 존재 여부 확인<br />

- 터미널 (윈도우의 경우 Bash Shell)에서 `~/.ssh`로 이동한다.

```
cd ~/.ssh
```

- `id_rsa.pub`, `id_ecdsa.pub`, `id_ed25519.pub` 파일 중 하나 존재 여부를 확인한다. (있다면 바로 3번)

<br />

(2) SSH 키 생성<br />

- 터미널(윈도우의 경우 Bash Shell)에서 키를 생성한다.

```
ssh-keygen -t ed25519 -C "(이메일 주소)"
```

- 원할 시 `passphrase`를 입력한다.
- 1번의 과정으로 키 생성을 확인한다.

<br />

(3) GitHub에 키 등록

- 공개키 열람하여 복사

```
cat ~/.ssh/id_ed25519.pub
```

- `New SSH Key` 클릭하여 키 이름과 함께 등록

<br />

(4) SSH로 사용해보기<br />

- 원격을 SSH주소로 변경한 후 테스트

<br />

## GPG로 커밋에 사인하기

### GPG 키를 통한 검증

#### GitHub 커밋 내역 살펴보기

- 로컬에서 푸시한 커밋과 GitHub에서 작성한 커밋 비교
- `Verified`: 신뢰할 만한 출처에서 커밋되었다는 인증

<br />

### GPG 사용

(1) GPG 툴 설치<br />

- 윈도우: [`다운로드 사이트`](https://www.gnupg.org/download/)
- 맥: `brew install gnupg`
- `gpg --version`으로 확인

(2) GPG 키 생성<br />

- [가이드](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)<br />

<br />

(3) `New GPG key`클릭하여 등록<br />

- [가이드](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)
- 맥의 경우 추가 절차(환경 변수 설정) 있음

<br />

(4) 사인하기

- 커밋에 사인: 명령어에 `-S` 옵션 추가

```
git commit -S -m '(메시지)'
```

- 태그에 사인: 명령어에 `-s` 옵션 추가

```
git tag -s (태그명) (커밋 해시) -m (메시지)
```

<br />

## GitHub Actions

> CI/CD: 지속적 통합과 배포

- [📹 얄코님 영상](https://www.youtube.com/watch?v=UbI0Q_9epDM)<br />
- 동종: GitLab CI/CD, BitBucket Pipelines<br />

### GitHub Actions 살펴보기

- github.io 페이지의 액션

  - 해당 레파지토리 페이지에서 `Actions` 탭 살펴보기
  - 새로운 커밋 푸시한 직후 다시 살펴보기

- 다른 프로젝트에서 액션 추가해보기

  - `Actions` 탭에서 액션들 살펴보고 적용해보기
  - `Marketplace` 살펴보고 적용해보기
  - 커밋 후 pull하여 로컬에서 확인하기

<br />

### GitHub Actions 체험해보기

PR시마다 코드 테스트 후 실패시 자동 close

- `.github/workflow/test.yaml` 살펴보기
- 코드 수정(성공 & 실패)하여 `main` 브랜치로 PR 날려보기

<br />

## GitHub 추가 팁

### [Octo Tree](https://chrome.google.com/webstore/detail/octotree-github-code-tree/bkhaagjahfmjljalopjnoealnfndnagc)

<br />

### GitHub CLI

> [주요 명령어](https://cli.github.com/manual/)

- GitHub 작업 전용 CLI 툴
- [사이트 바로가기](https://cli.github.com/)

<br />

#### 로그인/로그아웃

```
gh auth (login/logout)
```

#### 레포지토리들 보기

```
gh repo list
```

#### 프로젝트 클론

```
gh repo clone (사용자명)/레포지토리명
```

#### 프로젝트 생성/삭제

```
gh repo (create/delete)
```

#### 이슈 목록 보기

```
gh issue list
```

#### 이슈 열람/닫기

```
gh issue (view/close) (이슈 번호)
```

#### 이슈 생성

```
gh issue create
```

#### 풀 리퀘스트 만들기/목록 보기

```
gh pr (create/list)
```

#### 풀 리퀘스트 보기/코멘트/닫기/병합

```
gh pr (view/comment/close/merge) (PR 번호)
```
