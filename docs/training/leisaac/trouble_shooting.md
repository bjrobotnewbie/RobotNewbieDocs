# 故障排除

## VSCode 调试器无法工作

> 相关 issue：[IsaacLab/issues/3305](https://github.com/isaac-sim/IsaacLab/issues/3305)

当您使用 VSCode Python 调试器启动程序时，可能会遇到以下错误：

```shell
OSError: libstdc++.so.6: version `GLIBCXX_3.4.30' not found
```

请尝试在您的 conda 环境中安装相应的依赖项：
```shell
conda install -c conda-forge gcc=12 -y
```
