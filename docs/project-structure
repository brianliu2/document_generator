# 数据合成器项目结构文档

## 1. 项目概述

数据合成器是一个全栈应用，由前端（基于现代JavaScript框架）和后端（基于Python Django）组成。该应用允许用户上传文件，提取文本，优化提示词，并生成专业数据。

## 2. 技术栈

### 2.1 前端
- **框架**：Vue.js 3
- **UI库**：Element Plus
- **状态管理**：Pinia
- **HTTP客户端**：Axios
- **路由**：Vue Router
- **构建工具**：Vite
- **语言**：TypeScript

### 2.2 后端
- **框架**：Django 4.2+
- **API框架**：Django REST Framework
- **数据库**：PostgreSQL
- **异步任务**：Celery
- **缓存**：Redis
- **AI集成**：OpenAI, DeepSeek, Gemini APIs
- **文件存储**：Django FileField + 云存储选项

## 3. 目录结构

```
document_generator/
├── frontend/                        # 前端应用
│   ├── public/                      # 静态资源
│   ├── src/
│   │   ├── assets/                  # 图片、样式等资源
│   │   ├── components/              # 可复用组件
│   │   │   ├── common/              # 公共UI组件
│   │   │   ├── file-upload/         # 文件上传相关组件
│   │   │   ├── text-extraction/     # 文本提取相关组件
│   │   │   ├── prompt-optimizer/    # 提示词优化相关组件
│   │   │   └── model-management/    # 模型管理相关组件
│   │   ├── views/                   # 页面视图
│   │   │   ├── HomeView.vue         # 主页
│   │   │   ├── UploadView.vue       # 上传页面
│   │   │   ├── ExtractView.vue      # 提取页面
│   │   │   ├── OptimizerView.vue    # 优化页面
│   │   │   ├── ModelsView.vue       # 模型管理页面
│   │   │   └── HistoryView.vue      # 历史记录页面
│   │   ├── stores/                  # Pinia 状态存储
│   │   │   ├── file.ts              # 文件存储
│   │   │   ├── extraction.ts        # 提取结果存储
│   │   │   ├── prompt.ts            # 提示词存储
│   │   │   ├── model.ts             # 模型配置存储
│   │   │   └── history.ts           # 历史记录存储
│   │   ├── services/                # API服务
│   │   │   ├── api.ts               # API基础设置
│   │   │   ├── fileService.ts       # 文件相关API
│   │   │   ├── extractionService.ts # 提取相关API
│   │   │   ├── promptService.ts     # 提示词相关API
│   │   │   ├── modelService.ts      # 模型相关API
│   │   │   └── historyService.ts    # 历史记录相关API
│   │   ├── utils/                   # 工具函数
│   │   ├── router/                  # 路由配置
│   │   ├── types/                   # TypeScript类型定义
│   │   ├── App.vue                  # 根组件
│   │   └── main.ts                  # 入口文件
│   ├── .env                         # 环境变量
│   ├── vite.config.ts               # Vite配置
│   ├── tsconfig.json                # TypeScript配置
│   ├── package.json                 # 依赖管理
│   └── README.md                    # 前端说明文档
│
├── backend/                         # Django后端应用
│   ├── document_generator/          # Django项目配置
│   │   ├── __init__.py
│   │   ├── settings/                # 多环境配置
│   │   │   ├── __init__.py
│   │   │   ├── base.py              # 基础设置
│   │   │   ├── development.py       # 开发环境
│   │   │   └── production.py        # 生产环境
│   │   ├── urls.py                  # URL路由
│   │   ├── wsgi.py                  # WSGI配置
│   │   ├── asgi.py                  # ASGI配置
│   │   └── celery.py                # Celery配置
│   │
│   ├── apps/                        # Django应用
│   │   ├── core/                    # 核心功能
│   │   │   ├── __init__.py
│   │   │   ├── admin.py             # 管理界面配置
│   │   │   ├── apps.py              # 应用配置
│   │   │   ├── models.py            # 数据模型
│   │   │   ├── serializers.py       # DRF序列化器
│   │   │   ├── views.py             # API视图
│   │   │   ├── urls.py              # URL配置
│   │   │   └── tests.py             # 测试
│   │   │
│   │   ├── file_manager/            # 文件管理应用
│   │   │   ├── __init__.py
│   │   │   ├── admin.py
│   │   │   ├── apps.py
│   │   │   ├── models.py            # 文件模型
│   │   │   ├── serializers.py
│   │   │   ├── views.py             # 文件上传API
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── text_extraction/         # 文本提取应用
│   │   │   ├── __init__.py
│   │   │   ├── admin.py
│   │   │   ├── apps.py
│   │   │   ├── models.py            # 提取结果模型
│   │   │   ├── serializers.py
│   │   │   ├── services/            # 提取服务
│   │   │   │   ├── __init__.py
│   │   │   │   ├── vlm_service.py   # VLM API服务
│   │   │   │   └── converter.py     # 文件转换器
│   │   │   ├── views.py             # 提取API
│   │   │   ├── urls.py
│   │   │   ├── tasks.py             # Celery任务
│   │   │   └── tests.py
│   │   │
│   │   ├── prompt_optimizer/        # 提示词优化应用
│   │   │   ├── __init__.py
│   │   │   ├── admin.py
│   │   │   ├── apps.py
│   │   │   ├── models.py            # 提示词模型
│   │   │   ├── serializers.py
│   │   │   ├── services/            # 优化服务
│   │   │   │   ├── __init__.py
│   │   │   │   └── llm_service.py   # LLM API服务
│   │   │   ├── views.py             # 优化API
│   │   │   ├── urls.py
│   │   │   ├── tasks.py             # Celery任务
│   │   │   └── tests.py
│   │   │
│   │   └── model_management/        # 模型管理应用
│   │       ├── __init__.py
│   │       ├── admin.py
│   │       ├── apps.py
│   │       ├── models.py            # 模型配置
│   │       ├── serializers.py
│   │       ├── views.py             # 模型管理API
│   │       ├── urls.py
│   │       └── tests.py
│   │
│   ├── utils/                       # 工具函数
│   │   ├── __init__.py
│   │   ├── api_clients/             # API客户端
│   │   │   ├── __init__.py
│   │   │   ├── openai_client.py
│   │   │   ├── deepseek_client.py
│   │   │   └── gemini_client.py
│   │   ├── security.py              # 安全相关工具
│   │   └── validators.py            # 验证工具
│   │
│   ├── media/                       # 用户上传文件
│   ├── static/                      # 静态文件
│   ├── templates/                   # 模板文件
│   ├── manage.py                    # Django管理脚本
│   ├── requirements/                # 依赖管理
│   │   ├── base.txt                 # 基础依赖
│   │   ├── development.txt          # 开发依赖
│   │   └── production.txt           # 生产依赖
│   └── README.md                    # 后端说明文档
│
├── docs/                            # 项目文档
│   ├── prod.md                      # 产品需求
│   ├── project-structure.md         # 项目结构（本文档）
│   ├── technical-development-guide.md # 技术开发指南
│   ├── api-documentation.md         # API文档
│   ├── deployment-guide.md          # 部署指南
│   └── user-guide.md                # 用户指南
│
├── docker/                          # Docker配置
│   ├── frontend/                    # 前端Docker配置
│   │   └── Dockerfile
│   ├── backend/                     # 后端Docker配置
│   │   └── Dockerfile
│   ├── nginx/                       # Nginx配置
│   │   ├── Dockerfile
│   │   └── nginx.conf
│   └── docker-compose.yml           # Docker Compose配置
│
└── scripts/                         # 工具脚本
    ├── setup.sh                     # 项目初始化脚本
    ├── dev.sh                       # 开发环境启动脚本
    └── deploy.sh                    # 部署脚本
```

## 4. 数据库设计

### 4.1 UploadedFile 模型
```python
class UploadedFile(models.Model):
    file = models.FileField(upload_to='uploads/')
    file_name = models.CharField(max_length=255)
    file_type = models.CharField(max_length=50)
    file_size = models.IntegerField()
    upload_date = models.DateTimeField(auto_now_add=True)
    user = models.ForeignKey(User, on_delete=models.CASCADE, null=True, blank=True)
```

### 4.2 ExtractedText 模型
```python
class ExtractedText(models.Model):
    uploaded_file = models.ForeignKey(UploadedFile, on_delete=models.CASCADE)
    text_content = models.TextField()
    format_type = models.CharField(max_length=20)  # markdown, html, text
    extraction_date = models.DateTimeField(auto_now_add=True)
    model_used = models.CharField(max_length=50)
```

### 4.3 PromptTemplate 模型
```python
class PromptTemplate(models.Model):
    name = models.CharField(max_length=100)
    template_text = models.TextField()
    description = models.TextField(blank=True, null=True)
    created_date = models.DateTimeField(auto_now_add=True)
    updated_date = models.DateTimeField(auto_now=True)
```

### 4.4 OptimizedPrompt 模型
```python
class OptimizedPrompt(models.Model):
    original_prompt = models.TextField()
    optimized_prompt = models.TextField()
    extracted_text = models.ForeignKey(ExtractedText, on_delete=models.SET_NULL, null=True, blank=True)
    model_used = models.CharField(max_length=50)
    created_date = models.DateTimeField(auto_now_add=True)
    user = models.ForeignKey(User, on_delete=models.CASCADE, null=True, blank=True)
```

### 4.5 ModelConfig 模型
```python
class ModelConfig(models.Model):
    name = models.CharField(max_length=100)
    provider = models.CharField(max_length=50)  # OpenAI, DeepSeek, Gemini, etc.
    model_identifier = models.CharField(max_length=100)
    api_key = models.CharField(max_length=255, blank=True, null=True)  # Encrypted
    base_url = models.URLField(blank=True, null=True)
    default = models.BooleanField(default=False)
    created_date = models.DateTimeField(auto_now_add=True)
    updated_date = models.DateTimeField(auto_now=True)
    user = models.ForeignKey(User, on_delete=models.CASCADE, null=True, blank=True)
```

## 5. API 端点设计

### 5.1 文件管理 API
```
POST   /api/files/upload/            # 上传文件
GET    /api/files/                   # 获取文件列表
GET    /api/files/{id}/              # 获取文件详情
DELETE /api/files/{id}/              # 删除文件
```

### 5.2 文本提取 API
```
POST   /api/extraction/extract/      # 提取文本
GET    /api/extraction/              # 获取提取历史
GET    /api/extraction/{id}/         # 获取提取详情
PUT    /api/extraction/{id}/format/  # 更改格式（Markdown/HTML/Text）
DELETE /api/extraction/{id}/         # 删除提取记录
```

### 5.3 提示词优化 API
```
POST   /api/prompts/optimize/        # 优化提示词
GET    /api/prompts/                 # 获取提示词历史
GET    /api/prompts/{id}/            # 获取提示词详情
POST   /api/prompts/templates/       # 创建模板
GET    /api/prompts/templates/       # 获取模板列表
GET    /api/prompts/templates/{id}/  # 获取模板详情
PUT    /api/prompts/templates/{id}/  # 更新模板
DELETE /api/prompts/templates/{id}/  # 删除模板
```

### 5.4 模型管理 API
```
POST   /api/models/                  # 创建模型配置
GET    /api/models/                  # 获取模型列表
GET    /api/models/{id}/             # 获取模型详情
PUT    /api/models/{id}/             # 更新模型配置
DELETE /api/models/{id}/             # 删除模型配置
POST   /api/models/{id}/verify/      # 验证API密钥
PUT    /api/models/{id}/default/     # 设为默认模型
```

### 5.5 用户管理 API
```
POST   /api/auth/login/              # 登录
POST   /api/auth/logout/             # 登出
POST   /api/auth/register/           # 注册
GET    /api/auth/user/               # 获取用户信息
PUT    /api/auth/user/               # 更新用户信息
```

## 6. 前端路由设计

```
/                  # 主页
/upload            # 文件上传页面
/extract           # 文本提取页面
/optimize          # 提示词优化页面
/models            # 模型管理页面
/history           # 历史记录页面
/login             # 登录页面
/register          # 注册页面
/profile           # 用户资料页面
```

## 7. 部署架构

### 7.1 开发环境
- 前端：Vite 开发服务器
- 后端：Django 开发服务器
- 数据库：SQLite / PostgreSQL
- 缓存：本地内存缓存

### 7.2 生产环境
- 前端：Nginx + 静态文件
- 后端：Gunicorn + Django
- 数据库：PostgreSQL
- 缓存：Redis
- 任务队列：Celery + Redis
- 反向代理：Nginx
- 容器化：Docker + Docker Compose
- CI/CD：GitHub Actions / Jenkins

## 8. 安全考虑

### 8.1 API 密钥管理
- 使用 Django 的 SECRET_KEY 加密存储 API 密钥
- 前端不存储明文密钥
- 使用环境变量传递敏感信息

### 8.2 认证与授权
- 基于 JWT 的认证
- 基于角色的访问控制
- CSRF 保护
- XSS 防御

### 8.3 数据安全
- HTTPS 加密传输
- 敏感数据加密存储
- 定期备份
- 日志审计

## 9. 性能优化策略

### 9.1 前端优化
- 代码分割与懒加载
- 资源压缩
- 缓存策略
- CDN 加速

### 9.2 后端优化
- 数据库索引优化
- 查询优化
- 缓存机制
- 异步任务处理

## 10. 测试策略

### 10.1 前端测试
- 单元测试：Vue Test Utils
- 端到端测试：Cypress
- 组件测试：Storybook

### 10.2 后端测试
- 单元测试：Django TestCase
- API 测试：DRF Test
- 集成测试：pytest
- 性能测试：Locust

## 11. 未来扩展考虑

### 11.1 技术扩展
- GraphQL API 支持
- WebSocket 实时通信
- 微服务架构迁移
- Kubernetes 部署

### 11.2 功能扩展
- 移动端适配
- 更多 LLM 模型支持
- 提示词模板库
- 批量优化功能
- 团队协作功能