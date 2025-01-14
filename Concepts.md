# Linear Argebra

### Bilinear form(쌍선형 형식)

두 벡터에 대한 관계를 선형적으로 표현.

Bilinear form($B$)은 다음을 만족한다.

$B(a\mathbf u+b\mathbf v,\mathbf w)=aB(\mathbf u,\mathbf w)+bB(\mathbf v,\mathbf w)$ : 첫 번째 인자에 대해 선형

$B(\mathbf u,a\mathbf v+b\mathbf w)=aB(\mathbf u,\mathbf v)+bB(\mathbf u,\mathbf w)$ : 두 번째 인자에 대해 선형

여기서 $a, b \in \mathbb R$ or $\mathbb C$, $\mathbf u, \mathbf v, \mathbf m \in \mathrm V$(벡터)

Bilinear form은 행렬 표현을 통해 일반적으로 다음과 같이 표현할 수 있다.

$B(\mathbf u, \mathbf v) = \mathbf u^T A \mathbf v$

- $A$는 행렬(매개변수)
- $A$가 단위 행렬(identity matrix)인 경우 내적이 된다.
- $A$에 따라 벡터 간의 관계를 조정할 수 있다.




# Probability & Statistics

### Normalization constant(정규화 상수)

$f(x)$가 확률 밀도 함수라면 $\int_{-\infty}^{\infty} f(x) , dx = 1$ 을 만족해야 한다.

하지만 $f(x)$가 1로 정규화되지 않은 어떤 함수라면 정규화 상수($Z$)를 도입하여

$f_{normalized}(x) = \frac{f(x)}{Z}$ 와 같이  전체 적분을 1로 만들어주는 것이다.

$Z = \int f(x)dx$

따라서 $\int f_{normalized}(x)dx = \frac{1}{Z} \int f(x)dx = \frac{Z}{Z} = 1$

이 되어 적분값이 1을 만족하는 함수로 변환할 수 있는 것이다.

---