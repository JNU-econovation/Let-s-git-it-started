# Linux 용어


| index | item | index | item |
| --- | --- | --- | --- |
| 1 | [cd](#cd) | 8 | [mv](#mv) |
| 2 | [clear](#clear) | 9 | [ps](#ps) |
| 3 | [cp](#cp) | 10 | [pwd](#pwd) |
| 4 | [echo](#echo) | 11 | [rm](#rm) |
| 5 | [kill](#kill) | 12 | [touch](#touch) |
| 6 | [ls](#ls) | 13 | [uname](#uname) |
| 7 | [mkdir](#mkdir) 



### cd
    
---

```bash
cd {이동하고 싶은 디렉토리}
```

cd는 change directory의 약자입니다.

이동하고 싶은 디렉토리로 현재 위치를 바꿔줍니다.



### clear

---

```bash
clear
```

터미널 창에 쓰여있는 기록을 지웁니다.




### cp

---

```bash
cp {file1} {file2}
file1 파일을 복사하여 file2 파일을 생성

cp {file1} {file2} {dir1/}
dir1 directory 안에 file1과 file2를 생성

cp -r {dir1/} {dir2/}
dir1 directory를 dir2로 복사
```

cp는 copy의 약자로 파일이나 디렉토리를 복사할 수 있습니다.

### echo

---

```bash
echo {옵션} {문자열}
문자열을 출력

echo *
모든 파일, 폴더 출력
```

echo는 마치 메아리와 같이 입력한 문자열을 출력할 수 있습니다. *문자를 통해서 모든 파일과 폴더도 출력할 수 있습니다.

### kill

---

```bash
kill {옵션} {프로세스id}
해당 프로세스를 종료

kill -l
사용할 수 있는 옵션 출력
```

kill 명령어를 통해서 원하는 프로세스를 종료시킬 수 있습니다. 일반적으로 사용되는 옵션은 -9입니다.

### ls

---

```bash
ls {옵션} {파일/디렉토리}
해당 디렉토리 안의 디렉토리 및 파일 출력
```

ls는 list segments의 약자로 원하는 디렉토리 안의 내용을 출력하여 볼 수 있습니다.

### mkdir

---

```bash
mkdir {옵션} {생성할 디렉토리 이름}
디렉토리를 생성
```

mkdir은 make directory의 약자로 디렉토리를 생성합니다.

### mv

---

```bash
mv {옵션} {dir1/file1} {dir2/file2}
dir1의 file1을 dir2의 fil2라는 이름으로 변경하고 이동
```

mv는 move의 약자로 파일이나 디렉토리를 이동시킬 수 있습니다.

### ps

---

```bash
ps {옵션}
```

ps는 process state의 약자로 현재 실행 중인 프로세스와 상태를 출력합니다.

### pwd

---

```bash
pwd
```

pwd는 print working directory의 약자로 현재 경로를 출력합니다.

### rm

---

```bash
rm {옵션} {삭제 파일 or 삭제 디렉토리}
파일 삭제 혹은 디렉토리 삭제
```

rm은 remove의 약자로 파일이나 디렉토리를 삭제합니다.

가장 많이 쓰이는 옵션으로는 -rf가 있습니다. (하위 경로까지 강제로 삭제)

### touch

---

```bash
touch {옵션} {file1}
옵션이 없을 경우 file1이라는 파일 생성
```

touch는 본래 파일의 날짜와 시간을 수정하는 명령어이지만, 0바이트 파일을 생성하기 위해 자주 사용됩니다.

### uname

---

```bash
uname {옵션}
```

uname은 시스템에 대한 정보를 출력합니다. -a 옵션을 통해서 시스템의 전체 정보를 확인할 수 있습니다.