## fast-forward vs. 3-way merge

Git에서 `merge`가 이뤄지는 두 방식.<br />

```
git merge --no-ff (병합할 브랜치명)
```

<br />

## 다른 브랜치에서 원하는 커밋만 따오기 (cherry-pick)

`main` 브랜치에서 실행

```
git cherry-pick (체리의 해시)
```

<br />

## 다른 브랜치에서 파생된 브랜치 옮겨붙이기

`rebase --noto` 옵션 사용<br />

<br />

```
git rebase --onto (도착 브랜치) (출발 브랜치) (이동할 브랜치)
```

> ex. `git rebase --onto main fruit citrus`<br /> > `citrus`로 fast-forward

<br />

## `rebase --onto`를 되돌리려면?

예시, `git rebase --onto main fruit citrus`를 진행한 후 `git reflog`를 사용해서 내역을 살펴보면, 아래와 같이 `rebase --onto` 명령시 여러 내역들이 진행된 것을 볼 수 있다.<br />

`rebase --onto`가 여러 동작들을 포함한다는 것을 알 수 있다.<br />

`reset`은 브랜치별로 이뤄지므로, `rebase --onto`로 영향을 받은 모든 브랜치들에서 하나하나 리셋을 진행해주어야 한다. 혹은 다시 옮겨붙이는 방법도 있다.<br />

변화가 일어난 브랜치는 `main`(fast-forward 됨)과 `citrus` 이 둘이다.<br />

<br />

### `main` 브랜치

`main`은 옮겨붙여진 `citrus`로 fast-forward된 것이 마지막 액션이므로 `reflog`의 기록상에서 그 이전 기록으로 `reset --hard`를 하면 된다.<br />

<br />

### `citrus` 브랜치

#### 방법 A

그리고 `citrus` 브랜치는 해당 브랜치가 옮겨지기 전 마지막 커밋인 `commit: Lime` 부분을 `reflog`에서 찾아 그리로 `reset --hard` 하면 된다.<br />

<br />

#### 방법 B

다른 방법으로는, 다시 `rebase --onto`를 사용해서 `citrus`의 커밋들을 `main`으로부터 도로 `fruit`브랜치의 `orange`부분으로 옮기는 것이다.<br />

그러려면 `orange` 커밋으로 `checkout` 한 다음 그곳에서 새 브랜치를 만들고 (`temp`라 가정)

```
git rebase --onto temp main citrus
```

위 명령어로 `citrus`의 두 커밋들을 해당 위치로 옮겨붙인 뒤 `temp` 브랜치는 삭제하면 된다.<br />

<br />

## 다른 가지의 마디들 묶어서 가져오기

다른 커밋들을 하나로 묶어 가져오기. (`merge --squash` 옵션 사용)<br />

<br />

### `root` 브랜치의 마디들을 하나로 묶어 `main` 브랜치로 가져오기

```
git merge --squash (대상 브랜치)
```

- 변경사항들 스테이지 되어 있음
- `git commit` 후 메시지 입력

<br />

### 일반 `merge`와의 차이

일반 `merge`와 `merge --squash`는 실행 후 코드의 상태는 같지만 내역 면에서 큰 차이가 있는 것이라고 이해하면 된다.<br />

- 일반 merge: A와 B 두 브랜치를 한 곳으로 이어붙임.<br />
- `merge --squash`: B 브랜치의 마디들을 복사해다가 한 마디로 모아 A 브랜치에 붙임 (staged 상태로)

<br />

## 협업을 위한 브랜치 활용법

Gitflow<br />

[Vincent Driessen at nvie](https://nvie.com/posts/a-successful-git-branching-model/)

<br />

### 사용되는 브랜치들

| 브랜치  | 용도                            |
| ------- | ------------------------------- |
| main    | 제품 출시/배포                  |
| develop | 다음 출시/배포를 위한 개발 진행 |
| release | 출시/배포 전 테스트 진행(QA)    |
| feature | 기능 개발                       |
| hotfix  | 긴급한 버그 수정                |
