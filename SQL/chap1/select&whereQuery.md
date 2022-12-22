# 1주차

쿼리문:  데이터베이스에 명령을 내리는 것

**Select 쿼리문** : 데이터를 선택해서 가져오겠다는 의미

**테이블과 필드** :

테이블 : 데이터가 담긴 엑셀 시트와 동일

필드 :데이터베이스 시스템에서 처리의 최소 단위

**문법정리**

```jsx
//테이블 보기
show tables 
//select문 
select * from orders
//where절 (1)원하는 테이블 (2) 조건 
select * from users wher name = "황**"

```

**where절과 자주 같이 쓰는 문법**

between

in

like

**이외 유용한 문법**

limit

distinct

count