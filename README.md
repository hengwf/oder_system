# 中餐点餐系统（含堂食 + 外卖）

## 系统简介

本系统为中餐门店专用点餐收银一体化系统，同时支持堂食扫码点餐与外卖平台对接，实现堂食、外卖订单统一管理、后厨统一出餐、财务统一对账，提升出餐效率、减少错单漏单，适配中餐多菜品、多口味、多规格的复杂点餐场景。

## 技术栈

- **后端**: Node.js + Express + MongoDB
- **前端**: React + Ant Design (后台管理) + Ant Design Mobile (顾客端)
- **实时通信**: Socket.io
- **API接口**: RESTful API

## 系统功能

### 1. 顾客端（H5/小程序）
- 扫码识别桌台
- 菜品分类浏览
- 口味、做法、分量选择
- 购物车管理
- 在线支付
- 订单状态查询

### 2. 服务员/收银端
- 开台、并台、转台、清台
- 代客点餐
- 退菜审核
- 收银结账
- 交接班对账

### 3. 后厨端（KDS系统）
- 实时订单接收
- 订单状态管理
- 堂食/外卖区分
- 出餐标记
- 声音提醒

### 4. 后台管理系统
- 菜品管理
- 分类管理
- 桌台管理
- 订单管理
- 会员管理
- 数据统计
- 系统设置

### 5. 外卖平台对接
- 美团订单自动接入
- 饿了么订单自动接入
- 外卖订单状态同步
- 库存管理

## 项目结构

```
food_system/
├── backend/            # 后端服务
│   ├── config/         # 配置文件
│   ├── controllers/    # 控制器
│   ├── models/         # 数据模型
│   ├── routes/         # 路由
│   ├── middleware/     # 中间件
│   ├── services/       # 服务
│   ├── app.js          # 主应用
│   └── package.json    # 依赖配置
├── frontend/           # 前端应用
│   ├── admin/          # 后台管理系统
│   ├── customer/       # 顾客端
│   └── kitchen/        # 后厨KDS系统
├── .env                # 环境变量
└── README.md           # 项目说明
```

## 安装部署

### 1. 环境准备

- Node.js 14+ 
- MongoDB 4.0+

### 2. 安装依赖

```bash
# 安装后端依赖
cd backend
npm install

# 安装前端依赖
cd ../frontend/admin
npm install

cd ../customer
npm install

cd ../kitchen
npm install
```

### 3. 配置环境变量

复制 `.env.example` 文件为 `.env`，并填写相应的配置信息：

```env
# 数据库配置
MONGODB_URI=mongodb://localhost:27017/food_system

# 服务器配置
PORT=3000

# JWT配置
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRES_IN=7d

# 外卖平台配置
MEITUAN_APP_KEY=your_meituan_app_key
MEITUAN_APP_SECRET=your_meituan_app_secret
ELEME_APP_KEY=your_eleme_app_key
ELEME_APP_SECRET=your_eleme_app_secret

# 支付配置
WECHAT_APPID=your_wechat_appid
WECHAT_MCHID=your_wechat_mchid
WECHAT_API_KEY=your_wechat_api_key
ALIPAY_APPID=your_alipay_appid
ALIPAY_PRIVATE_KEY=your_alipay_private_key
ALIPAY_PUBLIC_KEY=your_alipay_public_key
```

### 4. 启动服务

```bash
# 启动后端服务
cd backend
npm run dev

# 启动后台管理系统
cd ../frontend/admin
npm run dev

# 启动顾客端
cd ../customer
npm run dev

# 启动后厨KDS系统
cd ../kitchen
npm run dev
```

### 5. 访问地址

- 后台管理系统: http://localhost:3001
- 顾客端: http://localhost:3002
- 后厨KDS系统: http://localhost:3003

## 系统使用

### 1. 初始化数据

1. 登录后台管理系统（默认账号：admin，密码：123456）
2. 创建菜品分类
3. 添加菜品信息
4. 设置桌台信息

### 2. 堂食流程

1. 顾客扫码桌台二维码
2. 浏览菜单并选择菜品
3. 选择口味、做法、分量
4. 提交订单
5. 后厨接收订单并制作
6. 服务员上菜
7. 顾客用餐后结账

### 3. 外卖流程

1. 顾客在美团/饿了么下单
2. 订单自动同步到系统
3. 后厨接收订单并制作
4. 标记出餐
5. 骑手取餐
6. 完成订单

## 注意事项

1. 外卖平台对接需要在美团和饿了么开放平台注册开发者账号
2. 支付功能需要配置相应的支付商户信息
3. 系统部署到生产环境时需要配置HTTPS
4. 定期备份数据库以防止数据丢失

## 技术支持

如有技术问题，请联系系统管理员。
