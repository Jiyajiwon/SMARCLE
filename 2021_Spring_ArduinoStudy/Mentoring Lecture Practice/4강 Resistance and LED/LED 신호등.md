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

<hr/>

## **느낀 점**

* 회로를 설계할 때 줄이 최대한 꼬이지 않게 해야 혼란을 줄일 수 있을 것 같다. 그리고 이는 2차원 그래픽으로 회로도를 (먼저) 작성해보면 도움이 될 것 같다.
* 이번에 작성한 회로도는 선이 크로스자로 꼬여있어서 보기에 좋지 않다. (실제로 보면 잘 인지되지 않지만 평면 회로도로 보면 알 수 있다.)
* 부품을 늘릴수록 보드 공간 활용도 잘 해야할 것 같다. 몇 개 안 꽂았는데도 보드가 굉장히 좁다고 느껴졌다. 보기 좋게 설계하되 빈 공간은 최소화해야겠다.
* 다른 부원 활동한 것을 보니까 저항을 연결하지 않아 LED가 터지는 경우가 있었다. 주의해야겠다.
