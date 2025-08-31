# 智能办公系统

基于Vue和Python的现代化智能办公系统，集成了AI功能，提供一站式企业办公解决方案。

## 技术栈

### 前端
- Vue.js 3
- Vue Router
- Element Plus UI组件库
- Axios
- Three.js (3D渲染库)
- GLTF模型加载

### 后端
- Python
- Django (Web框架)
- LangChain (AI框架)
- DeepSeek-v3-0324 (LLM模型)
- PyYAML (配置管理)

## 项目结构
```
smart-office/
├── frontend/           # Vue前端项目
│   ├── public/         # 静态资源
│   └── src/            # 源代码
│       ├── api/        # API接口
│       ├── assets/     # 资源文件
│       ├── components/ # 组件
│       ├── router/     # 路由配置
│       ├── store/      # 状态管理
│       ├── utils/      # 工具函数
│       └── views/      # 页面视图
└── backend/            # Python后端项目
    ├── config/         # 配置文件
    ├── setting.yaml    # YAML格式配置文件
    ├── apps/           # 应用模块
    │   ├── auth/       # 认证模块
    │   ├── dashboard/  # 仪表盘模块
    │   └── ...         # 其他业务模块
    └── ai/             # AI相关功能
        └── langchain/  # LangChain集成
```

## 数据库构建与配置

### 数据库配置

项目使用YAML格式的配置文件`setting.yaml`管理数据库配置：


1. 编辑`setting.yaml`文件，配置数据库连接信息：
```yaml
# 数据库设置
database:
  engine: "django.db.backends.mysql"  # 可选：postgresql、sqlite3、oracle等
  name: "smart_office"
  user: "your_database_user"
  password: "your_database_password"
  host: "localhost"
  port: "3306"
```

2. 数据库配置字段说明：
   - `engine`: 数据库引擎类型
   - `name`: 数据库名称
   - `user`: 数据库用户名
   - `password`: 数据库密码
   - `host`: 数据库服务器地址
   - `port`: 数据库端口号

### 数据库迁移流程

每当您修改模型时，需要创建并应用迁移：

1. 生成迁移文件：
```bash
cd backend
python manage.py makemigrations
```


2. 应用迁移到数据库：
```bash
python manage.py migrate
```

### 数据初始化与管理

1. 创建企业管理员：
```bash
python manage.py createsuperuser
```



## 启动项目

### 后端启动

1. 安装依赖：
```bash
cd backend
pip install -r requirements.txt
```

2. 执行数据库迁移：
```bash
python manage.py migrate
```

3. 启动开发服务器：
```bash
python manage.py runserver
```


### 前端启动

1. 安装依赖：
```bash
cd frontend
npm install
```

2. 开发环境启动：
```bash
npm run dev
```

3. 构建生产版本：
```bash
npm run build
```
