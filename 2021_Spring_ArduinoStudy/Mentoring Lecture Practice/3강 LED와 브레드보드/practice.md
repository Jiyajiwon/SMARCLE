## Arduino Sketch
![image](https://user-images.githubusercontent.com/78032658/113332163-c87eeb00-935b-11eb-8534-4d0c5c8e86c1.png)
1. setup()
: 아두이노 명령에 필요한 세팅
3. loop()
: 실제로 명령 내리는 데 주로 사용

<hr/>

## 오렌지보드에 대한 정보
* MicroUSB를 사용한다.(스마트폰 충전기로 주로 사용하는 단자)
* 도구-보드-아두이노UNO(호환보드)

## 포트 선택이 되지 않을 때/인식이 안 될 때 해결방법
* 해당 USB 장치가 알 수 없는 장치로 저장되어있는 경우 -> 해당 USB 장치의 저장된 정보를 제거하여 재인식시키는 방법
>1. 제어판 -> 하드웨어 및 소리
>2. 장치 및 프린터 -> 장치 관리자
>3. 기타 장치 -> 알 수 없는 장치 -> 제거 -> 케이블 재연결
* USB 드라이버가 제대로 설치되지 않았을 때 (성공한 방법!)
>1. [ftdichip](https://ftdichip.com/drivers/vcp-drivers/, "드라이버 다운로드")에 접속한다.
>2. 각자 OS에 맞는 드라이버를 다운 받는다. (나는 windows 설치)
>3. 압축 풀고 해당 파일을 C:\Program Files (x86)\Arduino\drivers\FTDI USB Drivers 폴더에 옮긴다.
>4. 장치관리자에 들어간다. -> 드라이버 업데이트 -> 드라이버 소프트웨어 검색 -> 직접 선택
>5. 된다!
  
<hr/>

## 1. "Hello world" 출력하기
1. 코드 입력

```c
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600); //시작한다. 통신속도는 9600.
}

void loop() {
  // put your main code here, to run repeatedly:
  Serial.println("Hello world") // 시리얼 모니터에 출력할 내용
}
```
2. 업로드(화살표 기호) -> 컴파일
3. 시리얼 모니터 확인(우측 상단)


- Serial의 s는 대문자다.


###### 포트: USB 몇 번에 꽂혀있는가 말해야 아두이노 코드 업로드 가능  
###### 오렌지보드는 MicroUSB를 사용한다.

<hr/>

## 2. 보드 LED 깜빡여보기
### 1. LED 켜기
```c
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600); //시작한다. 통신속도는 9600.
  pinMode(13, OUTPUT); // n번 핀을 x 용도로 쓰겠다.
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(13,HIGH); // LED 켰다 껐다, (핀 번호, 전류 흐르게(H) 안 흐르게(L))
}
```
![image](https://user-images.githubusercontent.com/78032658/113338498-28798f80-9364-11eb-97ae-dfef25d9c89f.png)

### 2. LED 끄기
```c
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600); //시작한다. 통신속도는 9600.
  pinMode(13, OUTPUT); // n번 핀을 x 용도로 쓰겠다.
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(13,LOW); // LED 켰다 껐다, (핀 번호, 전류 흐르게(H) 안 흐르게(L))
}
```
![image](https://user-images.githubusercontent.com/78032658/113338567-3fb87d00-9364-11eb-98d6-73058eb54f07.png)

### 3. 1초 간격으로 껐다 켰다하기
```c
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600); //시작한다. 통신속도는 9600.
  pinMode(13, OUTPUT); // n번 핀을 x 용도로 쓰겠다.
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(13,HIGH);

  delay(1000); // 시간 단위 == ms(밀리세컨드), 1000ms == 1s
  
  digitalWrite(13,LOW); // LED 켰다 껐다, (핀 번호, 전류 흐르게(H) 안 흐르게(L))

  delay(1000); // 여기도 delay 넣어야 함. 안 그러면 껐(1초)->켰(0초)->껐(1초)... 라서 계속 꺼져 있음
}
```
