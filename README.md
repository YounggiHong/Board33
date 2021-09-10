# 발견된 문제점
## 1. '조회' WriteDAO.xml의 33번째 resultType 문제
>**원인** : resultType부분의 com.lec.spring.WriteDTO에 .domain이 빠져서 목록이 불러와 오질 않는다.

```html
    <textarea name= "com.lec.spring.WriteDTO"> ->  <textarea name= "com.lec.spring.domain.WriteDTO">
```
## 2.'수정' updateOk.jsp의 태그 문제 발생

> **원인** :  view.do?uid=${uid}부분에 param이 빠져서 수정 이후 오류 발생.
```html
    <textarea name="view.do?uid=${uid}"> -> <textarea name="view.do?uid=${param.uid}">
```

## 3.'삭제' WriteDAO.xml에서 컬럼명 문제

> **원인** : WriteDAO.xml의 59번째 줄인 DELETE FROM test_write WHERE uid = #{uid} wr이 빠져서 삭제버튼 누른이후 오류 발생

```html
    <textarea name="WHERE uid = #{uid}"> -> <textarea name="WHERE wr_uid = #{uid}">
```







