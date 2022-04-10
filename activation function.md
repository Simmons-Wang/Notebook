# activation function

Without  activation function, DNN is just Percepton with linear simulation. Activation function add non-linear ability into neural network.

## Sigmoid

$$
\sigma(z) = {1 \over 1+e^{-z}}
$$

$$
\sigma'(z) = {e^{-z} \over (1+e^{-z})^2} = (1-\sigma(z)) \cdot \sigma(z)
$$

![img](https://pic2.zhimg.com/80/v2-595feb9c4660fdee432dcd30b8256735_1440w.jpg)

pros :

- smooth
- easy for derivation

cons:

- relatively heavy computation consumption, because of the exponentiation and division, both in activation and backward propagation.
- From the graph above we can see that the the maximum value of the derivation is 0.25. $0.25^{10} \approx 0.00000095$, which is vanishing gradient problem.
- The output of Sigmoid is not zero-mean, which will cause the later cell get the signal with non-zero means. It will change the data distribution gradually.

## tanh

Hyperbolic Tangent, saturation activation function which is the same as sigmoid and transformation of sigmoid.
$$
tanh(x) = {e^x - e^{-x} \over e^x + e^{-x}} = {2 \over 1+ e^{-2x}} + 1
$$


![img](https://pic1.zhimg.com/80/v2-ac5875cf045fbdf213b8b0ba67f10b30_1440w.jpg)

- the output range is (-1, 1), partly solve the non-zero problem of sigmoid.
- still high computation comsumption
- the derivation of tanh is (0, 1), partly solve the vanishing gradient problem, but not totally.

## ReLU

Rectified Linear Unit. 
$$
relu=max(0, x)

$$
![img](https://pic2.zhimg.com/80/v2-da3babf705f525effbaab3bbbed7df51_1440w.jpg)

- the effective derivation is 1, which solve the vanishing gradient problem.
- when x>1, exploding gradient may happens. to solve the problem:
  - control the weights.
  - gradient clipping. for example, $ReLU(x)=min(6, max(0,x))$

- when x < 0, it remove noise, change the dense matrix into a sparse matrix dynamically during the training. But abandon all the x < 0, make it hard to learn some features. we should not set the lr too large [https://www.zhihu.com/question/67151971]. 
- lower computation comsuption
- fast convergence and better model

## leaky ReLU, PReLU（Parametric Relu）, RReLU（Random ReLU）

![img](https://pic3.zhimg.com/80/v2-96c799e1b9f0b80de1ca17e503e4c11a_1440w.jpg)



To prevent dead model, we define $y=\alpha x$ when $x<0$ instead of $y =0$

- **Leaky ReLU**. $\alpha = 0.01$, $\alpha$ is a constant, which is better than Relu but not stable.
- PRelu. $\alpha$ is a learned parameter.
- RReLU. During training, $\alpha$ is random chosen, but fixed during test.

## application

- Sigmoid and tanh is suitable for Pr prediction, such as gate in LSTM
- Relu is suitable for DNN

