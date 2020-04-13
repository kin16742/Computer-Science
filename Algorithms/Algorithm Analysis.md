# Algorithm Analysis

#### Algorithm?

알고리즘이란 어떠한 input과 output으로 정의되는 문제를 해결하기 위한 해결 방법의 순서를 의미

#### Running Time

수행 시간은 input 크기에 비례한다. 평균 수행 시간은 계산하기 힘들기 때문에, 최악 수행 시간에 초점을 우선적으로 둔다.

#### Algorithm Analysis

##### 조건

- HW/SW 환경이 동일해야만 하다. 
- 모든 input을 고려

##### Pseudoode

알고리즘을 표현하는 방식으로, 말보다 구조적이며 실제 프로그램보다는 단순하게 작성된다.

프로그램 디자인 이슈는 작성하지 않고 알고리즘만을 작성한다.

수행되는 기본 연산을 식별할 수 있으며 이를 통해 걸리는 시간을 측정한다. ( input size를 통해 )

```
ex)
int Search(int[] E, int n, int K)
	int ans, index;
	ans = -1;
	for(index = 0; index < n; index++)
		if(K == E[index])
			ans = index;
			break;
	return ans;
```

##### Worst Case Complexity

1. Dn을 고려 중인 문제에 대한 크기 n의 입력 집합으로 하고, I를 Dn의 요소로 한다.
2. t(I)를 입력 I에서 알고리즘에 의해 수행되는 기본 연산의 수로 한다.
3. W(n) = max{t(I) | x ∈ Dn}을(를) 기준으로 함수를 정의한다.
4. W(n)는 크기 n의 입력에 대해 알고리즘이 수행하는 최대 기본 연산 수이다.

##### Average Complexity

1. Pr(I)를 입력 I가 발생할 확률로 설정한다.

2. 그러면 알고리즘의 평균 기본 연산 수는 다음과 같이 정의된다.

   A(n) = Σ Pr(I) t(I).

3. 알고리즘을 분석하여 t(I)를 결정한다.

4. 그러나 Pr(I)는 분석적으로 계산할 수 없다.

**Average-Behavior Analysis**

A(n) = Pr(s)As(n) + Pr(f)Af(n)

- Pr(s) : 성공 case 발생 확률
- Pr(f) : 실패 case 발생 확률
- As(n) : 성공 case의 평균 기본 연산 수
- Af(n) : 실패 case의 평균 기본 연산 수

##### Optimality (최적성)

각각의 문제들은 문제 복잡도를 가진다. 

문제 복잡도 : 문제를 해결하기 위해  필요한 최소한의 기본 연산 수

어떤 알고리즘의 Worst Case가 optimal하다면 그 알고리즘은 최적의 알고리즘이다. 

#### 점근 분석

 input size를 사용해 최악의 경우의 기본 연산 횟수를 계산한 뒤, Big-Oh 표기법으로 표현한다.

```
ex 1) f(n) = n^2 + 2n + 1
	  f(n) = O(n^2)
ex 2) f(n) = 3n
	  f(n) = O(n)
```

##### 복잡도 표기법

**Big-Oh**

f(n)가 점근적으로 g(n)보다 작거나 같을 때

**Big-Omega**

f(n)가 점근적으로 g(n)보다 크거나 같을 때

**Big-Theta**

f(n)가 점근적으로 g(n)와 같을 때