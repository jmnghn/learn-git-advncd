## 제대로 파는 Git & GitHub

> [https://www.yalco.kr/lectures/git-github/](https://www.yalco.kr/lectures/git-github/)

<br />

### Git 설정 & 프로젝트 관리 시작하기.

- `git init`과 `.git`의 역할.

<br />

### 과거로 돌아가는 두 가지 방법

- `reset`과 `revert`
  - reset(`--hard`)은 말그대로 reset이고, revert는 '커밋했던 내역'을 되돌린다는 의미. (그 시점으로 돌아가는게 아니라, 그 시점에 커밋했던 내용을 '취소'한다는 의미)
  - revert의 `--continue`와 `--no-commit`
    - 상황에 따라서지만, `git rm [file]` 후, `--continue`

<br />

### 여러 branch 만들어보기

`git switch [브랜치명]`<br />

- `checkout` 명령어가 Git 2.23버전부터 `switch`, `restore` 로 분리.<br />
- 브랜치 성생과 동시에 이동하기<br />

  ```
  git switch -c new-temas
  ```

  > git checkout -b (새 브랜치명)<br />

- 브랜치 삭제하기

  ```
  git branch -d [삭제할 브랜치명]
  ```

  ```
  git branch -D [삭제할 브랜치명] # 대문자
  ```

  > 지울 브랜치에 다른 브랜치로 적용되지 않은 내용의 커밋이 있을 시에는 `-D(대문자)` 옵션으로 '강제 삭제'합니다.

- 브랜치 이름 바꾸기

  ```
  git branch -m (기존 브랜치명) (새 브랜치명)
  ```

- 결과 살펴보기

  ```
  git log --all --decorate --oneline --graph
  ```

  > `git log` 위치한 브랜치에서의 내역만 볼 수 있음.

<br />

### branch 합치기 실습

`merge`와 `rebase`.<br />

- `merge`: '두 브랜치'를 '한 커밋'에 이어붙입니다.<br />

  - '브랜치 사용내역을 남길 필요가 있을 때' 적합한 방식입니다.
  - 다른 형태의 merge에 대해서도 이후에 다룹니다.

- `rebase`: 브랜치를 '다른 브랜치'에 '이어붙입니다'.<br />
  - 한 줄로 깔끔히 정리된 내역을 유지하기 원할 때 적합합니다.
  - 이미 팀원과 공유된 커밋들에 대해서는 사용하지 않는 것이 좋습니다.

명령어를 입력하는 브랜치가 서로 반대. (main으로 merge하고 싶으면 main에서 merge. 특정 브런치를 main으로 rebase하고 싶으면 특정 브랜치에서 rebase.)

<br />

#### `merge`

현재 `main`브랜치 일 때,<br />

`git merge [브랜치명]`<br />

> `merge`는 `reset`으로 되돌리기가 가능하다. (merge도 하나의 커밋.)
> `git merge aboart`(merge 진행 취소)과 메시지 없이.(`-m`옵션 없이) commit.

<br />

#### `rebase`

rebase할 브랜치 에서,(merge와 반대!)<br />

`git rebase main`<br />

> 하고나면, `main` 브랜치가 뒤쳐져 있는 상황인데, `main`브랜치로 이동 후 rebase한 브랜치 시점으로 `fast-forward`. -> `git merge [rebase한 브랜치]`

<br />

### 충돌 해결하기

- `--abort`처음 해봤음... (rebase/merge 둘 다... :) 유산시키다 라니... 끔찍하군.)
- 충돌 해결하고 `add` 한 후에는 `commit`만 하면 되는구나..! (메세지가 자동으로...)
- rebase 충돌해결 처음해봤음. :) (`--continue`, 오... 이런식으로 진행되는구나...)

<br />

### push와 pull

push의 `-u` 옵션. (이후에 [원격저장소 브랜치]를 명령어에 입력하지 않아도 됨)<br />

`pull --no-rebase`와 `pull -rebase`
