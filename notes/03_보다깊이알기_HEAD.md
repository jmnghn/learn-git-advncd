## Git의 `HEAD`

<br />

### `checkout`으로 앞뒤 이동해보기

```
git checkout HEAD^
```

- `^` 또는 `~`: 갯수만큼 이전으로 이동.<br />
  - `git checkout HEAD^^^`, `git checkout HEAD~5`<br />
- `커밋 해시`를 사용해서도 이동이 가능하다.<br />
  - `git checkout (커밋해시)`<br />
- `git checkout -`: (이동을) 한 단계 되돌리기.

> `git switch`와 `checkout`의 차이. (오호)<br />

<br />

### 이전으로 `checkout`된 상태에서 소스트리로 `HEAD` 상태 보기.

→ `익명의 브랜치`에 위치하고 있다는 것을 알 수 있다. (checkout을 하고나니 만든 적 없는 브랜치가 존재하고 있음)<br />

> 특정 브런치의 특정 시점으로 돌아가서 새로운 브랜치를 생성할 수 있다. :) <br />

<br />

### `HEAD` 사용하여 `reset`하기

`git reset`을 HEAD를 사용해서도 할 수 있다.<br />

```
git reset HEAD(원하는 단계) (옵션)
```
