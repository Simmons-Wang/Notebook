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