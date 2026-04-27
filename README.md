#  Flask Web Server LED Control (Raspberry Pi)

라즈베리파이와 Flask 웹 서버를 활용하여
웹 브라우저에서 LED를 ON/OFF 제어하는 IoT 프로젝트입니다.

---

##  프로젝트 개요

이 프로젝트는 Python 기반의 **Flask 웹 서버**와
라즈베리파이의 **GPIO 핀 제어**를 결합하여

 웹에서 버튼 클릭 또는 URL 접근으로
 실제 LED를 제어하는 시스템을 구현합니다.

---

##  사용 기술

* Python 3
* Flask
* gpiozero
* Raspberry Pi

---

##  하드웨어 구성

| 부품           | 설명    |
| ------------ | ----- |
| LED (Red)    | 출력 장치 |
| 330Ω 저항      | 전류 제한 |
| 점퍼 케이블       | 연결    |
| Raspberry Pi | 제어 장치 |

### 연결 방법

* LED 긴 다리 → GPIO 21
* LED 짧은 다리 → 330Ω 저항 → GND

---

##  실행 방법

### 1. Flask 설치

```bash
sudo apt-get install python3-flask
```

### 2. 코드 실행

```bash
sudo python3 main20.py
```

### 3. 웹 접속

브라우저에서 아래 주소 입력

```
http://<라즈베리파이_IP주소>/
```

---

##  기능 설명

### 기본 페이지

* `/`

```
hello Flask 출력
```

### LED 제어

* `/ledon` → LED ON
* `/ledoff` → LED OFF

 웹 요청을 통해 GPIO 신호를 제어하는 구조

---

##  HTML 기반 제어 (선택)

`main20-1.py` 사용 시
웹 페이지 버튼으로 제어 가능

### 추가 설정

```
project_20/
 └── templates/
     └── index.html
```

* 버튼 클릭 → POST 요청 → LED 제어

---

##  동작 원리

1. 사용자가 웹에서 요청 (/ledon 또는 /ledoff)
2. Flask 서버가 요청 수신
3. GPIO 핀 제어 코드 실행
4. LED ON/OFF 동작

---

##  결과

* `/ledon` 접속 → LED 켜짐
* `/ledoff` 접속 → LED 꺼짐

---

##  주의사항

* 반드시 `sudo` 권한으로 실행해야 GPIO 제어 가능
* IP 주소는 실행할 때마다 변경될 수 있음 (`ifconfig`로 확인)
* 포트 80 사용 시 관리자 권한 필요

---

##  참고

* Flask 공식 문서: https://flask.palletsprojects.com/
* Raspberry Pi GPIO: https://gpiozero.readthedocs.io/

---

##  확장 아이디어

* 여러 개의 LED 제어
* 스마트폰 UI 최적화
* 센서 연동 (온도, 움직임 등)
* IoT 스마트홈 시스템 확장

---
