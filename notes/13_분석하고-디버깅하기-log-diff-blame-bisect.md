## 분석하고 디버깅하기

<br />

## log 더 자세히 알아보기

### 옵션들을 활용한 다양한 사용법

각 커밋마다의 변경사항 함꼐 보기

```
git log -p
```

<br />

### 최근 n개 커밋만 보기

```
git log -(갯수)
```

<br />

### 통계와 함께 보기

```
git log --stat
```

- 더 간략히: `--shortstat`

<br />

### 한 줄로 보기

```
git log --oneline
```

- `pretty=oneline --abbrev-commit`의 줄임

<br />

### 변경사항 내 단어 검색

```
git log -S (검색어)
```

<br />

### 커밋 메세지로 검색

```
git log --grep (검색어)
```

> [기타 제한 옵션 보기](https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%BB%A4%EB%B0%8B-%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0#limit_options)

<br />

### 자주 사용되는 그래프 로그 보기

```
git log --all --decorate --oneline --graph
```

- `--all`: 모든 브랜치 보기
- `--graph`: 그래프 표현
- `--decorate`: 브랜치, 태그 등 모든 레퍼런스 표시
  - `--decorate=no`
  - `--decorate=short`: 기본
  - `--decorate=full`

<br />

### 포맷된 로그 보기

> [포맷팅 옵션들 살펴보기](https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%BB%A4%EB%B0%8B-%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0#pretty_format)

얄코님 포맷

```
git log --graph --all --pretty=format:'%C(yellow) %h  %C(reset)%C(blue)%ad%C(reset) : %C(white)%s %C(bold green)-- %an%C(reset) %C(bold red)%d%C(reset)' --date=short
```

- `date`를 `relative`로 바꿔보기
- 단축키로 등록하여 사용

<br />

## 차이 살펴보기 (`git diff`)

### 워킹 디렉토리의 변경사항 확인

```
git diff
```

<br />

### 파일명만 확인

```
git diff --name-only
```

<br />

### 스테이지의 확인

```
git diff --staged
```

- `--cached`와 같음

<br />

### 커밋간의 차이 확인

```
git diff (커밋1) (커밋2)
```

- 커밋 해시 또는 HEAD 번호로
- 현재 커밋과 비교하려면 이전 커밋만 명시

<br />

### 브랜치간의 차이 확인

```
git diff (브랜치1) (브랜치2)
```

<br />

## 누가 코딩했는지 알아내기(`git blame`)

### 파일의 부분별로 작성자 확인하기

```
git blame (파일명)
```

<br />

### 특정 부분 지정해서 작성자 확인하기

```
git blame -L (시작줄) (끝줄, 또는 +줄수) (파일명)
```

<br />

※ VSCode의 GitLens 확장 사용해보기

<br />

## 오류가 발생한 시점 찾아내기(`git bisect`)

이진 탐색 알고리즘으로 문제의 발생 시점을 찾아낸다.(반을 뚝자르고 뚝자르고...)<br />

<br />

### v3 시점이 의심되는 상황

### 이진 탐색 시작

```
git bisect start
```

<br />

### 오류발생 지점임을 표시

```
git bisect bad
```

<br />

### 의심 지점으로 이동

```
git checkout (해당 커밋 해시)
```

<br />

### 오류 발생 않을 시 양호함 표시

```
git bisect good
```

♻️ 원인을 찾을 때까지 반복

- `git bisect good/bad`

<br />

### 이진 탐색 종료

```
git bisect reset
```
