# B站API服务器 Bilibili Api

一个为bilibili.com API提供服务的Model Context Protocol (MCP)服务器，支持获取用户信息、视频搜索等功能。
A Model Context Protocol (MCP) server that provides services for the bilibili.com API, supporting functions such as obtaining user information and video search.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| get_user_info | Get information about a Bilibili user |
| get_video_info | Get detailed information about a Bilibili video |
| search_videos | Search for videos on Bilibili |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659451907](https://mcp.xiaobenyang.com/inspector/1777316659451907)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659451907](https://mcp.xiaobenyang.com/inspector/1777316659451907)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "B站API服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659451907/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "B站API服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659451907/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "B站API服务器": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659451907",
          },
          "transport": "stdio"
        }
      }
}

```
