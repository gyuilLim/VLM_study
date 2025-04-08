# Maximum Likelihood Estimation(최대 가능도 추정, MLE)

다양한 분포에 대하여 정규 분포로 적합시키는 방법을 **최대 가능도 추정**이라고 한다.

$N$개의 관측 데이터$\{x^{(1)}, x^{(2)}, \dots, x^{(N)},\}$이 있을 때, 이 샘플 데이터들의 정규 분포의 매개변수는 아래와 같다.

- $\hat \mu$ : 샘플의 평균
    - $\hat \mu = \frac{1}{N}\sum^N_{n=1}x^{(N)}$

- $\hat \sigma$ : 샘플의 표준편차
    - $\hat \sigma = \sqrt{\frac{1}{N}\sum^N_{n=1}(x^{(N)}-\hat \mu)^2}
    $

이 때 이 샘플 분포를 발생시켰을 가능성이 가장 높은 모집단의 평균과 표준편차를 추정하는 것이 **최대 가능도 추정**이다.

## 가능도 최대화

매개변수 $\theta$를 갖는 확률 분포가 있다고 하자. $\theta$에는 $\mu$와 $\sigma$가 포함된다.

이 때 $\theta$를 갖는 확률 밀도 함수는 $p(x; \theta)$로 표현할 수 있다.

모집합으로부터 샘플링된 $N$개의 샘플 $\mathcal D=\{x^{(1)}, x^{(2)}, \cdots, x^{(N)} \}$가 있다고 하자.

각 $x$가 독립적으로 생성되었다고 할 때, 샘플 $\mathcal D$가 발생할 확률을 아래와 같이 나타낼 수 있다.

$$p(\mathcal D; \theta) = p(x^{(1)};\theta)p(x^{(2)};\theta) \cdots p(x^{(N)};\theta) = \Pi^N_{n=1}p(x^{(n)};\theta)$$

위 수식에서 $p(\mathcal D; \theta)$를 **가능도** 또는 **가능도 함수**라 한다.

## 최대 가능도 추정

어떤 함수에서의 최대값은 기울기가 0인 지점, 즉 미분했을 때의 값이 0인 지점에서 발생한다.

가능도 함수에서 미분값을 계산한 후 0이되는 지점을 찾는 식으로 매개변수를 추정할 수 있다. 이를 "**해석적 해(Analytic Solution)를 구한다**"라고한다.

해석적 해를 구하기위해 가능도 함수에 로그를 취한다. 로그를 취하는 이유는 2가지가있다.

1. 로그는 곱셈을 덧셈으로 취급할 수 있게해주어 식을 간편하게 변환할 수 있다.
2. 로그는 단조함수이기 때문에, 함수의 최대, 최소 관계가 그대로 유지된다.

따라서 최대값을 추정하는 최대 가능도 추정 문제에서 로그를 취하면 계산 편의의 이점을 취할 수 있는 것이다.

이를 **로그 가능도**라고 한다.

$$\log p(\mathcal D; \theta) = \sum^N_{n=1} \log p(x^{(n)};\theta) $$

주어진 샘플 $\mathcal D$에 대해 정규 분포로 모델링한다고 하면,

$\mathcal N(x;\mu, \sigma) = \frac{1}{\sqrt{2\pi\sigma^2}}\exp(-\frac{(x-\mu)^2}{2\sigma^2})$

$N$개의 관측 데이터로 구성된 샘플 $\mathcal{D}=\{ x^{(1)}, x^{(2)}, \cdots, x^{(N)} \}$ 에 대한 `가능도 함수 (확률 밀도 함수)`

- $\mathcal{N}(\mathcal{D}; \mu, \sigma) = p(\mathcal{D}; \mu, \sigma) = p(\mathcal{D}; \theta) = L(\theta)$

- $p(\mathcal{D}; \mu, \sigma)= \prod_{n=1}^N \mathcal{N}(x^{(n)}; \mu, \sigma) = \prod_{n=1}^N\frac{1}{\sqrt{2\pi\sigma^2}}\exp \left( -\frac{(x^{(n)} - \mu)^2}{2\sigma^2} \right)$

$N$개의 관측 데이터로 구성된 샘플 $\mathcal{D}=\{ x^{(1)}, x^{(2)}, \cdots, x^{(N)} \}$ 에 대한 `로그 가능도 함수`

- $\log ~ p(\mathcal{D}; \mu, \sigma) = \log ~ L(\theta)$

    $ = \log \prod_{n=1}^N\frac{1}{\sqrt{2\pi\sigma^2}}\exp \left( -\frac{(x^{(n)} - \mu)^2}{2\sigma^2} \right)$

    $ = \log \prod_{n=1}^N\frac{1}{\sqrt{2\pi\sigma^2}} + \log \prod_{n=1}^{N} \exp \left( -\frac{(x^{(n)} - \mu)^2}{2\sigma^2} \right)$

    $ = \log \left( \frac{1}{\sqrt{2\pi\sigma^2}} \right)^N + \sum_{n=1}^{N} \left( -\frac{(x^{(n)} - \mu)^2}{2\sigma^2} \right)$

    $ = - \frac{N}{2} \log ~ {2\pi\sigma^2} - \frac{1}{2\sigma^2} \sum_{n=1}^{N}  (x^{(n)} - \mu)^2$

위 식을 $\sigma, \mu$에 대해 각각 편미분하여 0이 되는 지점을 계산하면,

$$\mu = \frac{1}{N} \sum^N_{n=1} x^{(n)}$$
$$\sigma = \sqrt{\frac{1}{N}\sum^N_{n=1}(x^{(n)}-\hat \mu)^2}$$

이다. 즉 결론은 샘플 데이터로부터 구해진 평균과 표준 편차로 모집단의 분포를 정규분포 형태로 추정할 수 있다는 것이다.

# Gaussian Mxiture Model(GMM)

GMM이란, 데이터가 여러개의 가우시안 분포(Gaussian Distribution)의 혼합으로 구성되어 있다고 가정하는 **확률 모델**이다.

데이터가 하나의 정규분포를 따르지 않고 여러개의 정규분포가 섞여있는 형태. 아래와 같은 확률 밀도 함수로 표현된다.

$$p(x) = \sum^K_{k=1} \phi_k \cdot \mathcal N(x;\mu_k, \mathbf \Sigma_k)$$

$K$ : 정규분포의 개수 (클러스터 개수)

$\phi_k$ : k번째 정규분포의 가중치 (각 0~1 범위, 합은 1을 만족해야함)

$\mathcal N(x;\mu_k, \mathbf \Sigma_k)$ : 평균이 $\mu_k$이고 분산이 $\mathbf \Sigma_k$을 따르는 정규분포

$x$ : 관측 데이터

매개변수를 포함하여 수식을 다시쓰면 아래와 같다.

$$p(x;\Phi, \mu, \mathbf \Sigma) = \sum^K_{k=1} \phi_k \mathcal \cdot N(\mathbf x; \mu_k, \mathbf \Sigma_k)$$

## Marginalization(주변화)

Joint Probability(결합 확률)
- $p(x,y)$
- $x$와 $y$가 동시에 일어날 확률

Marginal Probability(주변 확률)
- $p(x), p(y)$
- $x$와 $y$가 별개로 일어날 확률

결합 확률에서 특정 확률 변수를 제거함으로써 주변 확률을 구할 수 있다. 이를 `주변화`라고 한다.

예를 들어 확률 변수 $y$에 대한 주변화를 통해 주변 확률 $p(x)$를 구한다고 하면 아래와 같이 나타낼 수 있다.

- 이산 변수인 경우 : $p(x) = \sum_y p(x,y)$
- 연속 변수인 경우 : $p(x) = \int_y p(x,y)dy$

곱셈 정리에 의해 결합 확률 $p(x,y) = p(x|y)p(y)$.

## GMM의 매개변수 추정의 어려움

단일 정규분포에서는 최대 우도 추정법으로 매개변수 $\mu$와 $\sigma$를 구할 수 있었다.

하지만 여러개의 정규분포가 혼합되어있는 GMM은 최대 우도 추정법으로, 그러니까 해석적으로 매개변수를 구하기 어렵다.

$$p(x;\Phi, \mu, \mathbf \Sigma) = \sum^K_{k=1} \phi_k \mathcal \cdot N(\mathbf x; \mu_k, \mathbf \Sigma_k)$$

GMM은 위와 같이 표현할 수 있는데, 여기서 관측 데이터를 $\mathcal D$, 추정해야하는 매개변수 집합을 $\theta$ 라고 할 때 GMM의 Likelihood $p(\mathcal D; \theta)$ 는 아래와 같이 나타낼 수 있다.

$$p(\mathcal D; \theta) = p(x^{(1)};\theta)p(x^{(2)};\theta) \cdots p(x^{(N)};\theta) \\ = \Pi^N_{n=1} p(x^{(n)};\theta)$$

계산의 편의를 위해 로그를 취해 Log-likelihood로 재정의하면

$$\log p(\mathcal D;\theta) = \log \Pi^N_{n=1} p(x^{(n)};\theta) \\ = \sum^N_{n=1} \log (\sum^K_{k=1} \phi_k \mathcal N(x^{(n)}; \mu_k, \Sigma_k))$$

위 식에서 Log-likelihood 함수가 로그-합(log-sum) 형태로 정의되는 것을 확인할 수 있다.

따라서 GMM의 매개변수 추정에서는 해석적으로 정답을 찾기 어려운 것이다.

## EM Algorithm (Expectation-Maximization)

