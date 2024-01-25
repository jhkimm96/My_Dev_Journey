# 영화정보 DUMP SQL IMPORT

## MYSQL CLIENT 를 통한 DUMP 파일 IMPORT

- mysql client 접속
- mysql -u root -p : 루트권한 먼저 접속필요!
    - 패스워드 입력
- show databases; : 현재 데이터 베이스 확인
- use database; : 사용할 데이터 베이스 선택
- create database kobis_db : kobis_db라는 데이터 베이스 생성
- select Host, User, Password from user; : user 권한 확인
- create user ‘kobis_user’@’localhost’ identified by ‘kobis1234’; : 권한 생성
- grant all privileges on kobis_db.* to ‘kobis_user’@’localhost’ identified by ‘kobis1234’ : 권한 적용
- flush privileges : 권한 적용후 꼭 이 문구 입력해야 한다!

### **import**

mysql 접속, root 계정이 아니어도 됨.

```html
mysql -u root -p

아니면

mysql -u root kobis_user -p
```

해당 커멘드 입력시 프롬프트로 비밀번호 입력 해서 접속

기존에 만들어 놓은 database 선택 혹은 새로 생성

```html
CREATE DATABASE kobis_db

USE kobis_db
```

source 명령어로 sql파일 import후 쿼리 실행해서 확인해보기

```html
source [파일경로]/[파일명].sql

source C:\Users\khous\OneDrive\바탕 화면/kobis_db_dump.sql
```

### **export**

```html
mysqldump -u [사용자 계정] -p [패스워드] [원본 데이터베이스명] > [생성할 백업 DB명].sql

ex) mysqldump -u root -p db > db.sql
passowrd: 0000
```

### **DBEAVER 무료 툴로 데이터베이스 연결**

![Untitled](%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%87%E1%85%A9%20DUMP%20SQL%20IMPORT%200fdf1439f5804f06b1f0cbe6ddc55240/Untitled.png)