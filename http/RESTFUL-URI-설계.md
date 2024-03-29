# URI 설계 규칙

URI를 설계할 때는 기본적으로 `리소스`를 식별한다고 생각하면 된다.
```
회원을 등록, 수정, 삭제하는 프로그램에 대한 URI를 설계한다면 회원이 리소스가 된다.

/members
```

`리소스`와 `행위`를 분리해줘야 한다.
URI에는 `리소스`만 담고 `행위`는 GET, POST, PUT, DELETE 등의 메소드로 구분할 수 있다.  


## 권장 사항
### 1. 명사 사용
동작이 아닌 `명사`인 `리소스`를 참조해야 한다.  
`리소스`는 `document`, `collection`, `store`로 구분할 수 있다.  

#### 1-1. document  
단일 개념
#### 1-2. collection
서버가 관리하는 리소스 저장소로 서버가 URI를 지정해준다.
```
HTTP/1.1 201 Created
Location: /members/100
```
여기서 컬렉션은 /members가 된다.
`POST` 메소드가 갖는 특징이며 클라이언트는 등록될 리소스의 URI를 모르며 서버가 관리한다.
#### 1-2. store
클라이언트가 관리하는 리소스 저장소로 처음부터 클라이언트는 등록될 리소스의 URI를 알고 있다.
```
/files/{fileName}
```
여기서 스토어는 /files가 된다.
`PUT` 메소드의 특징이기도 하다.  

### 2. 슬래시(/) 사용
`슬래시(/)`를 사용하여 계층형 구조를 띄어야 한다.
### 3. 후행 슬래시 금지
URI 마지막 경로에는 슬래시를 사용하지 않는다.
```
/members/ (x)
/members (o)
```
### 4. 하이픈(-) 사용
가독성을 위해 `하이픈(-)`를 사용하여 긴 단어는 구분해준다.
### 5. 언더바(_) 지양
`언더바(_)` 대신 `하이픈(-)`을 사용하자  
응용프로그램의 폰트에 따라 `언더바(_)`가 사라지거나 보이지 않을 수 있다.  
### 6. 소문자 사용
### 7. 파일 확장자 사용 지양
### 8. CRUD 메소드 명 사용 금지
`리소스`와 `행위`는 분리해야 한다. CRUD는 메소드로 명시해주면 된다.
### 9. 쿼리스트링 사용
조회할 때 정렬, 필터 등을 사용해야 할 때는 URI를 별도로 사용하지 않고 기존 URI에 쿼리스트링을 활용한다. 
### 10. 동사 사용 지양
`리소스` - `명사`로 URI를 설계해야 한다.  

- exception  
  `컨트롤 URI`  
  모든 URI를 명사로만 설계하면 좋겠지만 현실적으로 불가능할 때가 많다. 문서, 컬렉션, 스토어로 해결하기 어려울 때는 프로세스를 나타내는 동사를 사용한다.  
  ```
  /members/{id}/delete
  ```

----  

> 참고  
[REST API URI Naming Conventions and Best Practices](https://restfulapi.net/resource-naming/)




