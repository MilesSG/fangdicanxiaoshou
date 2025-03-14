# 🏢 房地产销售管理系统 (Real Estate Sales Management System)

## 📋 项目简介 (Project Introduction)

房地产销售管理系统是一个基于Spring Boot和MyBatis-Plus开发的全功能Web应用，专为房地产销售行业设计。系统提供了完整的房产信息管理、客户资源管理、销售记录跟踪和数据统计分析功能，帮助房地产销售企业高效管理销售流程和客户资源。

## 🔍 系统功能 (System Features)

### 🏠 前台功能模块
- **房产展示**：多维度展示房产信息，包括户型、面积、价格、位置等
- **在线预约**：客户可在线预约看房，系统自动记录客户意向
- **用户论坛**：提供交流平台，用户可分享购房经验和问题
- **新闻公告**：发布行业动态、政策信息和企业公告
- **收藏功能**：用户可收藏心仪房源，方便后续查看
- **个人中心**：用户可管理个人信息、查看收藏房源和预约记录

### 🔐 后台管理模块
- **房产管理**：添加、编辑、删除房产信息，上传房产图片
- **客户管理**：记录客户信息，跟踪客户意向，管理客户关系
- **销售记录**：记录销售过程，生成销售报表，统计销售业绩
- **员工管理**：管理销售人员信息，分配客户资源，评估业绩
- **系统设置**：配置系统参数，管理用户权限，维护数据字典
- **数据统计**：多维度统计分析销售数据，支持可视化图表展示

## 🛠️ 技术架构 (Technical Architecture)

- **后端框架**：Spring Boot 2.2.2.RELEASE
- **ORM框架**：MyBatis-Plus 2.3
- **数据库**：MySQL 8.0
- **前端技术**：HTML5, CSS3, JavaScript, jQuery, ElementUI
- **模板引擎**：Thymeleaf
- **项目构建**：Maven
- **权限控制**：基于拦截器的权限管理
- **数据交互**：RESTful API风格

## 📥 快速开始 (Quick Start)

### 1. 环境准备
- JDK 1.8+
- Maven 3.0+
- MySQL 8.0+
- Eclipse/IntelliJ IDEA (推荐)

### 2. 数据库配置
1. 创建名为`fangdicanxiaoshou`的数据库
```sql
CREATE DATABASE IF NOT EXISTS fangdicanxiaoshou DEFAULT CHARSET utf8mb4 COLLATE utf8mb4_general_ci;
```
2. 使用提供的SQL脚本初始化数据库结构和基础数据
3. 配置数据库连接（默认用户名：root，密码：888999）

### 3. 项目启动
1. 克隆项目到本地
```bash
git clone https://github.com/MilesSG/fangdicanxiaoshou.git
```
2. 使用IDE导入Maven项目
3. 更新配置文件`src/main/resources/application.yml`中的数据库连接信息
4. 运行`com.fangdicanxiaoshouApplication.java`启动项目
   或使用Maven命令启动：
```bash
mvn spring-boot:run
```

### 4. 访问系统
- 前台访问：http://localhost:8080/fangdicanxiaoshou/front/index.html
- 后台管理：http://localhost:8080/fangdicanxiaoshou/admin/dist/index.html

## 👥 用户账号 (User Accounts)

### 管理员账号
- **账号**：admin
- **密码**：admin

### 普通用户账号
- **账号**：a1
- **密码**：123456

## 📁 项目结构 (Project Structure)

```
fangdicanxiaoshou/
├── docs/               # 项目文档
├── src/                # 源代码
│   ├── main/
│       ├── java/       # Java代码 
│       │   └── com/
│       │       ├── controller/  # 控制器层
│       │       ├── service/     # 服务层
│       │       ├── dao/         # 数据访问层
│       │       ├── entity/      # 实体类
│       │       ├── utils/       # 工具类
│       │       └── config/      # 配置类 
│       └── resources/  # 资源文件
│           ├── mapper/          # MyBatis映射文件
│           ├── static/          # 静态资源
│           ├── admin/           # 后台管理前端代码
│           ├── front/           # 前台展示前端代码
│           └── application.yml  # 配置文件
└── pom.xml             # Maven配置文件
```

## 🔧 核心配置 (Core Configuration)

### 数据库配置
```yaml
spring:
    datasource:
        driverClassName: com.mysql.cj.jdbc.Driver
        url: jdbc:mysql://127.0.0.1:3306/fangdicanxiaoshou?useUnicode=true&characterEncoding=utf-8&useJDBCCompliantTimezoneShift=true&useLegacyDatetimeCode=false&serverTimezone=GMT%2B8
        username: root
        password: 888999
```

### 文件上传配置
```yaml
spring:
    servlet:
      multipart:
        max-file-size: 1000MB
        max-request-size: 1000MB
    resources:
      static-locations: classpath:static/,file:static/
```

### MyBatis-Plus配置
```yaml
mybatis-plus:
  mapper-locations: classpath*:mapper/*.xml
  typeAliasesPackage: com.entity
  global-config:
    id-type: 1
    field-strategy: 2
    db-column-underline: true
    refresh-mapper: true
    logic-delete-value: -1
    logic-not-delete-value: 0
  configuration:
    map-underscore-to-camel-case: true
    cache-enabled: false
    call-setters-on-nulls: true
```

## 📦 主要功能模块 (Main Modules)

- **房产信息管理**：房源录入、查询、修改、删除；房源图片上传管理
- **客户管理**：客户信息录入、查询、修改、删除；客户跟进记录管理
- **销售记录管理**：销售记录录入、查询、统计；销售业绩分析
- **在线预约管理**：预约信息管理、预约状态更新、预约提醒
- **论坛管理**：帖子管理、回复管理、敏感内容过滤
- **新闻公告管理**：新闻编辑、发布、修改、删除；公告管理
- **系统管理**：用户管理、角色权限管理、系统参数配置

## 📝 详细文档 (Documentation)

更详细的系统文档和使用指南，请参阅：[使用说明文档](/docs/使用说明文档.md)

## 🔄 更新日志 (Change Log)

- **2025-03-14**: 首次发布，完成基础功能开发
- **2025-03-14**: 添加详细文档，优化README

## 👨‍💻 贡献者 (Contributors)

- MilesSG - 系统设计与开发

## 📄 许可证 (License)

本项目基于MIT许可证开源 - 详见 [LICENSE](LICENSE) 文件

---

© 2025 房地产销售管理系统 | All Rights Reserved 