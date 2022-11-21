## Git의 각종 설정

<br />

### `global`설정과 `local` 설정하기

config를 `--global`과 함께 지정하면 전역으로 설정된다.<br />

- 특정 프로젝트만의 `user.name`과 `user.email` 지정해보기.

<br />

### 설정값 확인하기

<br />

#### 현재 모든 설정값 보기

```
git config (glboal) --list
```

<br />

#### 에디터에서 보기

```
git config (global) -e
```

<br />

#### 기본 에디터 수정

```
git config --glboal core.editor "code --wait"
```

- 또는 `code` 자리에 원하는 편집 프로그램의 `.exe`파일 경로 연결. <br />
- `--wait`: 에디터에서 수정하는 동안 CLI를 정지
- `git commit`등의 편집도 지정된 에디터에서 열게 됨.

> 위의 에디터 설정을 되돌리려면

`git config --glbal e`로 편집기를 연 뒤 아래 부분을 삭제하고 저장

```
[core]
  excludesfile = /Users/jmnghn/.gitignore_global
  editor = code --wait
```

<br />

### 유용한 설정들

<br />

#### 줄바꿈 호환 문제 해결

```
git config --global core.autocrlf (윈도우: true / 맥: input)
```

<br />

#### `pull`기본 전력 `merge` 또는 `rebase`로 설정

```
git config pull.rebase false
```

```
git config pull.rebase true
```

<br />

#### 기본 브랜치명

```
git config --global init.defaultBranch main
```

<br />

#### push시 로컬과 도일한 브랜치명으로

```
git config --global push.default current
```

<br />

### 단축키 설정

> [Git Alias](https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-Git-Alias)

```
git config --global alias.(단축키) "명령어"
```

> git config --global alias.cam "commit -am"
