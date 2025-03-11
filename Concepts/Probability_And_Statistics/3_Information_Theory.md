# Kullback-Leibelr Divergence(쿨백-라이블러 발산)

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

# Cross Entropy Loss(크로스 엔트로피 손실)

$$D_{KL}(P||Q) = \sum_x P(x)\log\frac{P(x)}{Q(x)}$$

이 식을 풀어쓰면

$$= \sum P(x)\log P(x) - \sum P(x)\log Q(x)$$

로 나타낼 수 있는데, 여기서 $P(x)\log P(x)$는 $P(x)$의 엔트로피이고, $P(x)\log Q(x)$는 $Q(x)$에 대한 $P(x)$의 Cross Entropy이다.

엔트로피로 바꾸어서 위 식을 다시 쓰면,

$$D_{KL}(P||Q) = H(P,Q) - H(P)$$

이다.

$H(P)$는 $P(x)$의 엔트로피인데, $P(x)$가 이미 고정된 분포이므로 상수이기 때문에 $H(P, Q)$를 최소화하는 것이 $D_{KL}(P||Q)$ 를 감소시키는 것이다.
