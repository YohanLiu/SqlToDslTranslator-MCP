# SQL to Elasticsearch DSL Translator

## 项目简介

SQL to Elasticsearch DSL Translator 是一个基于 MCP (Model Conversion Platform) 框架构建的服务，可以将 MySQL SQL 查询语句转换为 Elasticsearch DSL (Domain Specific Language) 查询。

该工具支持常见的 SQL 操作，包括：
- SELECT 查询
- WHERE 条件过滤
- GROUP BY 聚合
- ORDER BY 排序
- LIMIT 限制结果数量
- 函数操作（COUNT, AVG, SUM等）
- UNION 和 MINUS 操作

这个转换器可以帮助熟悉 SQL 语法但不熟悉 Elasticsearch DSL 的开发者快速构建 Elasticsearch 查询。

**整个项目全是基于 ai 的自主生成。**
支持版本: Elasticsearch 7.17

## 部署指南
### 使用 uvx（推荐）

```bash
uvx sqltodsltranslator-mcp@latest
```

### 使用 pip

```bash
pip install sqltodsltranslator-mcp
```

### 从源码安装

```bash
git clone https://github.com/YohanLiu/SqlToDslTranslator-MCP
cd SqlToDslTranslator-MCP
pip install -e .
```

### 应用配置

#### Claude Desktop 配置

在应用配置文件中添加以下配置：

```json
{
  "mcpServers": {
    "SqlToDslTranslator": {
      "args": [
        "sqltodsltranslator-mcp@latest"
      ],
      "command": "uvx"
    }
  }
}
```

#### Cherry Studio 配置

```json
{
  "mcpServers": {
    "SqlToDslTranslator": {
      "args": [
        "sqltodsltranslator-mcp@latest"
      ],
      "command": "uvx"
    }
  }
}
```

## 使用示例

**演示示例用 Cherry Studio进行演示**
首先在对话框中选择此 mcp 工具

![image-20250831214721589](https://gitee.com/yohan_liu/photo/raw/master/20250831214721670.png)

然后输入形如如下的文案即可进行对比 `帮我转成DSL：SELECT id, name, age FROM users WHERE age > 18 AND status = 'active' ORDER BY age DESC LIMIT 10`

![image-20250831214739269](https://gitee.com/yohan_liu/photo/raw/master/20250831214739341.png)

演示视频链接：https://www.bilibili.com/video/BV1vCa5zwEM1/