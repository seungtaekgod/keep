# 3장

## 1.

```sql
select bookname from BOOK where bookId = 1;
select bookname from BOOK where price >= 20000;
select sum(salePrice) from Orders
where custId = (select custId from customer where name = '박지성');
select count(*) from Orders
where custid = (select custId from Customer where name = '박지성');
select count(distinct publisher) from BOOK B
join orders O on o.bookId = B.bookId
where custid = (select custId from Customer where name = '박지성');
select bookname, price, abs(price - salePrice) from Orders O
join BOOK B on O.bookId = B.bookId
where custId = (select custid from customer where name = '박지성');
select bookname from Orders O
join BOOK B on O.bookId = B.bookId
where B.bookId not in (
  select bookid from orders
  where custid = (select custid from Customer where name = '박지성')
)
group by bookname;
```

## 2.

```sql
select count(*) from BOOK;
select count(distinct publisher) from BOOK;
select name, address from Customer;
select orderId from Orders
where orderdate between '2024-07-04' and '2024-07-07';
select orderId from Orders
where orderdate not between '2024-07-04' and '2024-07-07';
select name, address from Customer
where name like "김%";
select name, address from Customer
where name like "김%이";
select name from Customer
where custid not in (select custid from Orders);
select sum(salePrice), avg(salePrice) from Orders;
select name, sum(salePrice) from Orders O
join Customer C on C.custId = O.custId
group by name;
select name, bookId from Orders O
join Customer C on C.custId = O.custId
group by name, bookid;
select * from Orders
where orderId = (
  select orderid from Orders o
  join BOOK b on o.bookId = b.bookId
  order by abs(o.salePrice - b.price) desc
  limit 1
);
select C.name from orders o
join Customer C on C.custId = O.custId
group by C.name
having avg(o.salePrice) > (select avg(salePrice) from Orders);
```

## 3.

```sql
select name from Customer C
join Orders O on C.custId = O.custId
join BOOK B on B.bookId = O.bookId
where B.publisher in (
  select B1.publisher from Customer C1
  join Orders O1 on C1.custId = O1.custId
  join BOOK B1 on B1.bookId = O1.bookId
  where C1.custId = (select custid from customer where name = '박지성')
)
and C.name != '박지성';

select name from Customer c
join orders o on c.custId = o.custId
join BOOK b on b.bookId = o.bookId
group by c.name
having count(distinct b.publisher) >= 2;

select b.bookId, b.bookname from BOOK b
join Orders O on b.bookId = O.bookId
group by b.bookId
having count(*) >= 0.3 * (select count(*) from Customer);
```

## 4.

```sql
insert into book(bookid, bookname, publisher, price)
values('북 아이디가 필요하다.','스포츠 세계', '대한미디어', 10000);

delete from book where publisher = "삼성당";
delete from book where publisher = "이상미디어";

update book
set publisher = '대한출판사'
where publisher = '대한미디어';

create table Bookcompany (
  name varchar(20) primary key,
  address varchar(20),
  begin date
);

alter table bookcompany add webaddress varchar(30);

insert into bookcompany(name, address, begin, webaddress)
values('한빛아카데미','서울시 마포구','1993-01-01','http://hanbit.co.kr');
```

## 5.

(1) 책을 안 산 고객들  
(2) 책을 산 고객들

## 6.

- DDL: create, alter, drop  
- DML: select, insert, delete, update  
- DCL: grant, revoke

## 7.

```sql
select * from R where A = 'a2';
select A, B from R;
select * from R join S on R.C = S.C;
```

## 9.

10

## 10.

8개

## 11.

a: 2, B: 2


