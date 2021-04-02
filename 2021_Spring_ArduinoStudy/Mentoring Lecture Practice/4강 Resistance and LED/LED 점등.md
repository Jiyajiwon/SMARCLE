## **1. 저항을 이용해 LED 켜기**
* 긴 다리&동글이 부분: (+), 짧은 다리&평평한 부분: (-)
*  GND(ground) : (-)극

### 코드
```c
int green = 12; // 변수 green을 12로 지정

void setup() {
  // put your setup code here, to run once:
  pinMode(green,OUTPUT); // green(12)번째 pin을 OUTPUT모드로 사용한다.
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(green,HIGH); // green이라는 12번 칸에 전원 공급. 디지털을 쓴다.
  delay(1000); // 1초 지연
  digitalWrite(green,LOW); // green이라는 12번 칸에 전원 끔.
  delay(1000); // 1초 지연
}
```
### 회로도
![image](https://user-images.githubusercontent.com/78032658/113391981-5b0ca200-93cf-11eb-89c8-236d8ceb1845.png)

## 실행 모습
![image](https://user-images.githubusercontent.com/78032658/113389284-b9835180-93ca-11eb-8440-3fc56005022e.png)
![image](https://user-images.githubusercontent.com/78032658/113389321-cef87b80-93ca-11eb-9db5-ca1785ba2015.png)
