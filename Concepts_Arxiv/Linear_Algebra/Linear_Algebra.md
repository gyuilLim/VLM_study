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

---

### Hadamard Product

Hadamard product란 같은 크기의 두 행렬 또는 텐서를 원소별로 곱하는 연산이다.

수식으로 표현하면 아래와 같다.

$$C = A \circ B$$

여기서 A와 B는 같은 크기의 행렬이고,

$C_{ij} = A_{ij} \cdot B_{ij}$ 형태로 각 원소끼리 곱한다.

Element-wise product(원소별 곱) 이라고도 하며 행렬곱과는 다르다.

파이썬 `Numpy`에서 사용 예시
```python3
import numpy as np
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])
C = A * B  # Hadamard product
```

---

### Eigenvalue & Eigenvector(고유벡터 & 고유값)

Eigenvector(아이젠 벡터)란 행렬 변환에서 방향이 변하지 않는 벡터를 말한다. 단지 크기만 스칼라배될 뿐, 방향은 그대로 유지되는 것이다.

아이젠 벡터의 정의는 아래와 같다.

$$A \bold v = \lambda \bold v$$

여기서,
- $\bold v$ : Eigenvector
- $\lambda$ : Eigenvalue

즉 행렬 $A$가 벡터 $\bold v$에 곱해졌을 때, 그 결과가 $\bold v$와 같은 방향이며, 크기만 $\lambda$배 되는것이다.

Eigenvector와 Eigenvalue를 구하려면 다음 방정식을 풀면 된다.

$$(A-\lambda I)\bold v = 0$$

벡터 $\bold v \ne 0$ 을 만족해야 하므로 해가 존재하려면 $(A-\lambda I)$가 가역 행렬이 아니어야 한다. 

이유는 만약 $(A-\lambda I)$의 역행렬이 존재한다면 $(A-\lambda I)\bold v = 0$ 양변에 $(A-\lambda I)^{-1}$ 을 곱할 수 있고, 따라서

$$\bold v = (A-\lambda I)^{-1} \cdot 0 = 0$$

이 된다. 그러므로 역행렬이 존재하지 않아야 한다. 따라서 행렬식(det)이 0이 되어야 하므로

$$\textrm{det}(A-\lambda I) = 0$$

를 만족하는 Eigenvalue $\lambda$를 구할 수 있다.