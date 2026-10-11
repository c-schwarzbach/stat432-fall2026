---
id: w07-cs148-lda-qda-bias-variance
title: "When should we prefer LDA over QDA?"
author: "Cameron Schwarzbach (cs148)"
---

In the Week 7 simulation, LDA performed better than QDA when the class covariances were similar, while QDA performed better as the covariance structures became more different. Explain this pattern using the bias-variance trade-off. Why does sharing one covariance matrix reduce variance but potentially introduce bias? How would your model choice change if the training sample were much smaller or much larger?