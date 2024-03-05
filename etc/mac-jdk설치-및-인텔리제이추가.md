### 1. jdk 설치
Homebrew가 설치되었다는 전제  
<br>
- java17 설치
```
brew install openjdk@17
```

- 환경변수 설정
```
echo 'export PATH="/opt/homebrew/opt/openjdk@17/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

### 2. ide
#### intellij에서 내가 설치한 jdk 추가하기  
인텔리제이에 내장된 기능으로 jdk를 설치할 수 있지만 나는 터미널을 통해 직접 설치하였고 해당 openjdk를 인텔리제이에 추가하고자 했다.  
Add JDK...를 누를 시 자동으로 `JavaVirtualMachines` 폴더 경로가 불러와지는데 `homebrew`를 통해 설치한 jdk는 해당 경로에 존재하지 않았다.  
내가 설치한 jdk를 추가하기 위해 `cmd + shift + g`를 누른 뒤 설치 경로를 입력해주면 된다.   

<img width="874" alt="스크린샷 2024-03-04 오후 11 15 20" src="https://github.com/2024-SpringStudy/spring/assets/122238744/1d31df4c-60d8-4876-b130-0f15ceddc898">

여기서 계속 Home directory가 아니라며 추가가 되지 않았는데 `/opt/homebrew/opt/openjdk@17/17.0.10/libexec/openjdk.jdk/Contents` 까지 들어가서 `Home` 폴더를 선택해주니 추가 완료!  
