# githubTest

- git 명령어 test


## intelij git 계정 두 개 사용법

- token 발급
    - github settings → Developer settings
    
    ![01](https://github.com/ChoiBongGeun/githubTest/assets/32670745/03f67bb4-07ed-4bfa-9e36-816bf7c82bc0)
    
    ![02](https://github.com/ChoiBongGeun/githubTest/assets/32670745/853a83d9-cb28-4ff5-9488-0c359dc9aee5)
    
    - token 생성
        - Note: 이름지정
        - Expiration: 토큰유효기간지정
        - select scopes: repo, gist, read:org, workflow를 필수 체크
- token 적용
    - file → settings → version Control → GitHub → Login with token
    
    ![03](https://github.com/ChoiBongGeun/githubTest/assets/32670745/dd8c045c-2da4-4e64-b15b-ef9c23a07943)
    
    - git auto fetch
        - set as default account for current project 선택 후 진행
        
        ![image](https://github.com/ChoiBongGeun/githubTest/assets/32670745/a85dad29-653f-44ed-a504-bea41021c7c9)
        

## git commit 취소

아래 사진 처럼 이상한 commit인 ‘잘못된 커밋 ’이 들어 갔을 때 해결 방법

![05](https://github.com/ChoiBongGeun/githubTest/assets/32670745/016698fc-885d-4d70-8585-a54ff023e947)

- **git reset**
    - 커밋 내역들을 삭제하고, 특정 시점의 커밋으로 되돌아감.
    - 이력이 같이 사라지기 때문에 깔끔한 이력을 유지 할 수 있다
    - intellij에서 reset 하는 법
        1. 정상적인 커밋 부분에서 우 클릭후 reset current Branch to Here 클릭
        2. Hard 체크 Reset
            
            ![06](https://github.com/ChoiBongGeun/githubTest/assets/32670745/abe276c2-20f6-40a8-8916-c74a0fb97c4e)
            
        3. git force push
        
        ![07](https://github.com/ChoiBongGeun/githubTest/assets/32670745/ed3705ba-8e79-4de0-ba87-7ad2ed475fb4)
        
        ![08](https://github.com/ChoiBongGeun/githubTest/assets/32670745/dbc0e2d5-84ec-4112-ae6f-7d2a437b4dd1)
        
        깔끔하게 지워진 이력 확인 가능 
        
        - 주의 사항
            - reset 전 누군가 잘못된 커밋을 pull로 가지고와 이력이 남아 있다면 commit 할때 reset 한 이력이 다시 들어갈 가능성이 있음
            - 사내를 예시로 들면 develop의 경우 여러 branch가 만들어지고 pull 받은 사람이 많기 때문에 문제가 생길 가능성이 높다
            - main의 경우 대부분의 사람이 pull 하지 않고 있기 때문에 main에 잘못 pr 날렸을 경우 시도 해볼 수 있다

- **git revert**
    - 이전 커밋 내역들은 그대로 두고, 되돌리고 싶은 커밋의 코드만 복원
    - 이력이 남고 다른 사람들과 같이 작업 할 때 문제가 좀 덜 생긴다
    - intelij에서 revert 하는 법
        1. revert할 commit에 우 클릭 후 Revert Commit 클릭 
            
            ![09](https://github.com/ChoiBongGeun/githubTest/assets/32670745/03be8223-848b-4575-8474-6bcf66fc56e9)
            
        2. git push 
        3. 아래와 같이 revert 표시와 함께 표시 
            
            ![10](https://github.com/ChoiBongGeun/githubTest/assets/32670745/41e9295a-60fa-4fb8-b619-beae411f6757)
            
            - 주의 사항
                - 잘못된 커밋 이외에 많은 수정 사항이 commit 되어 있다면 conflict 가 날 가능성있다
                - revert 후 conflic까지 해결 하여 문제 없도록 까지 해서 commit 해야 revert 완료
