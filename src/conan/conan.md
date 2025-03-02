# conan
# 安裝conan
[Installer](https://kiloath.github.io/Installer/)
```
> $ps='install_conan_latest.ps1' # C++
> irm -Uri https://gitlab.com/api/v4/projects/58360840/repository/files/$ps/raw | iex
```
# 初始
```
conan -v
conan profile detect --force
conan profile show
```
# 新建
```
conan new cmake_exe -d name=rice01 -d version=1.0
```