
# astrbot_plugin_onelastimage

<div align="center">
  <a href="https://astrbot.app/" target="_blank">
    <img src="https://github.com/user-attachments/assets/ffd99b6b-3272-4682-beaa-6fe74250f7d9" alt="AstrBot Logo" height="28" style="vertical-align: bottom;">
  </a>
  <a href="https://www.python.org" target="_blank">
    <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" style="vertical-align: bottom;">
  </a>
  <a href="https://vercel.com" target="_blank">
    <img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel" style="vertical-align: bottom;">
  </a>
</div>

**功能：** Astrbot One Last Kiss 卢浮宫风格生成器。

本插件允许用户发送图片，并通过调用 One Last Image API 将其转换为 "One Last Kiss" 艺术风格的图片。

-----

<table align="center">
  <tr>
    <td align="center">
      <p><strong>原图</strong></p>
      <img src="example.jpg" alt="图片1" width="300">
    </td>
    <td align="center">
      <p><strong>效果图</strong></p>
      <img src="example2.jpg" alt="图片2" width="300">
    </td>
  </tr>
</table>



## 1. 安装

1.  在 `data/plugins` 目录下克隆本插件
    ```bash
    git clone https://github.com/timetetng/astrbot_plugin_onelastimage
    ```

2.  安装本插件所需的 Python 依赖库：
    ```bash
    uv add httpx Pillow httpx
    ```
3.  重启 AstrBot，插件将会自动加载。

## 2. 配置

在 WebUI 修改配置项

添加自己的 `One Last Image API URL`, 不知道如何部署的可以查看我的这个项目

[**如何用 Vercel 免费部署自己的 One Last Image API 后端**](https://github.com/timetetng/one-last-image-api)

或者直接点击下面的按钮一键部署:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Ftimetetng%2Fone-last-image-api)

其他参数一般默认即可，详细的参数用法也可以参考[**配置参数**](https://github.com/timetetng/one-last-image-api?tab=readme-ov-file#%E9%85%8D%E7%BD%AE%E5%8F%82%E6%95%B0-config-%E8%AF%A6%E8%A7%A3)。

## 3\. 使用方法

本插件提供一个核心指令 `/onelast`。



### 基础用法

  * **发送图片并使用指令**
    发送 `/onelast` 并同时附带一张或多张图片。
  * **回复图片**
    在聊天中回复一张已发送的图片，并发送指令 `/onelast`。

### 高级用法 (自定义参数)

你可以在指令后跟随一个**Python 字典**格式的字符串，来覆盖默认的 API 参数。

**指令格式：**
`/onelast <参数字典字符串>`

#### ⚠️ 重要提示：

  * 参数必须是**严格的 Json** 格式，包括花括号 `{}`以及键名必须包裹在双引号 `""` 中。
  * 布尔值必须使用`true` 或 `false`，不能使用大写。
  * Json 中**不能含有空格**，这是 Astrbot 命令解析器的缺陷...

### 示例

1.  **使用默认配置生成**

      * `(发送图片)`

        `/onelast`

2.  **自定义参数 (例如开启水印并设置缩放2倍)**

      * `(发送图片)`

        `/onelast {'watermark':true,'zoom':2}`

3.  **回复图片并使用自定义参数**

      * `(引用一条图片消息)`

        `/onelast {'watermark':true,'hajimei':true}`

详细的参数用法也可以参考[**配置参数**](https://github.com/timetetng/one-last-image-api?tab=readme-ov-file#%E9%85%8D%E7%BD%AE%E5%8F%82%E6%95%B0-config-%E8%AF%A6%E8%A7%A3)。
