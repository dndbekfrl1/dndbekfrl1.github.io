
---
layout: post
title: '빠른 입출력'
tags:
  - java
hero: assets/img/pom.jpeg
overlay: red
---

입출력 속도가 Buffered이 월등하다는 것은 알고 있음. 
그런데 손에 익숙한건 Scanner이라서 활용을 못하고 있어서 
익힐겸 정리를 함 

<!–-break-–>

입출력 스트림으로부터 미리 버퍼에 데이터를 갖다 놓기 때문에 보다 효율적인 입출력이 가능합니다. [참고 - https://coding-factory.tistory.com/251]

``` java
BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
String s = bf=readLine();
int i= Integer.parseInt(bf.readLine());
```

예제를 통해 사용방법을 보겠음(백준 10989번 - 수 정렬하기3)
``` java
 public static void main(String[] args) throws Exception {
	    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
	    BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
	        
	    int N = Integer.parseInt(br.readLine());
	    int[] arr = new int[10001];
	    for (int i = 0; i < N; i++) {
	        arr[Integer.parseInt(br.readLine())] ++;
	    }
	    for (int i = 1; i < 10001; i++) {
			while (0 < arr[i]--) {
				bw.write(Integer.toString(i) + "\n");
			}
		}
	    br.close();
	    bw.close();
	}
```

추가로 여러개의 입력을 받는 경우를 정리함
```java
//1 2 3 4 5를 입력받는다 가정했을때,
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
String [] input = br.readline().split(" ");

//Integer로 바꿔줘야함 
int [] arr = new int [input.length-1];
for(int i=0;i<input.length-1;i++){
	arr[i]=Integer.parseInt(input[i]);
}

```
마지막으로 StringTokenizer은 split()과 유사한 기능이라고 함

-끝 