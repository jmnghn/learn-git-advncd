## reset-했어도-희망은-있다

<br />

### `reflog` 명령어

```
git reflog
```

> 프로젝트가 위치한 커밋이 바뀔 때마다 기록되는 내역을 보여주고 이를 사용하여 reset 하기 이전 시점으로 프로젝트를 복구할 수 있다.<br />

```
git reflog

9360d70 (HEAD -> main) HEAD@{0}: commit: Update notes
b361111 HEAD@{1}: commit: Update notes
56d4cd2 HEAD@{2}: commit: Update notes
019ed07 HEAD@{3}: commit: Learn stash
615e2be HEAD@{4}: commit (amend): Add Members to Panthers and Pumas
4df4de7 HEAD@{5}: commit (amend): Add a member to Panthers blahblah
...
```

```
git reset --hard 9360d70
```
