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





## 20220712

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



## 20220801

use math.isclose() to compare to float value, which is robust.

use 0b100100 to respesent a binary number and use bin() to present it.

