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

