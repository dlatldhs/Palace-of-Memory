# 타입
## 1. char
> ``` 1 byte의 정수를 저장하는 타입```
> ```
> int main()
> {
>   char ch = 250;
>   printf("%d\n", ch);
> }
> 결과값 : -6
## 결과값이 -6으로 나오는 이유
### 250을 비트로 바꾸면<br>![image](https://user-images.githubusercontent.com/80656700/183676417-24d0dc84-bb88-4a60-8357-0fc80d95f10e.png)<br>⭐위에 있는 그림 해석⭐<br> 1. MSB(Most Sinificant Bit)최상위 비트가 0인지 1인지 판단 => `MSB`가 0이면 음수 1이면 양수로 판단함<br>2. 양수면 바로 2진수를 10진수로 변환하여 구하면 됨<br>3. 음수면 2의 보수를 이용하여 절대값을 추출하여 구함(양수로 만들어주는거임)<br>4. 1의 보수를 만듬<br>![image](https://user-images.githubusercontent.com/80656700/183679369-65b6229f-3e33-48cb-b2bf-13413fb10383.png) <br>이렇게 만들어 진거에 1을 더함 <br>![image](https://user-images.githubusercontent.com/80656700/183679056-94fd8dc8-d65a-40ed-a7b0-4f53111336f5.png)<br>5. 최종값 6에 (-1)^s 를 곱함 이 s는 부호비트 즉 MSB를 의미함 1의 보수 말고 MSB가 1이였으니까 -1 * 6 을 하면 됨<br> 그래서 -6 이 나오는거임        
# 2. 비트 필드 구조체 비트 멤버의 정수 해석
> 아래 프로그램에서 예상되는 결과는 ?
> ```
> typedef struct
> {
>   char b1:2;
> } AAA;
> int main() {
>   AAA a;
>   a.b1 = 3;
>   printf("%d\n", a.b1 );
> }
결과값 : -1
> 일단 b1:2 는 char type 변수b1의 크기를 2bit로 지정하는거임
> 그리고 2bit안에 3을 넣으면
> ![image](https://user-images.githubusercontent.com/80656700/183885961-08d71dad-5cfb-4c48-9ad3-421081fae07d.png) 이렇게 됨
> 일반화 된 정수 타입의 해석 방법 3가지
> 1. 최상위 비트가(MSB) 1이면 무조건 음수(-)로 해석한다
> 2. 음수(-)일 경우 2의 보수와 절대값을 사용하여 추출한다.
> 3. 정수의 전체 비트 수와 상관없이 동일하게 적용된다. 