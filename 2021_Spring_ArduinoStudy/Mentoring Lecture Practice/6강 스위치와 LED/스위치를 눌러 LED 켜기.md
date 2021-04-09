## **스위치를 눌러 LED 켜기**
### **부품**
: 아두이노, 브레드보드, 스위치, 저항, 점퍼

### **주의**

* 저항은 LED의 (+) 쪽에 건다. 같은 신호를 공유하도록. 
* 저항은 극성이 없다.  
* 스위치 꽂을 때는 두 다리가 같은 신호를 공유하게 하면 안 된다. 따라서 중간에 홈을 사이에 두고 끼우는 것을 추천한다.

### **회로도**
![Untitled Sketch_bb](https://user-images.githubusercontent.com/78032658/114227956-aa933500-99b0-11eb-90ea-332943e110d1.png)



### **코드**

```c
int led = 4; // 4번 핀에 LED 꽂음.
int sw = 9; // 9번 핀에 스위치 꽂음.

void setup() {
  pinMode(led,OUTPUT);  // LED가 연결된 핀을 OUTPUT으로 설정함.
  pinMode(sw,OUTPUT);   // 스위치가 연결된 핀을 INPUT으로 설정함.
}

void loop() {
  if (digitalRead(sw) == HIGH) {  // 만약 스위치가 HIGH 상태면, 스위치가 눌러지면
    digitalWrite(led,HIGH); // LED가 연결된 핀을 HIGH 상태로 만들음. LED를 켬.
  }

  else {  // 만약 스위치가 HIGH 상태가 아니면, LOW 상태면, 스위치가 안 눌렸으면
    digitalWrite(led,LOW);  // LED가 연결된 핀을 LOW 상태로 만들음. LED를 끔.
  }
}
```

### **실행 모습**
![image](https://user-images.githubusercontent.com/78032658/114227058-71a69080-99af-11eb-9849-81596069bd94.png)
![image](https://user-images.githubusercontent.com/78032658/114227073-74a18100-99af-11eb-9935-960de6e5640a.png)

### **느낀 점**
* 스위치를 계속 누르고 있어야 하는 점이 좀 귀찮았다. 한 번 누르면 유지되게 만들어 보고 싶다.
