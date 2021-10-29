[[_TOC_]]

## Julia和Python需求

* 实现`.jl`和`.py`文件的逐行或逐段运行
* Interactive plots

## 配置方法

`Vscode`安装扩展`Julia`和`Python`，即可实现如下效果：

### Julia

* `.jl`文件逐行运行

![单行执行](.\pic\单行执行.png)

* `.jl`文件逐段运行

![整段执行](.\pic\整段执行.png)

* Julia绘制Interactive plots

![绘制Interactive plots](.\pic\interactive_plot.png)

### Python

* `.py`文件逐行运行

  ![逐行运行](.\pic\python_单行执行.png)

* `.py`文件逐段运行

![逐段运行](.\pic\python_整段执行.png)

* 绘制Interactive plots

![绘制Interactive plots](.\pic\python_interactive_plot.png)

![绘制Interactive plots](.\pic\python_interactive_plot_2.png)



## 示例代码

```Julia
using Plots, LaTeXStrings

x = 1:10
y = rand(10, 2)
# 不同的backend支持保存不同的图片格式. 比如gr支持保存为png, plotly支持保存为html等
# 详见https://docs.juliaplots.org/latest/output/#savefig-/-format
# Credit to 赵晴岳
gr()
fig = plot(x, y, title = "Two Lines", label = ["Line 1" "Line 2"], lw = 3)
xlabel!(L"\sqrt{\frac{a}{b}}")
ylabel!("My y label")

savefig("julia_plot.png")
```



```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2, 100)

plt.plot(x, x, label='linear')  # Plot some data on the (implicit) axes.
plt.plot(x, x**2, label='quadratic')  # etc.
plt.plot(x, x**3, label='cubic')
plt.xlabel(r'$\alpha$')
plt.ylabel('y label')
plt.title("Simple Plot")
plt.legend()
plt.savefig("python_plot.png")
```



## Vscode remote ssh

首先安装扩展`Remote - SSH`，然后如下图所示，点击`Add New`，输入连接命令，确认后Vscode会自动在config文件中写入连接信息。点击`Connect to Host in New Window`即可连接。

![](.\pic\remote-ssh.png)

![](.\pic\connect.png)
