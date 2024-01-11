https://baijiahao.baidu.com/s?id=1758494828106881785&wfr=spider&for=pc&searchword=ubuntu安装rpm

#  Ubuntu 上安装 RPM 包 RPM/DEB包转换

## 安装 alien

1、添加 `universe` 仓库

```
sudo add-apt-repository universe
```

2、更新仓库

```
sudo apt update
```

3、安装 Alien

```
sudo apt install alien
```

## 使用 alien 来安装 RPM

你可以使用 `alien` 来将 `.rpm` 转换成 `.deb`

```
sudo alien package.rpm
```

这会生成一个同名的 `package.deb` 文件，然后就可以用 `dpkg` 来安装了

```
sudo dpkg -i package.deb
```

不过你也可以直接用 `alien` 来安装 `.rpm`

```
sudo alien -i package.rpm
```