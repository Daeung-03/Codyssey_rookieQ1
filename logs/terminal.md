## 1. 터미널 조작 로그
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % pwd  
/Users/hugeung/Documents/Codyssey/Codyssey1st_rookie  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % ls -la  
total 8  
drwxr-xr-x@  5 hugeung  staff  160 Apr  1 15:27 .  
drwxr-xr-x   7 hugeung  staff  224 Apr  1 15:25 ..  
drwxr-xr-x@ 13 hugeung  staff  416 Apr  1 15:25 .git  
-rw-r--r--@  1 hugeung  staff   84 Apr  1 15:25 README.md  
drwxr-xr-x@  3 hugeung  staff   96 Apr  1 15:28 docs  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % cd docs  
hugeung@gimdaeung-ui-MacBookAir docs % cd ..  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % mkdir practice  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % cd practice   
hugeung@gimdaeung-ui-MacBookAir practice % touch test.txt    
hugeung@gimdaeung-ui-MacBookAir practice % mv test.txt ..  
hugeung@gimdaeung-ui-MacBookAir practice % mv test.txt renamed.txt  
mv: rename test.txt to renamed.txt: No such file or directory  
hugeung@gimdaeung-ui-MacBookAir practice % rename test.txt renamed.txt test.txt  
zsh: command not found: rename  
hugeung@gimdaeung-ui-MacBookAir practice % mv test.txt renamed.txt   
mv: rename test.txt to renamed.txt: No such file or directory   
hugeung@gimdaeung-ui-MacBookAir practice % cd ..   
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % mv test.txt renamed.txt   

ls: list directory contents, -l: long list format, -a: all(숨김파일 표시)   

## 2. 절대경로 vs 상대경로
절대경로: /Users/username/my-workspace (루트부터 시작)
상대경로: ./my-workspace 또는 ../ (현재 위치 기준)
dot은 현재 위치를 의미, ..은 상위 폴더를 의미

## 3. 권한 실습
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % ls -l renamed.txt.  
-rw-r--r--@ 1 hugeung  staff  0 Apr  1 15:29 renamed.txt.  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % chmod 755 renamed.txt.  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % ls -l renamed.txt.  
-rwxr-xr-x@ 1 hugeung  staff  0 Apr  1 15:29 renamed.txt.  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % chmod 644 Codyssey1st_rookie.  
chmod: Codyssey1st_rookie: No such file or directory.  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % chmod 644 practice.  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % ls -l practice.    
total 0.  
ls: fts_read: Permission denied.  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % chmod 755 practice.  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % ls -l practice       
total 0.  
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % ls -l
total 8
-rw-r--r--@ 1 hugeung  staff  84 Apr  1 15:25 README.md   
drwxr-xr-x@ 3 hugeung  staff  96 Apr  1 15:28 docs   
drwxr-xr-x@ 2 hugeung  staff  64 Apr  1 15:30 practice   
-rwxr-xr-x@ 1 hugeung  staff   0 Apr  1 15:29 renamed.txt   
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % xattr renamed.txt   
com.apple.provenance   


index 기준으로 0: file or directory, 1~3: User, 4~6: Group, 7~9: Others, 10: 확장 속성   
그룹, 유저는 OS에서 저장됨.
r = 읽기(4), w = 쓰기(2), x = 실행(1).  
755 = 7(rwx) 5(r-x) 5(r-x) -> 숫자 더하면 됨. 4(r--), 6(rw-).   

