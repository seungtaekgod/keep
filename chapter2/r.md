2장  
1. (2)  
2. (4)  
3. (3)  
4. (1)  
5. (1)  
6. (1)  
7. (3)  
8. (3)  
9. (4)  
10. (5)  

11.  
- (1) 후보키 아님. 불필요한 속성을 포함하지 않는 최소한의 속성을 가져야 하기 때문.  
- (2) 대체키라서 슈퍼키가 맞음  
- (3) NULL 값 X  
- (4) 가질 수 있음  

12.  
- (1) R: A, S: (C,D), (C,E)  
- (2) R의 기본키 (A), S의 기본키 (C,D)  

13.  
(1) a2인 튜플 반환  
(2) A, B 속성 가진 것만 반환  
(3) a2 b1  
(4) 다 곱한 결과 반환  
(5) (a1, b1, c1, c1, d2, e1), (a1, b1, c1, c1, d1, e2),  
  (a2, b1, c1, c1, d2, e1), (a2, b1, c1, c1, d1, e2),  
  (a3, b1, c2, c2, d3, e3)  
(6) Left Outer Join  
  (a1, b1, c1, c1, d2, e1), (a1, b1, c1, c1, d1, e2),  
  (a2, b1, c1, c1, d2, e1), (a2, b1, c1, c1, d1, e2),  
  (a3, b1, c2, c2, d3, e3), (a4, b2, c4, NULL, NULL, NULL)  
(7) Right Outer Join  
  (a1, b1, c1, c1, d2, e1), (a2, b1, c1, c1, d2, e1),  
  (a1, b1, c1, c1, d1, e2), (a2, b1, c1, c1, d1, e2),  
  (a3, b1, c2, c2, d3, e3), (NULL, NULL, NULL, c5, d3, e3)  
(8) Full Outer Join  
  (a1, b1, c1, c1, d2, e1), (a1, b1, c1, c1, d1, e2),  
  (a2, b1, c1, c1, d2, e1), (a2, b1, c1, c1, d1, e2),  
  (a3, b1, c2, c2, d3, e3), (a4, b2, c4, NULL, NULL, NULL),  
  (NULL, NULL, NULL, c5, d3, e3)  
(9) (c1, c2, c4, c5)  
(10) (c1, c2)  

14.  
(1) victor, jane  
(2) id>=2, age=31  
(3) customer 테이블에서 job 테이블 join  
(4) name, age  

