# Wsl2-with-X_Server
3분카레 에디션

## 목차
1. ~/.bashrc 에 내용추가
2. 방화벽 설정
3. 테스트
### 1. ~/.bashrc 에 아래와 같은 내용 추가
```bash
export DISPLAY=$(awk '/nameserver / {print $2; exit}' /etc/resolv.conf 2>/dev/null):0  
export LIBGL_ALWAYS_INDIRECT=1
```  
### 2. 윈도우 방화벽에서 인바운드 6000번 포트 허용 
#### 서순
제어판 -> Windows Defender 방화벽 -> 고급설정    
인바운드 규칙 -> 새규칙 -> 규칙종류(포트 -> 특정포트 ->TCP/6000)
### 3. 테스트
```bash
# Ubuntu 
sudo apt-get install x11-apps # 설치 
xclock # 실행후 창이 뜨면 성공
```