# quick start

### 设置go的代理

```bash
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,direct
```

### 安装gop
```bash
go get -u github.com/goplus/gop/cmd/gop
```

### 获取spx的tutorial

```bash
git clone https://github.com/goplus/spx
```


### 运行其中一个程序

```bash
cd spx/tutorial/01-Weather
gop run -v .
```
