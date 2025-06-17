# 4장

## 1.

```
ABS(-15) : 15, CEIL(15.7) : 16, COS(3.14159) : -1, FLOOR(15.7) : 15, LOG(10,100) : 2, MOD(11,4) : 3, POWER(3,2) : 9,
ROUND(15.7) : 16, SIGN(-15) : -1, TRUNCATE(15.7, 0) : 15, CHAR(67 USING utf8) : C, CONCAT('HAPPY','Birthday') : HAPPYBirthday,
LOWER('Birthday') : birthday, LPAD('Page 1',15,'*.') : *.*.*.*.*Page 1, REPLACE('JACK','J','BL') : BLACK, RPAD('Page 1',15,'*') : Page 1*********,
SUBSTR('ABCDEFG',3,4) : CDEF, TRIM(LEADING 0 FROM '00AA00') : AA00, UPPER('Birthday') : BIRTHDAY, ASCII('A') : 65,
LENGTH('Birthday') : 8, ADDDATE('2024-02-14', INTERVAL 10 DAY ) : 2024-02-24, LAST_DAY(SYSDATE()) : 2024-10-31,
NOW(): 2024-10-21 18:14:07, DATE_FORMAT(SYSDATE(), '%Y'): 2024, CONCAT(123): 123, CAST('12.3' AS DECIMAL(3,1)): 12.3,
IF(1=1, 'aa', 'bb'): aa, IFNULL(123, 345): 123, IFNULL(NULL, 123): 123
```

## 2.

```
(1). mybook표 그대로
(2). bookid 1,2,3 // ifnull(price,0) 10000, 20000, 0
(3). bookid 3 // price <null>
(4). bookid // price
(5). bookid 1,2,3 // price+100 10100, 20100, <null>
(6). sum(price)// avg(price) // count(*)
(7). count(*) 3 // count(price) 2
(8). sum(price) 30000 // avg(price) 15000
```

## 3.

```
(1). count(a) 2
(2). A 12,10 // B <null>,12
(3). A <null>,12,10 // 2,1,1
```

## 4.



## 5.

```
(1). 각 custid에 대한 custid, address, saleprice의 합
(2). 각 custid에 대해 이름과, 판매가의 평균 출력
(3). custid<=3, 주문한 고객중에 판매가 합
```

## 6.

답: 4

## 7.

```
(1). select distinct(name) from Customer
where address like '%대한민국%' and custid not in (select custId from orders);

(2). select name from Customer c
where not exists (select * from orders o where o.custId = c.custId) and address like '%대한민국%';

(3). select distinct(c1.name) from Customer c1
join Customer c2 on c1.custId = c2.custId
where c1.address like '%대한민국%' and c2.custId not in (select custid from orders);
```

## 8.

회원번호 1,2 // 등급 1,2

## 9.

2->3->4->5->1->6

## 10.

```
(1). 복잡한 쿼리 단순화: 자주 사용하는 복잡한 SELECT 문을 뷰로 만들어 쉽게 재사용할 수 있음
(2). 보안 강화: 특정 컬럼이나 행만 노출하도록 제한하여 사용자 접근 권한을 세밀하게 제어할 수 있음
(3). 논리적 독립성 제공: 실제 테이블 구조가 바뀌어도 뷰를 통해 일관된 인터페이스를 제공할 수 있음
```

## 11.

합계: 5000

## 12.

```
CREATE VIEW highorders AS
SELECT B.bookid, B.bookname, C.name AS customername, B.publisher, O.saleprice
FROM Book B
JOIN Orders O ON B.bookid = O.bookid
JOIN Customer C ON O.custid = C.custid
WHERE O.saleprice >= 20000;

SELECT bookname, customername FROM highorders;

DROP VIEW highorders;

CREATE VIEW highorders AS
SELECT B.bookid, B.bookname, C.name AS customername, B.publisher
FROM Book B
JOIN Orders O ON B.bookid = O.bookid
JOIN Customer C ON O.custid = C.custid
WHERE O.saleprice >= 20000;
```

# 5장

```
1. (1)
2. (1)
3. (1)
4. (1)
5. (3)
```

