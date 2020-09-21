# Insert

INSERT INTO tablename
(column1, column2...) => 모든 컬럼일 경우 생략 가능
VALUES(value1, value2...)

INSERT INTO table2 (col1, col2)  
SELECT * FROM table1  
WHERE condition;
> insert의 select 한 쿼리 응답 값이 들어간다. (col1,col2) 가 붙어있으므로 select에서도 똑같이 맵핑시켜줘야한다.  


![test](./image/test.png)