# 项目结构文档

> **注意:** 本文档专注于项目的文件和目录结构。关于技术栈详情和实现流程，请参考 [技术文档](./technical-documentation.md)。

## 1. 项目整体架构

### 1.1 根目录结构
```
document_generator/
├── frontend/            # 前端项目
│   ├── packages/        # 前端包
│   │   ├── core/        # 核心功能包
│   │   │   ├── src/     # 核心源代码
│   │   │   └── package.json # 核心包配置
│   │   └── web/         # Web版本
│   │       ├── src/     # Web源代码
│   │       └── package.json # Web包配置
│   └── ...配置文件
├── backend/             # Django后端
│   ├── document_generator/  # Django项目
│   │   ├── api/         # API应用
│   │   ├── file_processor/ # 文件处理应用
│   │   ├── text_extractor/ # 文本提取应用
│   │   ├── prompt_optimizer/ # 提示词优化应用
│   │   └── ...Django配置文件
│   ├── manage.py        # Django管理脚本
│   └── requirements.txt # Python依赖
├── docs/                # 项目文档
└── ...配置文件
```

### 1.2 配置文件
- `.env.example` - 环境变量示例
- `.gitignore` - Git忽略配置
- `README.md` - 项目说明文档
- `.vscode/` - VSCode配置目录

### 1.3 文档目录 (docs/)
- `README.md` - 文档索引
- `development-guidelines.md` - 开发指南
- `project-status.md` - 项目状态
- `project-structure.md` - 项目结构
- `technical-documentation.md` - 技术文档
- `prod.md` - 产品需求文档
- `CHANGELOG.md` - 更新日志

## 2. 前端核心包结构 (frontend/packages/core)

### 2.1 源代码目录 (frontend/packages/core/src/)
```
src/
├── api/               # API客户端
│   ├── client.ts      # API客户端实现
│   ├── endpoints.ts   # API端点定义
│   └── types.ts       # API类型定义
├── types/             # 公共类型定义
│   ├── file.ts        # 文件相关类型
│   ├── prompt.ts      # 提示词相关类型
│   └── model.ts       # 模型相关类型
└── utils/             # 工具函数
    ├── formatters.ts  # 格式化工具
    └── validators.ts  # 验证工具
```

### 2.2 核心包配置
- `package.json` - 核心包配置
- `tsconfig.json` - TypeScript配置

## 3. 前端Web包结构 (frontend/packages/web)

### 3.1 源代码目录 (frontend/packages/web/src/)
```
src/
├── components/        # Vue组件
│   ├── FileUpload.vue    # 文件上传组件
│   ├── TextViewer.vue    # 文本查看组件
│   ├── PromptEditor.vue  # 提示词编辑组件
│   ├── ModelSelector.vue # 模型选择组件
│   └── ResultViewer.vue  # 结果查看组件
├── services/          # 业务逻辑
│   ├── fileService.js   # 文件服务
│   ├── promptService.js # 提示词服务
│   └── modelService.js  # 模型服务
├── assets/           # 静态资源
│   ├── images/       # 图片资源
│   └── styles/       # 样式资源
├── App.vue           # 根组件
└── main.ts           # 入口文件
```

### 3.2 Web包配置
- `package.json` - Web包配置
- `vite.config.ts` - Vite配置
- `tailwind.config.js` - TailwindCSS配置
- `.env.local` - 本地环境变量
- `index.html` - 项目入口HTML文件

## 4. 后端结构 (backend/)

### 4.1 Django项目结构 (backend/document_generator/)
```
document_generator/
├── document_generator/    # Django项目配置
│   ├── settings.py      # 项目设置
│   ├── urls.py          # URL配置
│   ├── asgi.py          # ASGI配置
│   └── wsgi.py          # WSGI配置
├── api/                 # API应用
│   ├── views.py         # API视图
│   ├── serializers.py   # 序列化器
│   ├── urls.py          # API URL配置
│   └── tests.py         # API测试
├── file_processor/      # 文件处理应用
│   ├── models.py        # 文件模型
│   ├── services.py      # 文件处理服务
│   └── tests.py         # 文件处理测试
├── text_extractor/      # 文本提取应用
│   ├── services.py      # 文本提取服务
│   ├── adapters/        # VLM适配器
│   │   ├── openai.py    # OpenAI适配器
│   │   └── gemini.py    # Gemini适配器
│   └── tests.py         # 文本提取测试
└── prompt_optimizer/    # 提示词优化应用
    ├── services.py      # 提示词优化服务
    ├── adapters/        # LLM适配器
    │   ├── openai.py    # OpenAI适配器
    │   ├── deepseek.py  # DeepSeek适配器
    │   └── gemini.py    # Gemini适配器
    └── tests.py         # 提示词优化测试
```

### 4.2 Django配置文件
- `manage.py` - Django管理脚本
- `requirements.txt` - Python依赖
- `.env` - 环境变量

## 5. 依赖关系

### 5.1 前端核心包依赖
```
@document-generator/core
├── axios ^1.6.0         # HTTP客户端
└── zod ^3.22.4          # 类型验证
```

### 5.2 前端Web包依赖
```
@document-generator/web
├── @document-generator/core  # 依赖核心包
├── vue ^3.5.x             # Vue框架
├── pinia ^2.1.x           # 状态管理
└── tailwindcss ^3.4.1     # 样式框架
```

### 5.3 后端依赖
```
Django==5.0.0              # Django框架
djangorestframework==3.14.0 # Django REST框架
python-dotenv==1.0.0       # 环境变量管理
openai==1.12.0             # OpenAI API
google-generativeai==0.3.0 # Google Generative AI
pillow==10.2.0             # 图像处理
```

## 6. 前后端交互流程

前端和后端通过RESTful API进行交互，主要流程如下：

1. **文件上传流程**
   - 前端：用户通过FileUpload组件上传文件
   - 后端：file_processor应用接收并存储文件
   - 后端：text_extractor应用提取文件文本
   - 前端：显示提取的文本

2. **提示词优化流程**
   - 前端：用户编辑提示词
   - 后端：prompt_optimizer应用优化提示词
   - 前端：显示优化结果

3. **数据生成流程**
   - 前端：用户确认最终提示词
   - 后端：使用提示词生成数据
   - 前端：显示生成的数据

这个MVP结构专注于实现基本功能，后续可以根据需要扩展更多功能。
