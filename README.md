-----

# Entry Offline - Linux 설치 가이드

## 엔트리 오프라인 프로그램 리눅스 빌드

이 가이드는 **Ubuntu 20.04 이상** 버전을 기준으로 작성되었습니다.

### **설치 요구사항**
> 1GB의 여유 공간  
> 전원(선택)

### **설치 방법**
1. [릴리즈 메뉴](https://github.com/ijastor/entry-offline_linux/releases/tag/Entry)에 들어가 `Entry-2.1.29.AppImage`를 다운받습니다.
2. 다운로드 한 위치에서 터미널을 열고, 아래의 명령어를 입력 합니다.
```bash
./Entry-2.1.29.AppImage --no-sandbox
```

-----

### **Wine을 통한 설치 및 실행**

리눅스에서 윈도우용 엔트리 프로그램을 설치하고 실행하는 방법입니다.

1.  **Wine 설치**
    ```bash
    sudo apt install wine
    ```
2.  **윈도우용 설치 파일 다운로드**
    [https://playentry.org/download/offline](https://playentry.org/download/offline)에 접속하여 **Windows 64bit용** 파일을 다운로드하세요.
3.  **설치 진행**
    다운로드한 파일의 경로에서 다음 명령어를 실행합니다.
    ```bash
    wine (다운로드된_파일.exe)
    ```
4.  **프로그램 실행**
    설치가 완료되면, 다음 경로에서 `Entry.exe` 파일을 찾아 Wine으로 실행하면 됩니다.
    ```bash
    wine ~/.wine/drive_c/Entry/Entry.exe
    ```

-----
