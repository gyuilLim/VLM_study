# Probability & Statistics

### Normalization constant(정규화 상수)

$f(x)$가 확률 밀도 함수라면 $\int_{-\infty}^{\infty} f(x) , dx = 1$ 을 만족해야 한다.

하지만 $f(x)$가 1로 정규화되지 않은 어떤 함수라면 정규화 상수($Z$)를 도입하여

$f_{normalized}(x) = \frac{f(x)}{Z}$ 와 같이  전체 적분을 1로 만들어주는 것이다.

$Z = \int f(x)dx$

따라서 $\int f_{normalized}(x)dx = \frac{1}{Z} \int f(x)dx = \frac{Z}{Z} = 1$

이 되어 적분값이 1을 만족하는 함수로 변환할 수 있는 것이다.

---
### Likelihood(우도)

관찰된 데이터가 특정 확률 모델(모수)에 의해 생성될 가능성을 나타내는 척도

$L(\theta; x) = P(x|\theta)$

$L(\theta; x)$ : $\theta$라는 파라미터 집합에서 관찰된 데이터($x$)가 나타날 우도

$p(x|\theta)$ : 관찰 데이터 $x$가 주어졌을 때, 모수 $\theta$에 따른 조건부 확률

### 확률과 우도의 차이

$P(x|\theta)$

확률 : $\theta$가 고정, $x$가 변수. 특정 모델 하에서 데이터가 발생할 확률

우도 : $x$가 고정, $\theta$가 변수. 관찰된 데이터 $x$를 기준으로 특정 파라미터 $\theta$가 얼마나 적합한지 나타내는 척도

### Maximum Likelihood Estimation(최대 우도 추정)

$\hat \theta = argmax_\theta L(\theta; x)$

- 관찰된 데이터 $x$를 가장 잘 설명하는 \theta를 찾는 것

### Log-Likelihood(로그 우도)

$l(\theta; x) = \log L(\theta; x)$

- 계산의 편의를 위해 로그우도 사용


### Posterior Probability(사후 확률)

$P(\theta | D)= \frac{P(D|\theta)\cdot P(\theta)}{P(D)}$

- 데이터 $D$가 주어졌을 때 파라미터 집합 $\theta$가 참일 확률

- 우도와 사전확률을 결합하여 추정

- $P(D)는 정규화 상수의 역할을 할 수 있다.

---

### Bernoulli Distribution(베르누이 분포)

이진 확률 분포의 일종으로, 두가지 가능한 결과 중 하나가 발생할 확률을 모델링함

두 가지 경우밖에 없기때문에 이산 확률 분포이므로, PMF(Probability Mass Function, 확률 질량 함수)로 정의할 수 있다.

$P(X=x) = p^x(1-p)^{1-x}, \quad x \in {0, 1}$

위 식이 의미하는 것은 $x$가 1인 경우의 확률은 $p$, 0인 경우의 확률은 $1-p$라는 것이다.

베르누이 분포의 기대값은 $x=1$일 때 이므로

$\mathbb E[X] = 0 \cdot (1-p) + 1 \cdot p = p$ 이고

분산은 다음과 같이 계산된다.

$Var(x) = \mathbb E[X^2] - (\mathbb E[X])^2 = p - p^2 = p(1-p)$

---

### Laplace Distribution(라플라스 분포)

$$f(x) = \frac{1}{2b} \exp [\frac{-|x-\mu|}{b}]$$

- 라플라스 분포는 위와 같은 확률 밀도 함수로 표현된다.

- 가우시안 분포와 유사한 모양의 확률 밀도 함수이다.

- 범위는 $-\infty < f(x) < \infty$ 으로 모든 실수 범위이다.

- 평균 : $\mu$, 분산 : $2b^2$, 표준편차 : $\sqrt2 b$, 이 때 $b$는 스케일 상수라고도 함 

- 라플라스 분포는 확률 밀도 함수기 때문에 적분했을 때 1이 된다. 절대값을 포함하기 때문에, 구간을 나누어서 적분해야한다.

&nbsp;


  
- $x \ge 0$ 의 경우

$$\int^\infty_0 \frac{1}{2b}\exp (\frac{x}{b})dx = \frac{1}{2b}\int^\infty_0\exp(-\frac{x}{b})dx = \frac{1}{2b}[-b \exp (-\frac{x}{b})]^\infty_0 = \frac{1}{2}$$

- $x < 0$ 의 경우


$$\int^0_{-\infty} \frac{1}{2b}\exp (\frac{x}{b})dx = \frac{1}{2b}\int^0_{-\infty}\exp(-\frac{x}{b})dx = \frac{1}{2b}[b \exp (-\frac{x}{b})]^0_{-\infty} = \frac{1}{2}$$

- 두 구간에 대한 적분을 합치면 합이 1이 된다.

---

### Kullback-Leibelr Divergence(쿨백-라이블러 발산)

두 확률 분포 $P(x)$와 $Q(x)$ 간의 차이를 측정하는 비대칭적 척도이다.

분포간의 "정보 손실"을 나타낸다.

$$D_{KL}(P||Q) = \sum_x P(x)\log \frac{P(x)}{Q(x)}$$

- $P(x)$ : 실제 데이터 분포
- $Q(x)$ : 모델이 추정한 분포
- $\log\frac{P(x)}{Q(x)}$ : $Q(x)$로 $P(x)$를 설명하기 위한 "비효율성"

$P(x) = Q(x)$ 일 때, $D_{KL}(P||Q)=0$ 으로 최소이다.

두 분포 $P(x)$와 $Q(x)$의 차이가 클수록 $\log \frac{P(x)}{Q(x)}$ 가 커진다.

또한 항상 $D_{KL}(P||Q) \ge 0$ 이다. $Q(x)$가 $P(x)$를 설명하는데 "추가 정보"가 필요하기 때문이다.

따라서 KL Divergence를 모델의 예측 분포와 정답 레이블 분포의 차이를 최소화하는 데에 사용한 것이 Cross Entropy Loss이다.

---

### Cross Entropy Loss

$$D_{KL}(P||Q) = \sum_x P(x)\log\frac{P(x)}{Q(x)}$$

이 식을 풀어쓰면

$$= \sum P(x)\log P(x) - \sum P(x)\log Q(x)$$

로 나타낼 수 있는데, 여기서 $P(x)\log P(x)$는 $P(x)$의 엔트로피이고, $P(x)\log Q(x)$는 $Q(x)$에 대한 $P(x)$의 Cross Entropy이다.

엔트로피로 바꾸어서 위 식을 다시 쓰면,

$$D_{KL}(P||Q) = H(P,Q) - H(P)$$

이다.

$H(P)$는 $P(x)$의 엔트로피인데, $P(x)$가 이미 고정된 분포이므로 상수이기 때문에 $H(P, Q)$를 최소화하는 것이 $D_{KL}(P||Q)$ 를 감소시키는 것이다.
