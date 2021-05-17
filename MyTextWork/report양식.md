# 학습 날짜  

* 2021-04-23(금)  



# 학습시간

* 10:00 ~ 18:00(서초 클러스터)



# 학습 범위 및 주제 

* ft_printf 함수 작성 & 알고리즘 공부



# 학습 목표

* ft_printf 개요와 작성



# 상세학습내용

<br/><br/>
# 60. 합이 같은 부분집합(DFS : 아마존 인터뷰)


* N개의 원소로 구성된 자연수 집합이 주어지면, 이 집합을 두 개의 부분집합으로 나누었을 때 
두 부분집합의 원소의 합이 서로 같은 경우가 존재하면 “YES"를 출력하고, 그렇지 않으면 
”NO"를 출력하는 프로그램을 작성하세요.
예를 들어 {1, 3, 5, 6, 7, 10}이 입력되면 {1, 3, 5, 7} = {6, 10} 으로 두 부분집합의 합이 
16으로 같은 경우가 존재하는 것을 알 수 있다.

<br/>

#### ▣ 입력설명

* 첫 번째 줄에 자연수 N(1<=N<=10)이 주어집니다.
두 번째 줄에 집합의 원소 N개가 주어진다. 각 원소는 중복되지 않는다.



#### ▣ 출력설명

* 첫 번째 줄에 “YES" 또는 ”NO"를 출력한다.


#### ▣ 입력예제 1
6
1 3 5 6 7 10


#### ▣ 출력예제 1
YES

<br/>
<br/>


## 내가 짠 코드
*

<br/>

```c++


```


<br><br> 

## 풀이
*  

<br/>

```c++
#include <stdio.h>
#include <vector>
#include <algorithm>
#include <stack>
using namespace std;


int arr[11];
int ch[11];
int n, total = 0;	//Level
bool flag = false;	//부분집합의 합과 total - sum이 같을 경우 flag를 true로 바꿔줌.
void DFS(int L, int sum) //이진트리 재귀 함수 
{
	if (sum > (total / 2))	return ;
	if (flag) return ; //YES 경우가 존재하면 재귀를 끝내버린다. 
	int i;
	if (L == n+1)
	{
		if (sum == (total - sum))
		{
			flag = true;
		}
		return ;
	}
	else
	{
		DFS(L + 1, sum + arr[L]); //이해가 생각보다 어렵다. 
		//부분집합의 원소를 더하는 경우의 수 
		DFS(L + 1, sum); // 더하지 않는 경우의 수 
	}
}

int main()
{
	freopen("input.txt", "rt", stdin);
	int i;
	scanf("%d", &n);
	for (i = 1; i <= n; i++)
	{
		scanf("%d", &arr[i]);
		total += arr[i];
	}
	DFS(1, 0); //이진트리 재귀 함수
	if (flag)
		printf("YES");
	else printf("NO");
}

//36 삽입정렬 
//43, 44 이분검색 응용 
//51 다이나믹 
//56 재귀
//58 이진트리 깊이우선탐색 
```



# 학습 내용에 대한 개인적인 총평

* 알고리즘 이진트리가 생각보다 개념이 어려웠다. 재귀쪽을 이해를 잘 해놔야할 것 같다.



# 다음 학습 계획 

* 알고리즘 테스트 & printf 마무리하기
