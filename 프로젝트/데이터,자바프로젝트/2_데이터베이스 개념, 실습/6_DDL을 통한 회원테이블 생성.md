# CRUD

## 1. CREATE

- INSERT, PUT/POST

```sql
INSERT INTO `member` 
(
	NAME, 
	EMAIL, 
	MOBILE_NO, 
	PASSWORD, 
	SMS_SEND_YN, -- BIT
	REGISTER_DATE, -- DATETIME
	BIRTH_DATE -- DATE
)
VALUES
(
	'김멤버',
	'KIMMEM@NAVER.COM',
	'01011111111',
	'1234',
	TRUE,
	NOW(),
	19890824
);
```

- 레코드를 구분할 수 있어야한다.
- PK : 주식별자키로 테이블의 모든 데이터를 식별하는 컬럼
    - 중복불가, NULL 불가
    - DBEAVER 에서 CONSTRAINT 에 들어가서 따로 PRIMARY KEY 추가 가능하다.
    
    ```sql
    ALTER TABLE testdb.`member` ADD CONSTRAINT EMAIL_PK PRIMARY KEY (id);
    ```
    
- FK : 외부 식별자키로 테이블 간의 종속 관계

## 2. READ

- SELECT , GET

```sql
SELECT *
FROM MEMBER
WHERE 1=1
AND EMAIL = 'KIMMEM2@NAVER.COM'
AND SMS_SEND_YN = TRUE;
```

## 3.UPDATE

- UPDATE , PUT/PATCH
- WHERE 조건에 맞는 정보만 UPDATE 할 수 있도록 해야한다.

```sql
UPDATE `member` 
SET 
	SMS_SEND_YN = TRUE
WHERE EMAIL = 'KIMMEM@NAVER.COM';

-- UPDATE '테이블명'
-- SET
--     컬럼명 = 'UPDATE할값',
--     컬럼명 = 'UPDATE할값'
-- WHERE 1=1
-- AND 컬럼명 = 조건값
		
```

## DELETE

- DELETE
- WHERE 조건에 맞는 정보만 DELETE 해야한다.

```sql
DELETE
FROM 테이블명
WHERE 삭제조건
```