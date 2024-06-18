# 🌳bandit6 -> bandit7🌳
> The password for the next level is stored somewhere on the server and has all of the following properties: <br/>

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

다음 레벨의 비밀번호는 inhere 서버 어딘가에 존재하는데 다음과 같은 속성을 가지고 있다 <br />

<br/>

**hint commands**
>ls , cd , cat , file , du , find , grep


- file : 파일 종류(type) 확인
- du(disk usage) : 파일, 디렉토리 용량 확인
- find : 파일 검색
- grep : 파일 내 특정 문자열 검색

|명령어|뜻|
|------|---|
|-name|해당 이름의 파일을 찾음. 해당 이름에는 정규 표현식을 활용할 수 있음|
|-type|지정된 파일 타입에 해당하는 파일 검색|
|-user|해당 유저에게 속한 파일 검색|
|-empty|빈 디렉토리 혹은 크기가 0인 파일 검색|
|-delete|검색된 파일 혹은 디렉토리 삭제|
|-exec|검색된 파일에 대해 지정된 명령 실행|
|-path|지정된 문자열 패턴에 해당하는 경로에서 검색|
|-print|검색 결과를 출력. 검색 항목은 newline으로 구분. (기본 값)|
|-print0|검색 결과를 출력. 검색 항목은 null로 구분|
|-size|파일 크기를 사용하여 파일 검색|
|-mindepth|검색을 시작할 하위 디렉토리 최소 깊이 지정|
|-maxdepth|검색할 하위 디렉토리의 최대 깊이 지정|
|-atime|n일 이내에 액세스된 파일을 찾음|
|-ctime|n일 이내에 만들어진 파일을 찾음|
|-mtime|n일 이내에 수정된 파일을 찾음|
|-cnewer file|해당 파일보다 최근에 수정된 파일을 찾음|

[출처]https://coding-factory.tistory.com/804

<br />

## ☀️해결☀️
### 01 cd 명령어 : 위치 이동
👉 홈 디렉토리가 아닌 서버 어딘가 이기때문에 cd 명령어를 통해 루트(/)로 이동해준다. <br/>
```ssh
bandit6@bandit:~$ cd /
bandit6@bandit:/$
```

<br/>

### 02 ls -l 명령어 사용 : 파일 확인
👉 ls -l 명령어를 통해 현재 위치에 있는 파일들을 확인한다. 매우 많기 때문에 역시나 일일히 찾을 수는 없다!<br/>
```ssh
bandit6@bandit:/$ ls -l
total 164
lrwxrwxrwx   1 root root     7 Apr 22 13:08 bin -> usr/bin
drwxr-xr-x   2 root root  4096 Feb 26 12:58 bin.usr-is-merged
drwxr-xr-x   5 root root  4096 Jun 15 08:39 boot
drwxr-xr-x  16 root root  3340 Jun 17 14:59 dev
drwxr-xr-x   7 root root  4096 Jun 16 02:48 drifter
drwxr-xr-x 121 root root 12288 Jun 17 14:59 etc
drwxr-xr-x   3 root root  4096 Jun 16 02:49 formulaone
drwxr-xr-x  70 root root  4096 Jun 16 02:49 home
drwxr-xr-x   9 root root  4096 Jun 16 02:49 krypton
lrwxrwxrwx   1 root root     7 Apr 22 13:08 lib -> usr/lib
lrwxrwxrwx   1 root root     9 Jun 16 02:40 lib32 -> usr/lib32
lrwxrwxrwx   1 root root     9 Apr 22 13:08 lib64 -> usr/lib64
drwxr-xr-x   2 root root  4096 Apr  8 14:37 lib.usr-is-merged
lrwxrwxrwx   1 root root    10 Jun 16 02:40 libx32 -> usr/libx32
drwx------   2 root root 16384 Jun 15 08:37 lost+found
drwxr-xr-x   2 root root  4096 Jun 15 08:35 media
drwxr-xr-x   2 root root  4096 Jun 15 08:35 mnt
drwxr-xr-x   7 root root  4096 Jun 16 02:41 opt
dr-xr-xr-x 777 root root     0 Jun 17 14:59 proc
drwx------   7 root root  4096 Jun 16 03:29 root
drwxr-xr-x  29 root root   980 Jun 18 06:59 run
lrwxrwxrwx   1 root root     8 Apr 22 13:08 sbin -> usr/sbin
drwxr-xr-x   2 root root  4096 Mar 31 09:00 sbin.usr-is-merged
drwx------   6 root root  4096 Jun 15 08:39 snap
drwxr-xr-x   2 root root  4096 Jun 15 08:35 srv
dr-xr-xr-x  13 root root     0 Jun 17 15:00 sys
drwxrwx-wt 648 root root 69632 Jun 18 07:28 tmp
drwxr-xr-x  14 root root  4096 Jun 16 02:47 usr
drwxr-xr-x  13 root root  4096 Jun 17 14:59 var
```

<br/>

### 03 file 명령어 사용 : 1033 byte 파일 찾기
💡 33 byte 사이즈이며 user가 bandit7, group이 bandit6인 파일을 찾으려고 할때 무수히 많은 파일을 찾아주었는데 여기서 우리가 봐야할 부분은 Permission이 denied되지 않은 파일을 찾는 것이다. <br/>
```ssh
bandit6@bandit:/$ find -size 33c -user bandit7 -group bandit6
find: ‘./snap’: Permission denied
find: ‘./lost+found’: Permission denied
find: ‘./root’: Permission denied
find: ‘./proc/tty/driver’: Permission denied
find: ‘./proc/1736410/task/1736410/fd/6’: No such file or directory
find: ‘./proc/1736410/task/1736410/fdinfo/6’: No such file or directory
find: ‘./proc/1736410/fd/5’: No such file or directory
find: ‘./proc/1736410/fdinfo/5’: No such file or directory
find: ‘./tmp’: Permission denied
find: ‘./dev/shm’: Permission denied
find: ‘./dev/mqueue’: Permission denied
find: ‘./drifter/drifter14_src/axTLS’: Permission denied
find: ‘./var/tmp’: Permission denied
find: ‘./var/log/unattended-upgrades’: Permission denied
find: ‘./var/log/private’: Permission denied
find: ‘./var/log/amazon’: Permission denied
find: ‘./var/log/chrony’: Permission denied
find: ‘./var/cache/ldconfig’: Permission denied
find: ‘./var/cache/apparmor/baad73a1.0’: Permission denied
find: ‘./var/cache/apparmor/2425d902.0’: Permission denied
find: ‘./var/cache/pollinate’: Permission denied
find: ‘./var/cache/private’: Permission denied
find: ‘./var/cache/apt/archives/partial’: Permission denied
find: ‘./var/lib/udisks2’: Permission denied
find: ‘./var/lib/update-notifier/package-data-downloads/partial’: Permission denied
find: ‘./var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial’: Permission denied
./var/lib/dpkg/info/bandit7.password
find: ‘./var/lib/polkit-1’: Permission denied
find: ‘./var/lib/private’: Permission denied
find: ‘./var/lib/snapd/cookie’: Permission denied
find: ‘./var/lib/snapd/void’: Permission denied
find: ‘./var/lib/amazon’: Permission denied
find: ‘./var/lib/apt/lists/partial’: Permission denied
find: ‘./var/lib/chrony’: Permission denied
find: ‘./var/spool/rsyslog’: Permission denied
find: ‘./var/spool/bandit24’: Permission denied
find: ‘./var/spool/cron/crontabs’: Permission denied
find: ‘./run/lock/lvm’: Permission denied
find: ‘./run/systemd/inaccessible/dir’: Permission denied
find: ‘./run/systemd/propagate/systemd-udevd.service’: Permission denied
find: ‘./run/systemd/propagate/systemd-resolved.service’: Permission denied
find: ‘./run/systemd/propagate/systemd-networkd.service’: Permission denied
find: ‘./run/systemd/propagate/systemd-logind.service’: Permission denied
find: ‘./run/systemd/propagate/irqbalance.service’: Permission denied
find: ‘./run/systemd/propagate/chrony.service’: Permission denied
find: ‘./run/systemd/propagate/polkit.service’: Permission denied
find: ‘./run/systemd/propagate/ModemManager.service’: Permission denied
find: ‘./run/systemd/propagate/fwupd.service’: Permission denied
find: ‘./run/lvm’: Permission denied
find: ‘./run/cryptsetup’: Permission denied
find: ‘./run/multipath’: Permission denied
find: ‘./run/screen/S-bandit20’: Permission denied
find: ‘./run/screen/S-bandit25’: Permission denied
find: ‘./run/sudo’: Permission denied
find: ‘./run/user/11016’: Permission denied
find: ‘./run/user/11002’: Permission denied
find: ‘./run/user/11012’: Permission denied
find: ‘./run/user/11001’: Permission denied
find: ‘./run/user/11004’: Permission denied
find: ‘./run/user/11013’: Permission denied
find: ‘./run/user/11020’: Permission denied
find: ‘./run/user/11005’: Permission denied
find: ‘./run/user/11000’: Permission denied
find: ‘./run/user/11006/systemd/inaccessible/dir’: Permission denied
find: ‘./run/user/11008’: Permission denied
find: ‘./run/user/11023’: Permission denied
find: ‘./run/user/11003’: Permission denied
find: ‘./run/user/11007’: Permission denied
find: ‘./run/user/11015’: Permission denied
find: ‘./run/user/11010’: Permission denied
find: ‘./run/user/11017’: Permission denied
find: ‘./run/user/11009’: Permission denied
find: ‘./run/user/11026’: Permission denied
find: ‘./run/user/11011’: Permission denied
find: ‘./run/user/11014’: Permission denied
find: ‘./run/user/11019’: Permission denied
find: ‘./run/user/8001’: Permission denied
find: ‘./run/user/11024’: Permission denied
find: ‘./run/user/11022’: Permission denied
find: ‘./run/user/11025’: Permission denied
find: ‘./run/chrony’: Permission denied
find: ‘./run/udisks2’: Permission denied
find: ‘./etc/stunnel’: Permission denied
find: ‘./etc/credstore’: Permission denied
find: ‘./etc/xinetd.d’: Permission denied
find: ‘./etc/multipath’: Permission denied
find: ‘./etc/polkit-1/rules.d’: Permission denied
find: ‘./etc/ssl/private’: Permission denied
find: ‘./etc/sudoers.d’: Permission denied
find: ‘./etc/credstore.encrypted’: Permission denied
find: ‘./boot/efi’: Permission denied
find: ‘./boot/lost+found’: Permission denied
find: ‘./sys/kernel/tracing’: Permission denied
find: ‘./sys/kernel/debug’: Permission denied
find: ‘./sys/fs/pstore’: Permission denied
find: ‘./sys/fs/bpf’: Permission denied
find: ‘./home/bandit5/inhere’: Permission denied
find: ‘./home/bandit29-git’: Permission denied
find: ‘./home/bandit31-git’: Permission denied
find: ‘./home/drifter8/chroot’: Permission denied
find: ‘./home/ubuntu’: Permission denied
find: ‘./home/bandit27-git’: Permission denied
find: ‘./home/bandit30-git’: Permission denied
find: ‘./home/drifter6/data’: Permission denied
find: ‘./home/bandit28-git’: Permission denied
bandit6@bandit:/$
```

그러면 딱 파일 하나 찾을 수 있다
```ssh
./var/lib/dpkg/info/bandit7.password
```

cat 명령어를 사용하여 해당 파일 내용을 확인하면 password를 얻을 수 있다
```ssh
bandit6@bandit:/$ cat ./var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
