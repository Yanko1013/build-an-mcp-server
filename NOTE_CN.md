# 学习笔记

来源自 [MCP](https://modelcontextprotocol.io/docs/develop/build-server#typescript)，学习做一个 mcp 服务。

MCP: Model Context Protocol.

MCP 服务器主要包含以下三种能力：

- 资源（比如网络响应、静态文件）
- 工具（可以被调用的函数）
- 预设定提示词

两种通信模式，STDIO 服务器（本地 node xxx）和 HTTP 服务器

在 STDIO 模式下，不能用 console.log 打日志，MCP server 和 client（比如 CLI / IDE）之间是这样通信的：

stdin：client → server（发请求 JSON-RPC）
stdout：server → client（返回响应 JSON-RPC）

而 console.log 本质上是 process.stdout.write，会直接往 stdout 写数据

本来返回的是

``` json
{
  "a": 1
}
```

现在可能变成

```json

Hello World
{
  "a": 1
}

```

不符合 JSON-RPC
