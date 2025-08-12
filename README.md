-----

# Entry Offline - Linux 설치 가이드

## 엔트리 오프라인 프로그램 리눅스 빌드

이 가이드는 **Ubuntu 20.04 이상** 버전을 기준으로 작성되었습니다.

### **설치 요구사항**

  - **네트워크** 연결
  - **10GB 이상의 여유 공간**
  - 전원 (선택)

-----

### **빌드 설치 가이드**

1.  **패키지 목록 업데이트**
    ```bash
    sudo apt update
    ```
2.  **필수 패키지 설치**
    ```bash
    sudo apt install build-essential clang libdbus-1-dev libgtk-3-dev libnotify-dev libasound2-dev libcap-dev libcups2-dev libxtst-dev libxss1 libnss3-dev gcc-multilib g++-multilib libusb-1.0-0-dev curl gperf bison python3-dbusmock openjdk-8-jre git nodejs npm -y
    ```
3.  **엔트리 빌드 파일 가져오기**
    ```bash
    git clone https://github.com/entrylabs/entry-offline.git && cd entry-offline
    ```
4.  **npm 패키지 설치**
    ```bash
    npm install -g electron-builder cross-env
    ```
5.  **`package.json` 파일 수정**
    ```bash
    nano package.json
    ```
    파일을 열고, `"dist:mac": ...` 아래에 다음 내용을 추가하세요.
    ```json
    "dist:linux": "electron-builder --linux"
    ```
6.  **세팅하기**
    ```bash
    npm run dist:linux
    ```
7.  **빌드하기**
    ```bash
    electron-builder --linux
    ```
8.  **권한 부여 & 실행**
    ```bash
    sudo chmod +x /dist/*.AppImage
    sudo ./dist/*.AppImage
    ```
    이제 엔트리 오프라인 프로그램이 실행됩니다.

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
