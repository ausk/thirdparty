# thirdparty

C++ 开发时依赖的三方库

主要包含：

* OpenCV 420
* OpenVino 2020R1
* pybind11
* 运行库(vcredist_x64, redist_intel64)

```bash
git clone https://github.com/ausk/thirdparty
git pull
git push
```

使用说明：

(1) 将 ai.props 放置在 xxx.sln 解决方案目录下，然后使用项目的属性管理器添加 ai.props.

添加后，xxx.vcxproj 工程文件中应该有类似的属性表导入声明。

```
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Release|x64'">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
    <Import Project="..\ai.props" />
  </ImportGroup>
```

然后，就可以项目中就可以引用 opencv, openvino 等库了。

(2) 运行时，需要将对应的 opencv/openvino 的 dll 文件所在文件夹路径添加到 PATH 中。

(3) 可能还需要安装运行库。



