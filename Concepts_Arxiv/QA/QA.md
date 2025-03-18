# 1. Gradient Vanishing

- ReLU Activation
- Batch Normalization
- Residual Connection

# 2. Pretrained weights follow Zero-mean normal distribution.

# 3. Why do we add a minus to an objective function to transform a maxmization problem into a minimization problem?

전통적으로 수학에서 최적화 문제는 최소화 문제로 다뤄진다.

최소화 문제로 다루는 이유는 수렴과 안정성 측면으로 볼 수 있다.

최소값을 찾는 것이 더 직관적이기도 하고, 안정적인 학습 과정으로 간주된다.

왜냐하면 최대화 문제로 다루게 되면 수렴이 아닌 발산할 것이기 때문에 최적화가 불안정하기 때문이다. 


# 4. Why do we take the logarithm to convert multiplication into addition?

Log를 취하면 곱셈을 덧셈으로 취급할 수 있기때문에 계산이 더 간단해지고 최적화가 용이해진다.

또한 Log는 단조함수이기 때문에, 로그를 취하기 전 그래프와 최대, 최소 관계가 그대로 유지된다.