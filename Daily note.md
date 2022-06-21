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



### cake cutting







## 20220621

**ord()** and **chr()**

ord() will return the ASCII number, and chr() is the pair function of ord()



**global and nonlocal**

nonlocal will make the variable able to be refered and accessed from outer (only one level)

global will make the variable able to refered from a global scope



if the outer scope is already global, nonlocal is invalid to be used.



### brige survivors



