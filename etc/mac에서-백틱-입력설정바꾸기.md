# MAC OS에서 백틱 입력 설정 바꾸기

영어 입력인 상태에서만 백틱이 입력되어 한글을 입력하는 도중에 백틱을 사용할 때마다 영어로 굳이 바꿔줘야 하는 불편함이 있음.

`DefaultKeybindings` 설정을 변경해주면 된다.  


#### 1. KeyBindings 폴더 생성
```
mkdir -p ~/Library/KeyBindings
```

#### 2. DefaultKeyBinding.dict 파일 생성
```
vi ~/Library/KeyBindings/DefaultKeyBinding.dict
``` 

#### 3. 설정 파일 작성
```bash
{
    "₩" = ("insertText:", "`");
}
```

재부팅 후 한글 모드에서도 백틱을 마음껏 사용할 수 있다!   
되돌리고 싶으면 해당 설정 파일을 지우면 된다.