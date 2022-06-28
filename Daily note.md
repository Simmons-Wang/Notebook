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



