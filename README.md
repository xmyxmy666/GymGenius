# 智能健身应用程序说明书

## 项目简介
该项目是一个智能健身应用程序，利用Flask和Streamlit构建。它包含用户管理、健身计划、锻炼会话和锻炼动作的功能，并通过集成的机器学习模型提供动作监控和评估。

![系统](images/1.png)

## 项目主要功能
1. **用户注册和登录**：用户可以注册账户并登录。
2. **健身计划管理**：用户可以创建和管理健身计划。
3. **锻炼会话记录**：用户可以记录他们的锻炼会话。
4. **锻炼动作管理**：用户可以管理具体的锻炼动作。
5. **动作监控与评估**：通过摄像头实时监控用户的锻炼动作，并提供评估反馈。
6. **数据分析与可视化**：分析用户的健身数据，并进行可视化展示。

![动作监控](images/2.png)

## 运行环境和依赖项
项目依赖项管理在`requirements.txt`文件中。主要依赖包括：
- Flask
- SQLAlchemy
- PyMySQL
- Streamlit
- MediaPipe
- OpenCV
- Pyttsx3
- Aiohttp

## 安装和运行步骤

1. **克隆或下载项目代码**
   ```bash
   git clone <项目仓库地址>
   cd <项目目录>
创建虚拟环境并激活

bash
复制代码
python -m venv venv
source venv/bin/activate  # Linux/MacOS
venv\Scripts\activate  # Windows

安装依赖项

bash
复制代码
pip install -r requirements.txt
设置环境变量
创建一个.env文件，并添加以下内容：

plaintext
复制代码
SECRET_KEY=your_secret_key
SQLALCHEMY_DATABASE_URI=mysql+pymysql://root:201575@localhost/smart_fitness
创建数据库表

bash
复制代码
python create_tables.py
运行后端服务器

bash
复制代码
python run_backend.py
运行前端应用

bash
复制代码
streamlit run app.py




以下是完整的README文档内容，用Markdown格式编写，可直接放入你的README.md文件中：

markdown
复制代码
# 智能健身应用程序说明书

## 项目简介
该项目是一个智能健身应用程序，利用Flask和Streamlit构建。它包含用户管理、健身计划、锻炼会话和锻炼动作的功能，并通过集成的机器学习模型提供动作监控和评估。

![系统架构](images/architecture.png)

## 项目主要功能
1. **用户注册和登录**：用户可以注册账户并登录。
2. **健身计划管理**：用户可以创建和管理健身计划。
3. **锻炼会话记录**：用户可以记录他们的锻炼会话。
4. **锻炼动作管理**：用户可以管理具体的锻炼动作。
5. **动作监控与评估**：通过摄像头实时监控用户的锻炼动作，并提供评估反馈。
6. **数据分析与可视化**：分析用户的健身数据，并进行可视化展示。

## 运行环境和依赖项
项目依赖项管理在`requirements.txt`文件中。主要依赖包括：
- Flask
- SQLAlchemy
- PyMySQL
- Streamlit
- MediaPipe
- OpenCV
- Pyttsx3
- Aiohttp

## 安装和运行步骤

1. **克隆或下载项目代码**
   ```bash
   git clone <项目仓库地址>
   cd <项目目录>
创建虚拟环境并激活

bash
复制代码
python -m venv venv
source venv/bin/activate  # Linux/MacOS
venv\Scripts\activate  # Windows
安装依赖项

bash
复制代码
pip install -r requirements.txt
设置环境变量
创建一个.env文件，并添加以下内容：

plaintext
复制代码
SECRET_KEY=your_secret_key
SQLALCHEMY_DATABASE_URI=mysql+pymysql://root:201575@localhost/smart_fitness
创建数据库表

bash
复制代码
python create_tables.py
运行后端服务器

bash
复制代码
python run_backend.py
运行前端应用

bash
复制代码
streamlit run app.py
调用本地Llama3模型
项目中使用Llama3模型来生成健身计划和评估用户的锻炼动作。以下是如何在本地运行Llama3模型的步骤。

安装Llama3
克隆Llama3项目仓库

bash
复制代码
git clone <Llama3项目仓库地址>
cd <Llama3项目目录>
安装Llama3依赖项

bash
复制代码
pip install -r requirements.txt
运行Llama3模型

bash
复制代码
python run_llama3.py
确保Llama3模型运行在默认的localhost:11434端口上。

project-directory/
│
├── .env                   # 环境变量配置文件
├── .vscode/               # VSCode 配置
├── __pycache__/           # 缓存文件
├── app.py                 # Flask应用程序实例和Streamlit前端的入口文件
├── backend/               # 后端相关的模块
│   ├── __init__.py        # 后端初始化
│   ├── models.py          # 数据库模型定义
│   ├── routes.py          # 定义了API路由
│   └── ...
├── config.py              # 包含应用程序的配置
├── create_tables.py       # 用于创建数据库表
├── frontend/              # 前端相关的模块
│   ├── __init__.py        # 前端初始化
│   ├── login.py           # 用户登录功能
│   ├── dashboard.py       # 动作监控页面
│   ├── register.py        # 用户注册功能
│   ├── fitness_plans.py   # 健身计划管理功能
│   ├── workout_sessions.py# 锻炼会话管理功能
│   ├── exercises.py       # 锻炼动作管理功能
│   ├── data_analysis.py   # 数据分析与可视化功能
│   └── ...
├── run_backend.py         # 运行后端服务器
├── utils.py               # 包含通用的工具函数，如密码哈希等
└── requirements.txt       # 项目依赖项
主要模块说明
app.py

创建并配置Flask应用程序实例，初始化数据库，并注册路由。
config.py

包含应用程序的配置，如数据库URI和密钥。
create_tables.py

创建数据库和必要的表。
run_backend.py

启动后端服务器，并提供基本的API端点。
backend/models.py

定义数据库模型，包括用户、健身计划、锻炼会话和锻炼动作。
backend/routes.py

定义API路由，如用户注册、登录、创建健身计划和锻炼会话等。
frontend/dashboard.py

提供动作监控页面，使用摄像头实时监控用户的健身动作，并通过机器学习模型进行评估。
utils.py

包含通用的工具函数，如密码哈希和验证。
许可证
该项目使用MIT许可证，详情请参见LICENSE文件。

贡献
欢迎贡献者xmy提交问题报告、功能请求和拉取请求。
有问题请加v+13801456086