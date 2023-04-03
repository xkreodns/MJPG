# MJPG

- chat gpt mjpg
    
    라즈베리파이 웹캠을 사용하여 MJPG 실시간 스트리밍을 실행하는 방법은 다음과 같습니다.
    
    1. 라즈베리파이에 웹캠 연결하기
    
    라즈베리파이에 웹캠을 연결합니다. 대부분의 웹캠은 USB 포트에 연결할 수 있습니다.
    
    1. MJPG-Streamer 설치하기
    
    MJPG-Streamer는 라즈베리파이에서 웹캠을 사용하여 MJPG 스트리밍을 제공하는 오픈 소스 소프트웨어입니다. 터미널을 열고 다음 명령어를 입력하여 MJPG-Streamer를 설치합니다.

터미널 창 열고 명령어를 입력합니다.
sudo apt-get install libjpeg-dev imagemagick libv4l-dev
cd /tmp
git clone https://github.com/jacksonliam/mjpg-streamer.git
cd mjpg-streamer/mjpg-streamer-experimental
make clean all
sudo make install

스티리밍 서버 시작명령어
mjpg_streamer -i "input_uvc.so -d /dev/video0 -r 640x480 -f 15" -o "output_http.so -p 8080 -w /usr/local/share/mjpg-streamer/www"

위 명령어에서, **`-i`**는 입력 플러그인을 지정하는 옵션입니다. **`-d`**는 웹캠 장치를 지정하는 옵션입니다. **`-r`**은 해상도를 지정하는 옵션입니다. **`-f`**는 프레임 속도를 지정하는 옵션입니다.

- **`o`**는 출력 플러그인을 지정하는 옵션입니다. **`p`**는 포트 번호를 지정하는 옵션입니다. **`w`**는 웹 페이지 파일의 경로를 지정하는 옵션입니다.
1. 웹 브라우저에서 스트리밍 확인하기

라즈베리파이의 IP 주소와 포트 번호를 사용하여 웹 브라우저에서 스트리밍을 확인할 수 있습니다. 기본 포트는 8080입니다. 따라서 브라우저에서 다음 URL을 엽니다.

```
javascriptCopy code
http://<라즈베리파이 IP 주소>:8080

```

위와 같이 입력하면, 라즈베리파이 웹캠으로부터 전송되는 MJPG 스트림을 확인할 수 있습니다.

안된다고 당황하지말고 reboot 하고 다시하기
 
