see: https://yang-song.net/blog/2021/score/

## Intro

* likelihood based models: model the pdf explicitly
* implicit generative models: model the pdf implicitly
* score-based models: model the gradient of the log of the pdf
## Score function, score based models and score matching

$$\{x_1, \ldots, x_N\}\sim p(x)$$

we can learn this density with

$$p_\theta(x) = \frac{\exp(-f_\theta(x))}{Z_\theta}$$

We can model the score

$$s_\theta(x) = -\nabla_x f_\theta(x) \approx \nabla_x \log p(x)$$

We can train score-based models by minimizing the Fisher divergence

$$\mathbb{E}_{p(x)}[\|\nabla_x \log p(x) - s_\theta(x)\|]^2_2$$

## Langevin dynamics
$x_0\sim\pi(x)$

$$x_{i+1} \leftarrow x_i + \epsilon \nabla_x \log p(x) + \sqrt{2}z_i$$
where $z_i \sim \mathcal{N}(0,I)$

### Naive score matching

estimating the score functions are inaccurate in low density regions. 

### Multiple noise perturbations

how to bypass the difficulty of accurate socre estimation in regions of low data density?


## SDE perspective

$$d x = f(x,t) dt + g(t) dw$$

