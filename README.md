@[TOC](jest 使用 jest-allure 测试报告)

关于 jest 配置不做过多概述，请看：[https://blog.csdn.net/qq_41906031/article/details/120836787](https://blog.csdn.net/qq_41906031/article/details/120836787)

# 配置 jest-allure

1. **安装 jest-allure**

```powershell
npm install --save-dev jest-allure
```

2. **更改 jest.config.json** 在文件中添加：

```javascript
setupFilesAfterEnv: ["jest-allure/dist/setup"],
reporters: ["default", "jest-allure"],
```

3. **运行测试：**

```powershell
npm run jest
```

运行测试默认会在项目根目录生成一个 <font color="red">allure-results</font>目录

4. **修改 jest-allure 路径**（可以忽略）

- 修改配置文件，添加前置条件

```javascript
setupFilesAfterEnv: ["jest-allure/dist/setup", , "<rootDir>/testSetup.js"],
```

- 在项目根目录添加 <font color="red">testSetup.js</font> 文件

```javascript
reporter.allure.setOptions({ targetDir: "reports/allure-results" });
```

# 配置运行环境

1. **安装 allure**
   allure 下载地址：[https://github.com/allure-framework/allure2/tags](https://github.com/allure-framework/allure2/tags)
   windows 环境下载 zip 文件并解压

2. **添加 allure 环境变量**
   示例：D:\Program Files\allure-2.19.0\bin
   ![在这里插入图片描述](https://img-blog.csdnimg.cn/6b64391eadd14ec6937dc2631d3b4f73.png)

# 查看测试报告

在项目根目录运行 allure

```powershell
allure serve
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/4f61188c4ad4420a92a9dc4e16359b3b.png)
注：如果运行失败，请检查是否安装 java 运行环境
成功运行后会使用默认浏览器打开一个窗口显示测试报告，如下图所示：

![在这里插入图片描述](https://img-blog.csdnimg.cn/885c391d0f724631a136bd90f4e0d700.png#pic_center)
