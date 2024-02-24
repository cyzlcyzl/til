# fatal: Authentication failed for 에러 발생

```
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/cyzlcyzl/til.git/'
```


---

#### 1. Github > Settings > Developer Settings > Personal Access Tokens > Tokens
기존 만료된 토큰이 있다면 삭제
#### 2. Generate New Token
필요한 권한 체크해서 토큰 생성 후 복사
#### 3. git push
`Username`에는 깃허브 아이디, `Password`에 복사한 토큰을 입력
