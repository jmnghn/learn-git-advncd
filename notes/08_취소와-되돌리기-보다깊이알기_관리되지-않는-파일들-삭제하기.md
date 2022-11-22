## 관리되지 않는 파일들 삭제하기

<br />

### git clean

Git에서 추적하지 앟는 파일들 삭제

| 옵션 | 설명                                |
| ---- | ----------------------------------- |
| -n   | 삭제될 파일들 보여주기              |
| -i   | 인터렉티브 모드 시작                |
| -d   | 폴더 포함                           |
| -f   | 강제로 바로 지워버리기              |
| -x   | `.gitignore`에 등록된 파일들도 삭제 |

> 위 옵션들을 조합해서 사용한다.<br />

<br />

흔히 쓰이는 조합: git clean -df # 폴더 포함해서 강제로<br />

```
git clean -id
Would remove the following items:
  dir/          toClean1.txt  toClean2.txt
*** Commands ***
    1: clean                2: filter by pattern    3: select by numbers
    4: ask each             5: quit                 6: help
What now> 3
    1: dir/            2: toClean1.txt    3: toClean2.txt
Select items to delete>> 1,3
  * 1: dir/            2: toClean1.txt  * 3: toClean2.txt
Select items to delete>>
Would remove the following items:
  dir/          toClean2.txt
*** Commands ***
    1: clean                2: filter by pattern    3: select by numbers
    4: ask each             5: quit                 6: help
What now> 4
Remove dir/ [y/N]? y
Remove toClean2.txt [y/N]? n
Removing dir/
```
