# Daily note

## 20220609

### note about the installation of ftx

```
pip install ftx
```



- pip install ftx, there will be problem about ciso8601. I have to use visual studio build tool.
- When I use the buidl tool, https://stackoverflow.com/questions/44951456/pip-error-microsoft-visual-c-14-0-is-required provides a good tutorial.

### \__init\__.py

When I want to use the functions in another py file, if the current directory is not the env directory, there will be problem. We should create a \__init\__.py under the directory to make the whole directory a module.



## 20220620

### pizza cutting

$$
f(n) = f(n - 1) + n \\
f(0) = 1,
f(1) = 2,
f(2) = 4,
$$

imagine that: 

When we have one more cut, it must follow the next rules:

- cross all the existing line
- not cross any intersection



### cake cutting







## 20220621

**ord()** and **chr()**

ord() will return the ASCII number, and chr() is the pair function of ord()



**global and nonlocal**

nonlocal will make the variable able to be refered and accessed from outer (only one level)

global will make the variable able to refered from a global scope



if the outer scope is already global, nonlocal is invalid to be used.



### brige survivors



## 20220622

**dp**

when we want to use dp to solve the problem, start from one-dimension dp, the simplest and directest definition about the problem. 

abstract the practical problem into a sequence problem

the recursion formulation of dp usually involves more than 1 preview state,

- take more than 1 to choose decision,
- sum
- accumulate sum



## 20220624

wildcards





## 20220627

### Euler-Mascheroni constant

$$
S_n = \sum _{k=1}^n {1 \over k}
$$

![img](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2020%2F1217%2Fec6a9f2bp00qlgb0v001lc000mt00kgc.png&thumbnail=660x2147483647&quality=80&type=jpg)
$$
\int_{1}^{n+1} {1 \over x} dx - S_n \approx \gamma
$$
![img](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2020%2F1217%2Fde2e6ecdp00qlgb0v002gc000la00k4c.png&thumbnail=660x2147483647&quality=80&type=jpg)
$$
\gamma \approx 0.57721
$$
**the next step:**

use trapeziums instead of rectangles, we can prove the lower bound to 1/2, then prove it is monotonically decreasing. https://www.cantorsparadise.com/the-euler-mascheroni-constant-4bd34203aa01



## 20220628

### HM-GM-AM-QM inequality

$$
HM \leq GM \leq AM \leq QM \\
HM(harmonic \ mean) = {n \over \sum_1^n {1 \over x_i}} \\
GM(geometric \ mean) =  \sqrt[n]{\prod_1^n x_i} \\
AM(arithmetic \ mean) = {1 \over n} \sum_1^n x_i \\
QM(quadratic \ mean) = \sqrt{{1 \over n} \sum_1^n x_i^2}
$$



### draw NN by graphviz

http://magjac.com/graphviz-visual-editor/ is a good online editor for NN, such as:

```
digraph G {

        rankdir=LR
        splines=line

        node [fixedsize=true, label="", ];

        subgraph cluster_0 {
        color=white;
        node [style=solid, shape=circle];
        x1 [label=<T>]
        x2 [label=<&sigma;<SUB>0</SUB>>]
        
        x3 [label=<&xi;>]  # the html style letter
        x4 [label=<&rho;>]
        x5 [label=<K<SUB>\1</SUB>>] # the subsript
        {node [style=solid,shape=point]; # the point will be used as ellipsis for infinite and large size NN
          p1; p2; p3;}
          x6 [label=<K<SUB>n</SUB>>];
          label = "layer 1 (Input layer)";
         }

    subgraph cluster_1 {
        color=white;
        {node [style=solid, shape=circle];
        a12 a22 a32;} # every point name should be different
        {node [style=solid,shape=point];
        p10 p20 p30;}
        {node [style=solid, shape=circle];
            a62 a72 a82
        }; # the square bracket define the scope.
        label = "layer 2 (hidden layer)";
    }

    subgraph cluster_2 {
        color=white;
        node [style=solid, shape=circle];
        O [label=<&sigma;(K<SUB>1</SUB>)>];
        O1 [label=<&sigma;(K<SUB>2</SUB>)>];
        
        {node [style=solid,shape=point];
  p31; p32; p33;}
  
        O2 [label=<&sigma;(K<SUB>n-1</SUB>)>];
        O3 [label=<&sigma;(K<SUB>n</SUB>)>];
        label="layer 3 (output layer)";
    }

        x1 -> a12;
        x1 -> a22;
        x1 -> a32;
        x1 -> a62;
        x1 -> a72;
        x1 -> a82;
        
        x2 -> a12;
        x2 -> a22;
        x2 -> a32;
        x2 -> a62;
        x2 -> a72;
        x2 -> a82;
        
        x3 -> a12;
        x3 -> a22;
        x3 -> a32;
        x3 -> a62;
        x3 -> a72;
        x3 -> a82;
        
        x4 -> a12;
        x4 -> a22;
        x4 -> a32;
        x4 -> a62;
        x4 -> a72;
        x4 -> a82;
        
        x5 -> a12;
        x5 -> a22;
        x5 -> a32;
        x5 -> a62;
        x5 -> a72;
        x5 -> a82;

        x6 -> a12;
        x6 -> a22;
        x6 -> a32;
        x6 -> a62;
        x6 -> a72;
        x6 -> a82;

        a12 -> O;
        a22 -> O;
        a32 -> O;
        a62 -> O;
   }
```

http://alexlenail.me/NN-SVG/LeNet.html


## 20220701

### infinite coin flip



## 20220703

### if you want an array to be the key of dict

list is unhashable, but tuple can do that



### pandas isin() and contains()





### RE

pattern matching

- regex.
  - . for any character. \d for number. 
  - \* for more than zero times.
  - \+ for more than zero or zero.
  - greedy match is default. ? after \+ or \* is non-greedy
  - () is select
  - combine with format or replace is more powerful
- re.compile(regex).findall() or search()





### create file using shell

touch, if the file does not exist, it will create a new file

vi

echo. write line by line



### cat write a file

cat > path << EOF



EOF



top can make me see the backage jobs

jobs.



### sh -x can line by line run the shell script and print it.

after you create a new xxx.sh

chmod a+x xx.sh to make it executed

 



## 20220706

### Gaussian integration



### Jocab

input $\mathbf{X} \in \mathbb{R}_n$, output $\mathbf{Y} = [f_1(\mathbf{X}) \dots f_n(\mathbf{X})] \in \mathbb{R}_n$ 

$y_1 = f_1(x_1, x_2, \dots x_n)$

$y_2 = f_2(x_1, x_2, \dots x_n)$

$y_3 = f_3(x_1, x_2, \dots x_n)$

$y_n = f_n(x_1, x_2, \dots x_n)$
$$
|\mathbf{J} |= [\frac{\partial Y}{\partial X}] = \begin{vmatrix}
\frac{\partial f_1}{\partial x_1} & \dots  & \frac{\partial f_1}{\partial x_n} \\ 
\dots & \dots  & \dots \\ 
\frac{\partial f_n}{\partial x_1} & \dots  & \frac{\partial f_n}{\partial x_n} \\ 
\end{vmatrix}
$$
Jocab determint is to transfer the n - dimension space into m - dimension space, absolute value



For example, when we do double integral,  

$\int \int f_{xy}(x, y)dxdy = \int \int f_{xy}(x(u,v), y(u,v))|J|dudv$

Polar coordinate transformation

$dxdy = |J|drd\theta$



## 20220707

### coupon collector problem

given n coupons, how many coupons do you expect you need to draw with replacement before having drawn each coupon at least once?

Let $T$ be the number of draws.
$$
E(T) = {n \over n} + {n \over n-1} \dots + {n \over 1} = n \sum_{i=1}^{n}{1 \over i}
$$




## 20220713

### state price

state price means the price of the state

we assume a security, when a state happen, the payoff will be 1, or it will be zero. the state price is the value of the security at time 0.
$$
V_0 = \zeta (w)P(w) = {1 * \tilde{P}(w) \over (1 + r)^N} = \tilde{\mathbb{E}} {V_N \over (1+r)^N}
$$
the state price density means ${V_0 \over P(w)} = \zeta (w)$,  $V_0$ per unit real probability.

## the meaning the PDF

$\rho = M /V$, mass per unit volume, any definition like {0} per unit {1}, can be named as a kind of density,

 so $f(x) = \lim_{\Delta V \rightarrow 0}({M(\Delta V) \over \Delta V})$

the sum of the probability is 1, so $f(x) = \lim_{\Delta x \rightarrow 0}({P(\Delta x) \over \Delta x})$



## circle  sword,  Josephus problem

treat it as a circle.

when there are only $2^n$ people left, the first one will be the last survivor.

given the number of people is X. we can get Y which is the highest power of 2 that is less than or equal to X.

because Y must be more than or equal to X / 2, 

there will be Y-X people die before we get   $2^n$ people left, and we jump one at a time. so the first one of the  $2^n$ people left wil be $2 * (Y-X) + 1$.





### 20220712

### shell \$N

\$1 the first parameter you give to the command

\$n the nth parameter you give to the command

\$0 the name of this script itself

\$# the number of parameter you give

\$\$ the excute job id of  the script

\$? the state after the last command was excuted, 0 if it is normal, else 1.

\$@ or \$* all the parameter you give, “\$*” will make it as a single string



## undetected_chromedriver

it will not trigger anti-bot services, as a alternative for chrome driver in selenium

easy way:

```python
import undetected_chromedriver as uc
driver = uc.Chrome()
driver.get('https://distilnetworks.com')
opts = uc.ChromeOptions()
```

monkeypatch way

```python
import undetected_chromedriver as uc
uc.install()

from selenium.webdriver import Chrome
driver = Chrome()
driver.get('https://distilnetworks.com')
```



<<<<<<< Updated upstream

## 20220722

### convolutional kernel

It is feature filter, only detect specific line features

so we can use different kernels at the same time to generate a series of output for every dimension of th picture. 

Compared with pooling,  convolution means to detect feature, pools is going to reduce dimension.






### 202220724

### tacks of the bike

<img src="https://i0.wp.com/graduatetrader.com/wp-content/uploads/2020/07/Tracks-From-A-Two-Wheeled-Bike.png?ssl=1" alt="img" style="zoom:50%;" />



solve the problem from the properties of bike:

1. The tangent of every point on th track of back wheel should point to some point of the front wheel.
2. following what we said in the property 1,  the line segment generated by the tangent intersection will be be a fixed length.





### Transition Porbability Matrix

The matrix can be transfered to a recurrent decision tree.

It repesent the state transiton in a markov process.



## 20220725

### stop time

$$
r= f(\omega, t)
$$

both r and t are time. The stop time will return a time which is not relative with the future.

It is correspond with the state and time.

For example in binary pricing tree, it can represent the optimal executed time based on current state and current time, it returns sometime in the past.





### martingale and markov process

martingale:
$$
X_n = E_{n}(X_{n+1})
$$
markov process:
$$
E_n(f(X_{n+1)}) = g(X_{n})
$$
for any f(x), there will be a g(x) that make the (11) hold.

martingale may not be a markov process, because we need to prove it for any f(x).

markov process is also not always martingale, because only when f(x) = x, g(x) = x, it holds.



## 20220726

### CV for data science:

- be short and precise. only keep the relevant experience, do not inculde everything even if they are big achievement. customized

- grab the attention \. include your most attractive achievement. It also should be customized based on the JD. 

- skill, categorize them. soft skill need proof. do not be crowded. give them rank. customized

- Project experience. It should include the interns. include academic projects. customized

- Project decsription. 

  - STAR:
    - Situation
    - Task
    - Action
    - Result
  - highlight the key words. list the methods

  

- only relative courses. customize

- achievement is very important.

- Include your favorite books. not you love reading books

- domain is important, highlight it 



## 20220727

when you extract information for dict, use get() is better that use brackets. If the key does not exist in the dict, get() will return None instead of raising an error.



### Layers in CNN

#### FC

map the features(after convolution and pooling) with feature, the weight will be trained.
$$
y = Wx
$$
linearly transform space x into space y.





>>>>>>> Stashed changes





## 20220801

use math.isclose() to compare to float value, which is robust.

use 0b100100 to respesent a binary number and use bin() to present it.



## 20220802

### Poisson theorem

![image-20220802121448149](C:\Users\Simmons\AppData\Roaming\Typora\typora-user-images\image-20220802121448149.png)



### CNN

#### 图像数据在全连接神经网络中的难点：

1. 图像需要处理的数据维度高，计算成本很高，效率很低
2. 图像在数字化的过程中很难保留原有的特征，导致图像识别的准确率低。



#### CNN的优势：

 稀疏连接

卷积神经的特点就是每一层神经元只响应前一层的**局部范围**内的神经元。由卷积操作产生。缓解了图像产生的数据高维问题。



权值共享

在全连接中，计算每层的输出时，权重矩阵中的元素只作用于某一个输入元素一次；

而在卷积神经网络中，卷积核中的每一个元素将作用于每一个局部输入的特定位置上。根据参数共享的思想，我们只需要学习一组参数集合，而不需要针对每一个位置的每一个参数来进行优化学习，从而大大降低了模型需要训练的参数个数，降低了计算成本。



平移不变性

池化操作和权值共享使得网络对数如数的局部变换具有一定的平移不变性和缩放不变性。例如图片中是否有一只狗，无论这只狗再什么位置，这只狗所占像素的大小，都应该是别墅粗来



CNN模拟了人体视觉原理

1980年Fukushima最初提出的神经认知机可以被视为CNN的原型工程  \cite{fukushima1980self}。他们受到huble和wiesel对猫脑视觉皮层研究的启发，即视觉皮层存在复杂构造细胞层次 \cite{hubel1962receptive}。Lecun等人基于Fukushima的研究训练了LeNet-5模型，也就是经典CNN结构 \cite{lecun1998gradient}。

```

@article{lecun1998gradient,
  title={Gradient-based learning applied to document recognition},
  author={LeCun, Yann and Bottou, L{\'e}on and Bengio, Yoshua and Haffner, Patrick},
  journal={Proceedings of the IEEE},
  volume={86},
  number={11},
  pages={2278--2324},
  year={1998},
  publisher={Ieee}
}

@article{hubel1962receptive,
  title={Receptive fields, binocular interaction and functional architecture in the cat's visual cortex},
  author={Hubel, David H and Wiesel, Torsten N},
  journal={The Journal of physiology},
  volume={160},
  number={1},
  pages={106},
  year={1962},
  publisher={Wiley-Blackwell}
}


@article{fukushima1980self,
  title={A self-organizing neural network model for a mechanism of pattern recognition unaffected by shift in position},
  author={Fukushima, Kunihiko},
  journal={Biol. Cybern.},
  volume={36},
  pages={193--202},
  year={1980}
}

```



#### 权重初始化

 权重初始化方法应该考虑的因素：

- 对权重w的大小和正负缺乏先验，所以应初始化在0附近，但不能为全0或常数，所以要有一定的随机性，即数学期望E(w)=0E(w)=0；
- 因为梯度消失和梯度爆炸，权重不易过大或过小，所以要对权重的方差Var(w)有所控制；
- 不同激活层输出的方差相同





 高斯分布初始化

从均值为0，方差为1的[高斯分布中采样，作为初始权值。

torch.nn.init.normal_(tensor, mean=0, std=1)

kaiming高斯初始化

Kaiming He提出来的卷积层权值初始化方法 \cite{he2015delving}，目的是**使得每一卷积层的输出的方差都为1**，具体数学推导可以参考论文[1]. 权值的初始化方法如下：
$$
W_l \text  \\  N (0,\sqrt{\frac{2}{(1 + a^2) \times n_l}})
$$
torch.nn.init.kaiming_normal_(tensor, a=0, mode='fan_in', nonlinearity='leaky_relu') 

a为Relu函数的负半轴斜率，mode表示是让前向传播还是反向传播的输出的方差为1，nonlinearity可以选择是relu还是leaky_relu.



xavier高斯初始化

Glorot正态分布初始化方法 \cite{glorot2010understanding}，也称作Xavier正态分布初始化，参数由0均值，标准差为sqrt(2 / (fan_in + fan_out))的正态分布产生，其中fan_in和fan_out是分别权值张量的输入和输出元素数目. 这种初始化同样是为了保证输入输出的方差不变，但是原论文中([2])是基于线性函数推导的，同时在tanh激活函数上有很好的效果，但不适用于ReLU激活函数.
$$
\text{std} = \text{gain} \times \sqrt{\frac{2}{\text{fan_in} + \text{fan_out}}}
$$
torch.nn.init.xavier_normal_(tensor, gain=1) 



```
@inproceedings{he2015delving,
  title={Delving deep into rectifiers: Surpassing human-level performance on imagenet classification},
  author={He, Kaiming and Zhang, Xiangyu and Ren, Shaoqing and Sun, Jian},
  booktitle={Proceedings of the IEEE international conference on computer vision},
  pages={1026--1034},
  year={2015}
}

@inproceedings{glorot2010understanding,
  title={Understanding the difficulty of training deep feedforward neural networks},
  author={Glorot, Xavier and Bengio, Yoshua},
  booktitle={Proceedings of the thirteenth international conference on artificial intelligence and statistics},
  pages={249--256},
  year={2010},
  organization={JMLR Workshop and Conference Proceedings}
}

```



### adam算法的优势

1. 计算高效，方便实现，内存使用也很少。
2. 更新步长和梯度大小无关，只和alpha、beta_1、beta_2有关系。并且由它们决定步长的理论上限。基本上只需极少量的调参
3. 对目标函数没有平稳要求，即loss function可以随着时间变化， 适用于非稳态（non-stationary）目标
4. 能较好的处理噪音样本，并且天然具有退火效果
5. 能较好处理稀疏梯度，即梯度在很多step处都是0的情况
6. 适合解决含大规模数据和参数的优化问题



### 图像数据的数据增强方法

#### 像素级变换

1. 模糊 高斯模糊、平均模糊、中值模糊、GlassBluer(毛玻璃效果)、MotionBlur、ElasticTransformation(扭曲平滑)
2. 均衡化 CLAHE、AHE、HE
3. 颜色空间变换 ChannelDropout(随机选择通道像素失活，和Dropout层类似) CoarseDropout区域随机失活(擦除/高亮) ChannelShuffle(颜色空间随机交换)
4. 噪声 高斯噪声 椒盐噪声 camera sensor noise FrequencyNoiseAlpha：在频域中用随机指数对噪声映射进行加权，再转换到空间域。在不同图像中，随着指数值逐渐增大，依次出现平滑的大斑点、多云模式、重复出现的小斑块
5. 颜色干扰 对比度、饱和度、亮度
6. 增强 FancyPCA(检测图像中的所有边缘，将它们标记为黑白图像，再将结果与原始图像叠加) EdgeDetect、浮雕、锐化、Superpixel、黑白转置、雾化、雨化、阴影、雪、太阳耀斑

#### 空间级变换

crop Resize 旋转 Flip 仿射变换 弹性变换ElasticTransform Pad(常数、边界、反射) 网格畸变GridDistortion 光学畸变OpticalDistortion



#### mix

Hongyi Zhang等人（2018）提出了mixup来增强图像数据，基于邻域风险最小化原则，使用线性插值的方法扩展数据。\cite{zhang2017mixup}



```
@article{zhang2017mixup,
  title={mixup: Beyond empirical risk minimization},
  author={Zhang, Hongyi and Cisse, Moustapha and Dauphin, Yann N and Lopez-Paz, David},
  journal={arXiv preprint arXiv:1710.09412},
  year={2017}
}
```

#### mosaic

参考了CutMix数据增强方式。

步骤如下：

\1. 从数据集中每次随机读取四张图片

\2. 分别对四张图片进行翻转（对原始图片进行左右的翻转）、缩放（对原始图片进行大小的缩放）、色域变化（对原始图片的明亮度、饱和度、色调进行改变）等操作

\3. 拼接。操作完成之后然后再将原始图片按照 第一张图片摆放在左上，第二张图片摆放在左下，第三张图片摆放在右下，第四张图片摆放在右上四个方向位置摆好

4、进行图片的组合和框的组合 完成四张图片的摆放之后，我们利用矩阵的方式将四张图片它固定的区域截取下来，然后将它们拼接起来，拼接成一 张新的图片，新的图片上含有框框等一系列的内容





## 20220811

### dll load failed while importing win32api

1. conda install pywin32
2. copied the two files from `[installation directory of Anaconda]\Lib\site-packages\pywin32_system32` to `C:\Windows\System32`,
3. pip install --upgrade pywin32==225, it works



###  **WARNING: Ignoring invalid distribution -ip (path to packages)**

go to 'site-packages' directory, delete folders whose name start with ~ (tilde)





## 20220820

### joblib

