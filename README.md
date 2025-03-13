# 零基础脚本撸毛保姆教程

## 📖 教程目录

1. 编程环境安装（Windows/Mac）
2. 代码编辑器推荐
3. 获取脚本的两种方式
4. 安装依赖（自动/手动）
5. 运行脚本的通用方法
6. 常见问题与解决
7. 安全提示 & 学习资源



## 1️⃣ python环境安装

### 🔧 **Windows系统**

1. **下载Python** 访问[Python官网](https://www.python.org/downloads/)，点击“Download Python 3.x.x” ![img](https://www.python.org/static/img/python-logo.png)

2. **安装时必选项** 安装界面务必勾选 **✅ Add Python to PATH**，然后点“Install Now” （否则后续无法在命令行使用Python）

3. **验证安装** 按 `Win + R` 输入 `cmd` 打开命令行，输入：

   ```
   python --version
   ```

   显示版本号（如 `Python 3.12.6`）即成功！

### 🍎 **Mac系统**

1. **自带Python** Mac已预装Python 2，目前脚本大多都是基于3来开发的，不通用，所以需升级到Python 3：

   - 打开终端（Terminal），输入：

     ```
     brew install python
     ```

   - 若无Homebrew，先安装：

     ```
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```

2. **验证安装** 终端输入：

   ```
   python3 --version
   ```

## 2️⃣ 代码编辑器推荐

- **VSCode**（适合所有语言）： 下载地址：[https://code.visualstudio.com](https://code.visualstudio.com/) 安装后建议插件：Python、Prettier（代码格式化）
- **PyCharm（仅Python）**：社区版免费，适合深度开发。

## 3️⃣ 获取脚本的两种方式

### 方式一：下载ZIP压缩包（适合小白）

1. 进入GitHub脚本页面（如 `https://github.com/用户名/仓库名`）
2. 点击绿色按钮 **Code → Download ZIP**
3. 解压到桌面或指定文件夹

### 方式二：克隆仓库（需Git）

1. 安装Git：[Git官网](https://git-scm.com/)

2. 终端输入：

   ```
   git clone https://github.com/用户名/仓库名.git
   ```

## 4️⃣ 安装依赖（以Python脚本为例）

### 自动安装（推荐）

1. 打开终端，进入脚本所在目录：

   ```
   cd ~/Desktop/仓库名  # 路径替换为你的实际位置
   ```

2. 执行命令安装所有依赖：

   ```
   pip install -r requirements.txt
   或
   pip3 install -r requirements.txt
   ```

### 手动安装（无依赖清单时）

- 根据脚本提示的报错安装缺失库，例如：

  ```
  pip install requests selenium
  或
  pip3 install requests selenium
  ```

## 5️⃣ 运行脚本的通用方法

### Python脚本

1. 终端进入脚本目录

   ```
   cd ~/Desktop/仓库名  # 路径替换为你的实际位置
   ```

2. 输入命令：

   ```
   python main.py  # 或 python3 main.py
   ## main一般为程序的主入口，每个程序都需要从main函数开始运行
   ```

## 6️⃣ 常见问题与解决

1. **报错“命令未找到”**

   - 检查环境变量是否配置（安装时勾选PATH）
   - 重启终端或电脑

2. **依赖安装失败**

   - 尝试更换镜像源：

     ```
     pip install requests -i https://pypi.tuna.tsinghua.edu.cn/simple
     ```

3. **脚本权限不足**

   - Mac/Linux系统需添加执行权限：

     ```
     chmod +x script.sh
     ```



## 1️⃣ Node.js环境安装

### 🔧 **Windows系统**

1. **下载安装包** 访问[Node.js官网](https://nodejs.org/)，下载 **LTS版本**（长期支持版） ![img](https://nodejs.org/static/images/logo.svg)

2. **一键安装** 双击安装包，全部保持默认选项（**务必勾选 `Add to PATH`**） ✅ 安装完成后重启电脑

3. **验证安装** 按 `Win + R` 输入 `cmd` 打开命令行，输入：

   ```
   node -v  # 显示版本号如 v18.17.0
   npm -v   # 显示版本号如 9.6.7
   ```

### 🍎 **Mac系统**

1. **推荐用Homebrew安装** 打开终端（Terminal），输入：

   ```
   brew install node
   ```

2. **验证安装**

   ```
   node -v
   npm -v
   ```

## 2️⃣ 代码编辑器推荐

- VSCode

  安装以下插件提升效率：

  - `ESLint`（代码规范检查）
  - `Prettier`（自动格式化代码）
  - `npm Intellisense`（自动补全依赖名）

## 3️⃣ 获取Node.js脚本的两种方式

### 方式一：直接下载ZIP压缩包

1. 进入GitHub脚本仓库页面
2. 点击 `Code → Download ZIP`
3. 解压到桌面（路径不要有中文！）

### 方式二：克隆仓库（需Git）

```
git clone https://github.com/用户名/仓库名.git
```

## 4️⃣ 安装依赖（核心步骤）

### 方法一：npm自动安装

1. 终端进入脚本目录：

   ```
   cd ~/Desktop/文件夹名  # 替换为你的实际路径
   ```

2. 执行安装命令：

   ```
   npm install  # 自动读取package.json中的依赖
   ```

### 方法二：手动安装单个依赖

如果脚本报错缺少某个包（如 `axios`），手动安装：

```
npm install axios
```

## 5️⃣ 运行Node.js脚本的三种方法

### 基础运行

```
node index.js  # 运行主文件
```

### 使用package.json脚本

如果项目中有 `package.json`，查看 `scripts` 字段：

```
{
  "scripts": {
    "start": "node index.js",
    "test": "echo \"Error: no test specified\""
  }
}
```

运行指定命令：

```
npm run start  # 等效于 node index.js
```

### 实时热更新（开发推荐）

安装 `nodemon` 工具：

```
npm install -g nodemon  # 全局安装
nodemon index.js       # 文件修改后自动重启
```

## 6️⃣ 常见问题与解决

### 1. **`npm install` 安装慢或失败**

- 切换淘宝镜像源：

  ```
  npm config set registry https://registry.npmmirror.com
  ```

- 或使用cnpm

  ```
  npm install -g cnpm --registry=https://registry.npmmirror.com
  cnpm install
  ```

### 2. **权限不足（Mac/Linux报错）**

- 在命令前加

  ```
  sudo
  ```

  并输入密码：

  ```
  sudo npm install -g pm2
  ```

### 3. **缺少模块（Cannot find module）**

- 检查是否已安装依赖：

  ```
  npm list  # 查看已安装的包
  ```

- 删除

  ```
  node_modules
  ```

  后重装：

  ```
  rm -rf node_modules  # 删除旧依赖
  npm install          # 重新安装
  ```
