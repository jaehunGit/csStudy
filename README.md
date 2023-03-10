# csStudy

# 컴공 이론을 위한 기체초력 다지기

## Bit
1bit => 전구 스위치 하나라고 생각 0 과 1 두가지의 경우만 있음  
2bit => 전구 스위치 2개 2의 2제곱 4가지의 경우의 수  
4bit => 2의 4제곱 16가지의 경우의 수  
4bit => 8 4 2 1 (2의 3제곱, 2의 2제곱, 2의 1제곱, 2의0제곱)  

## 외워야 할 단위 체계 #1
8개 비트를 하나로 묶어 1바이트(byte)라고 한다.  
1바이트는 영문자 한 글자가 저장될 수 있는 메모리 크기이며 관리의 최소단위이다.  
※비약적으로 Computer = cpu + ram 이라고 말해도 과언이 아니다.  
근데 이때 cpu가 됐는 ram이 됐는 memory 용량의 가장 작은 단위가 1바이트이다.  
※1바이트 단위로 관리를 한다. 누가? cpu 나 window os 나 mac ios 가 중요한 전산 자원을 관리 할 수도 있다. 관리 최소 단위가 1바이트이다.  
※한글은 한 글자를 저장하려면 2바이트가 필요하다.  

## 외워야 할 단위 체계 #2
4비트는 16가지, 8비트는 256가지, 16비트는 65,536가지(64KB)이다. 일단 이렇게 외우자.  
2의 10제곱은 1024이다.  
1byte가 10개 모이면 2의 10제곱은 1024 이때 1KB(킬로바이트)라고 단위가 바뀜.  

## 컴퓨터가 글자를 다루는 방법
  - 십진수 65.  
  - 컴퓨터에겐 영문 대문자 'A'.  
  - 16진수로는 0x41.  
컴퓨터에는 원래 글자가 없음 -> 해결 방법 -> 숫자를 글자랑 매핑하자 여기서 나온 약속들, 체계들을 코드체계 라고 부른다.  
ex) ABC -> 0x41(65), 0x42(66), 0x43(67)  
65 66 67이라는 숫자를 써놓고 이거를 화면에 이렇게 생긴 그림을 그려줌 65 => A 라는 모양으로 그려줌. => 이걸 랜더링한다. 라고 말함.  


  - ASCII(American Standard Code for Information Interchange)는 미국에서 사용하는 표준 코드체계이다.  
  - 숫자와 글자를 구별하지 않고 정보를 말 할 때는 바이너리(Binary)라고 한다.  
  
  
ex) 'A' => 16진수로는 65 => 0x로는 0x41 이렇게 되있는데  
1이라는 숫자 값이 있을때 0x01 인데 문자 '1'은 0x31 라고한다. => 숫자 1과 문자1을 구분해야 함.  

## 컴퓨터가 글자를 다루는 방법
메모장에  
Hello World!  
Hi.  
  
  
를 입력한다면  
바이너리로 바뀐다. 빈칸도 문자임 바이너리로는 20.  
엔터도 입력해서 개행 엔터키도 정보가 있음 enter => 0A 0D => 한묶음 \r \n 이라고 있음 프로그래밍하면 앎.  
요렇게 하면 맨마지막에 0A 0D 가 두번나옴 enter 을 두번 쳤다는 걸 알 수 있음.  
  
## 컴퓨터가 사진을 다루는 방법 #1
  - 모니터 화면 상 '점' 하나를 화소(Pixel)이라 한다.
  - 여러 점들을 모아 사진을 만들 수 있다.
  - 화소 하나를 표현하는데 8비트, 16비트, 24비트, 32비트 정보가 필요할 수 있다.
화소 하나를 표현하는데 RGB 각각 8비트 2의8제곱 총 256 0~255 단계가 있다.  
근데 여기에다가 24비트에 +8비트를 하면 32비트가 되는데 여기서 8비트는 색이 아니라 투명도를 얘기하는 거다.  
여기서 투명도를 결정하는 걸 알파채널이라고 말한다.  
알파채널을 합쳐서 RGBA 라고 말한다.  
얘가 32비트 트루컬러 라고 말한다.  

## 컴퓨터가 사진을 다루는 방법 #2
  - 빛의 3원색을 Red, Green, Blue 이다.  
    이 점에 착안해 RGB 컬러가 등장한다. 여기에 알파채널을 붙여서 RGBA라고 말한다.
  - 화소가 작을수록 사진이 매끄럽다. (고해상도)

### RGB 색상 표현과 픽셀
8bit -> 2의 8제곱 -> 256  
화소 -> 32bit -> 4byte  

=> 우리가 보통 화소를 합쳐서 사진을 만들때 보통 bitmap 이라고 말함.
=> 이렇게 하면 너무 용량이 커져 jpg 이라든지 등등을 쓴다.

## 컴퓨터가 사진을 다루는 방법 #3

만약 행이 0~12까지 있고 열이 0~12까지 있다면
  - 1, 1, 1 => 열이 1이고 행이 1인 곳에 한개를 칠해라
  - 1, 2, 2 => 열이 1이고 행이 2인 곳에 두개를 칠해라


=> 이런걸 영상의 압축이라고 한다. 압축의 원리 중 하나이다.  
=> 굉장히 적은 용량으로도 큰 사진의 데이터를 표현할 수 있다.  


# 넓고 얕은 컴퓨터 구조

## 디지털 회로와 덧셈(CPU 자작도 가능!)
어떻게 하면 CPU를 제작 할 수 있을까?  
=> 솔직히 말하면 우리가 제작 할 필요는 없다. 만들어져 있는 거 잘 쓰면 됨. 

input   |     Oust S
A | B | AND | OR | XOR | NOT
---|---|---|---|---|---
0 | 0 | 0 | 0 | 0 | 1
1 | 0 | 0 | 1 | 1 | 0
0 | 1 | 0 | 1 | 1
1 | 1 | 1 | 1 | 0

### 디지털 회로
AND => 둘다 참 일때 => 참  
OR => 둘중 하나라도 참이거나 둘다 참 일때 => 참  
XOR => 두개의 인풋이 서로 다를때 => 참 => 00 11 이든 같게 나오면 => false 를 반환 => 배타적 OR 라고 말함  
NOT => 0 이면 1로 1이면 0으로 뒤집음  

CPU 는 전자 계산기라고 말함.  
무엇을 계산할까? => 산수 계산. => A B 가 있으면 (+, -, x, /) 사칙 연산.  


칩셋은 인풋 A 인풋 B 그리고 결과 S 가 있다. => A가 B가 각각 1비트라고 말할 수 있음.

## 컴퓨터가 덧셈 하는 방법 #1
  - 2진수 1+1은 2진수 10(2) 이다.
  - A가 1, B가 1이면 XOR 연산결과 S는 0이다.
  - 동시에 A가 1, B가 1이면 AND 연산결과 C는 1이다. 이 1은 자리 올림(Carry)이다.
=> 반 가산기. => 이걸 가지고 1bit + 1bit 를 더하는 것.  
=> 반 가산기는 치명적 단점이 있음. => 더 할때 맨 처음꺼는 모르겠는데 이거 [8421] 이걸 넘어가면 자리 올림까지(3개) 더해주는 로직이 필요함.  
=> 이 로직을 가지고 있는 것이 전 가산기.  

더하기만 만들면 컴퓨터는 다 만들 수 있다.  
어떤 선생님이 수제 CPU를 만든 사람이 있다. => 빵판을 엄청 많이 붙이고 해서 만듦. => 엄청난 노력이 필요..  

## 컴퓨터가 뺄셈 하는 방법 #1
  - 6에 4를 더하면 10이다. 즉 4, 4는 6에 대한 10의 보수이다.
  - 13 - 6 은 7이다.
  - 13에 6에 대한 10의 보수 4를 더하고 10자리에서 1을 빼도 역시 7이다.
  => 보수 덧셈을 하면 자동으로 뺄셈이 된다. -> 즉, 덧셈으로 뺄셈을 할 수 있는 것. -> 더하기를 하는 전가산기로 뺄셈도 가능.  
  
## 컴퓨터가 뺄셈 하는 방법 #2
  - 2진수에서 0은 1로, 1은 0으로 뒤집으면 1의 보수가 된다.
  - 1의 보수에 1을 더하면 2의 보수이다.
  - 어떤 숫자에 2의 보수를 더하면 자동으로 2진수 뺄셈이 된다. **단, 자리올림은 버린다.**
=> 2진수로 뺄셈을 할때는 2의 보수를 쓴다. -> 2진수의 2의 보수 구하는 방법.  
=> 2의 보수 = 1의 보수 + 1 => 1의 보수는 인버터임 NOT 연산자를 사용하면된다 0 은 1로, 1은 0으로.  



**13 - 6 을 2진수로 봐보면..**  
13을 2진수로 표현하면 **1101**  
6을 2진수로 표현하면 **0110** 이것의 1의 보수를 구해보면 **1001** 여기다가 + 1 을 하면 => 1001 + 1 => **1010**  
1101 + 1010 => **10111** 이때 자리 올림이 발생 5자리번째 숫자는 4비트로 표현 못하므로 버림 => **0111** => 8 4 2 1 중에 4 2 1 을 더하면 **7**이 나옴!  

=> 덧셈을 했는데 이걸 응용해서 뺄셈도 했음 => 이제 곱셈, 나눗셈이 남음 => 사실 곱셈은 여러번 더하면 곱셈이다. 나눗셈은? 여러번 빼면 나눗셈이 자동으로 구현됨.  
**이렇게 사칙연산이 완성됨**
=> 지금까지 말한 것은 정수에 관한 것만 했음. => 실수는 너무 딥해져서 안함! 혹시 공부하고 싶다면  
=> **IEEE 754 표준을 찾아보면 됨 (부동 소수점 이런 것들이 나옴. 여기까지 하면 일의 수준 지금 수업의 목표랑은 달라서 안함.)**

## 컴퓨터가 곱셈 하는 방법
  - 4비트로 5를 표현하면 0101이다.
  - 4비트 0101을 왼쪽으로 한 칸씩 밀면(Shift) 1010이다.
  - 맨 오른쪽에 0이 채워진다. (Padding)
  - 4비트로 표현하는 2진수 1010은 10이다.
  - 왼쪽으로 한 칸 밀면 곱하기 2, 두칸 밀면 곱하기 4가 된다.

=> 자리 올림은 버림, 채우는 건 0으로 채움.  

## 컴퓨터가 나눗셈 하는 방법
  - 4비트로 6을 표현하면 0110이다.
  - 4비트 0110을 오른쪽으로 한 칸씩 밀면 0011이다.
  - 맨 왼쪽에 0이 채워진다.(Padding)
  - 4비트로 표현하는 2진수 0011은 3이다.


=> 한 가지 언급해야할 건 => 우리가 지금 당장 표현하는건 4비트 -> 2의 4제곱 -> 숫자 15까지 밖에 안됨.  
=> 더 큰수를 하면 8bit로 늘려버림 -> 만약 더 큰 수를 다룰거라면 -> 8bit를 더 붙이던지.. 아니면 32bit로 올리던지..!  
=> 어쨋든 기본적으로 나눗셈이라고 하는 것은 기본적으로 뺄셈이라고 생각하면 된다.  
=> 15 / 5를 하고 싶다면 -> 15 - 5 를 하고 10 - 5 => 5 - 5 => 0 => 총 몇번 뺐다? => 3번 뺐다. => 나누기는 크거나 같다면 뺄 수 있을 때 까지 빼는 것!  

**이게 어떤 문제가 잇냐면..**
  - 7을 0으로 나누면?
  - 7에서 0을 빼면 7이고 7은 0보다 크다.
  - 7에서 0을 계속 빼면 언제가는 0보다 작은 숫자를 만날 수 있는가?
  - 만날 수 없다면 뺄셈 연산은 언제 끝날까?

=> 결과는? 칩셋이 폭발해버림 유튜브에 영상이 있음  
=> 우리가 쓰는 pc cpu는 오류가 발생하면서 연산을 해주지 않음 그래서 cpu가 망가지거나 폭발하는 일은 벌어지지 않음  
=> 매커니즘이 없는 칩셋은 폭발 => 우리가 프로그래밍 공부를 하면서 7/0 같은 이상한 것은 바로 에러가 나버림 => 하지 않는 걸 추천!  

## 컴퓨터가 연산하는 과정
보통 컴퓨터라고 하면 cpu, ram 이라고 생각.  
cpu는 말 그대로 연산하는 장치.(비메모리)  
ram은 메모리 반도체(저장)  

보통 컴퓨터라고 하면 cpu, ram + ssd(hdd)
ram은 0 [] 1 []  ... 100 [] ... 4,294,967,293 [] 이렇게 있는데 0 1 ... 100 ... 4,294,967,293 은 일련번호라고 생각  
일련번호라는 것도 엑셀에서 c열의 3행 칸에 정보를 담을 수 있는데 => **메모리 하고 가장 비슷하다고 할 수 있는 것은 엑셀이라고 생각!**  






public static String DIODE_FORMATTER(ItemListVO list, String diode) {
		String text = "";

		String[] checkItemCatgArr = {"PERI_TR", "PERI_TR_HV", "PERI_TR_ASYM_LOD", "PERI_TR_HV_ASYM_LOD", "CORE_TR", "CELL_TR"}; // 추가 필요

		if (Arrays.asList(checkItemCatgArr).contains(list.getItemCatgNm())) {
			if (diode.equals("first")) {
				text = list.getVrfTmlGVal() != null && !list.getVrfTmlGVal().equals("#") ? list.getVrfTmlBVal() : "";
			} else if (diode.equals("second")) {
				text = list.getVrfTmlNgVal() != null && !list.getVrfTmlNgVal().equals("F") && !list.getVrfTmlNgVal().equals("#") ? list.getVrfTmlBVal() : list.getVrfTmlB2Val();
			}
		} else if (diode.equals("second")) {
			text = list.getVrfTmlB2Val();
		}

		return text;
	}
