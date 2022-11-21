## fetch vs. pull

- `fetch`: 원격 저장소의 최신 커밋을 로컬로 가져오기만 함.
- `pull`: 원격 저장소의 최신 커밋을 로컬로 가져와 `merge` 또는 `rebase`

<br />

### `fetch` 한 내역 적용 전(merge또는 rebase 전) 살펴보기

(1) 원격의 `main` 브랜치에 커밋 추가<br />

- `git checkout origin/main`으로 확인하기<br />

(2) 원격의 변경사항 `fetch`<br />

- `git checkout origin/main`으로 확인해보기<br />
- `pull`로 적용.<br />

<br />

### 원격의 새 브런치 확인

- `git checkout origin/(브랜치명)`<br />
- `git switch -t origin/(브랜치명)`<br />
