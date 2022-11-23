## Git의 추가 기능들

## Git hooks

Git상의 이벤트마다 자동으로 실행될 스크립트를 지정한다.<br />

### Git Hooks 폴더 보기

프로젝트 폴더 내 `.git` > `hooks` 폴더 확인.<br />

- 파일 끝에 `.sample`을 없애면 훅 실행파일이 된다.

<br />

### `gitmoji-cli`로 활용예 보기

> [`gitmoji-cli GitHub`](https://github.com/carloscuesta/gitmoji-cli)

<br />

#### `gitmoji-cli` 설치

맥: `brew install gitmoji`<br />
윈도우: `npm i -g gitmoji-cli`<br />

<br />

#### 프로젝트의 훅에 적용

프로젝트 폴더에서 아래 명령어 실행

```
gitmoji -i
```

- `hooks` 폴더에 추가된 파일 확인하기
- 프로젝트에 수정 뒤 `git add .`, `git commit`하여 진행
- 커밋 추가 뒤 push하여 GitHub에서 확인

#### gitmoji-cli 훅을 해제하려면

- `hooks`폴더에서 `prepare-commit-msg` 파일을 삭제해주면 된다.

<br />

## Git Submodules

### 서브모듈

- 프로젝트 폴더 안에 또 다른 프로젝트가 포함될 때 사용한다.
- 여러 프로젝트에 사용되는 공통모듈일 때 유용하다.

<br />

### 사용해보기

#### 두 개의 프로젝트 생성

- `main-project`, `submodule`
- 양쪽 모두 파일 생성 및 작성 뒤 커밋
- 두 프로젝트 모두 GitHub에 각각 레파지토리 만들어 올리기
  - 혹은 GitHub에서 생성해도 좋음.

<br />

#### `main-project`에 서브모듈로 `submodue` 프로젝트 추가

`main-project` 디렉토리상 터미널에서 아래 명령어 실행

```
git submodule add (submodule의 GitHub 레포지토리 주소) (하위폴더명, 없을 시 생략)
```

- 프로젝트 폴더 내 `submodule`폴더와 `.gitmodules` 파일 확인
- 스테이지된 변경사항 확인 뒤 커밋
- 양쪽 모두 수정사항 만든 뒤 `main-project`에서 `git status`로 확인.
  - `submodule`의 변경사항은 포함되지 않음 확인
- `main-project`에서 변경사항 커밋 뒤 푸시
- `submodule`에서 변경사항 커밋 뒤 푸시
- `main-project`에서 상태 확인
- `main-project`에서 커밋, 푸시 뒤 GitHub에서 확인

<br />

#### 서브모듈 업데이트

(1) `main-project` 새로운 곳에 clone하기<br />
(2) 아래 명령어들로 서브모듈 init 후 클론

```
git submodule init (특정 서브모듈 지정시 해당 이름)
```

```
git submodule update
```

(3) GitHub에서 `submodule`에 수정사항 커밋

`main-project`에서 아래 명령어로 업데이트

```
git submodule update --remote
```

- 서브모듈 안에 또 서브모듈이 있을 시: `--recursive` 추가
