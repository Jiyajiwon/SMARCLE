## **1. 3색 LED를 사용하여 신호등 만들기**

* 저항/LED 연결 시 다른 저항/LED 다리에 걸리면 안 된다. 즉, 같은 신호를 공유하게 하면 안 된다. (b/c 빨노초 독립 제어)

### **코드**
```c
int green = 12; // 초록색 LED를 12번으로
int yellow = 10; 
int red = 8; 

void setup() {
  // put your setup code here, to run once:
  pinMode(green,OUTPUT);
  pinMode(yellow,OUTPUT);
  pinMode(red,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly: 
  digitalWrite(green,HIGH); // 초록불 켜기
  digitalWrite(yellow,LOW); // 노란불 끄기
  digitalWrite(red,LOW); // 빨간불 끄기
  delay(1000); // 1초 대기

  digitalWrite(green,LOW); // 초록불 끄기
  digitalWrite(yellow,HIGH); // 노란불 켜기
  digitalWrite(red,LOW); // 빨간불 끄기
  delay(1000); // 1초 대기
  
  digitalWrite(green,LOW); // 초록불 끄기
  digitalWrite(yellow,LOW); // 노란불 끄기
  digitalWrite(red,HIGH); // 빨간불 켜기
  delay(1000); // 1초 대기
}
```

### **회로도**
![신호등](https://user-images.githubusercontent.com/78032658/113432748-ec543680-9418-11eb-9068-1c87091a7c1a.png)

### **실행 모습**
![image](https://user-images.githubusercontent.com/78032658/113432849-13ab0380-9419-11eb-8e0b-4a5bcbd8fe3c.png)
![image](https://user-images.githubusercontent.com/78032658/113432857-160d5d80-9419-11eb-8aec-1bd9064b6489.png)
![image](https://user-images.githubusercontent.com/78032658/113432864-19a0e480-9419-11eb-8969-72d8bcefd4c4.png)

