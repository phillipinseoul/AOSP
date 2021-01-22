# AOSP
How to build AOSP in Ubuntu. (Android Device: Google Pixel 4 XL)

## 1. REPO 설치
### 홈 디렉터리에 bin/ 디렉터리가 있고 다음 경로에 포함되어 있는지 확인한다.
* $ mkdir ~/bin
* $ PATH=~/bin:$PATH

### Repo 런처를 다운로드하고 실행 가능한지 확인한다.
* $ curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
* $ chmod a+x ~/bin/repo

## 2. REPO Client 초기화
### 작업 파일을 보관할 빈 디렉터리("aosp_10" 이라 하자)를 만든다. (macOS를 사용하는 경우, 대소문자를 구분하는 파일 시스템이어야 한다.)
* $ mkdir aosp_10
* $ cd aosp_10

### Git을 실명과 이메일 주소로 구성한다.
* $ git config --global user.name "Your Name"
* $ git config --global user.email "you@example.com"

### repo init: 최근 버그가 수정된 최신 버전의 Repo를 다운로드한다. Android 소스에 포함된 다양한 저장소가 작업 디렉터리 내에 배치되는 위치를 지정하는 매니페스트의 URL을 지정해야 합니다.
* $ repo init -u https://android.googlesource.com/platform/manifest
* $ repo init -u https://android.googlesource.com/platform/manifest -b android-10.0.0_r7 (google coral에 해당)

## 3. Android Source Tree 다운로드
### 기본 매니페스트에 지정된 저장소에서 Android 소스 트리를 작업 디렉터리로 다운로드하려면 다음을 실행한다.
* $ repo sync

## 4. Android 빌드 시작
### envsetup.sh: 환경을 초기화한다.
* $ source build/envsetup.sh

### lunch을 사용하여 빌드할 대상을 선택한다.
* $ lunch
* 14번 (coral) 선택

### Code 빌드
* $ m

### 빌드 실행 (Android 기기 시뮬레이션)
* $ emulator

### 기기 flash
* $ make fastboot adb



