# 南工校园助手

一个面向南京工业大学学生的非官方 Android 校园工具。应用可登录教务系统并集中展示课表、课程成绩和考试安排，同时提供倒数日、随手记等日常功能。

> 本项目仅用于学习与技术交流，与南京工业大学官方无隶属或合作关系。请勿将项目用于商业、攻击、批量抓取或其他违反学校规定的用途。

## 主要功能

- **教务系统登录**：支持登录状态保持；账号和密码使用 Android Keystore 在本机加密保存。
- **成绩查询**：查看课程成绩、学分与绩点，计算平均绩点和加权均分，并支持按学年、学期、课程类型筛选与排序。
- **绩点趋势**：按学期展示平均绩点变化。
- **我的课表**：从教务系统获取课表，以周视图显示，支持刷新、手动添加课程和查看教师、教室、周次等详情。
- **考试通知**：默认展示当前学期考试，可按学年、学期或全部记录进行筛选。
- **校园日常**：主页内置倒数日和随手记。
- **显示设置**：支持字号调整以及亮色、暗色和跟随系统主题。

## 项目信息

| 项目 | 内容 |
| --- | --- |
| 应用名称 | 南工校园助手 |
| 当前版本 | 1.2.2 |
| 应用包名 | `com.njtech.gradebook` |
| 开发语言 | Java 11 |
| 最低系统 | Android 6.0（API 23） |
| 目标系统 | Android API 35 |
| 开发工具 | Android Studio、Gradle |

## 获取源码

```bash
git clone https://github.com/BLEXX123/NJTech-Campus-Assistant.git
cd NJTech-Campus-Assistant
```

克隆完成后使用 Android Studio 打开项目根目录，等待 Gradle 同步完成即可运行。

也可以在 Windows PowerShell 中构建调试版：

```powershell
.\gradlew.bat assembleDebug
```

生成的 APK 位于：

```text
app/build/outputs/apk/debug/app-debug.apk
```

## 正式版签名

签名密钥和口令不得上传到 GitHub。本项目已通过 `.gitignore` 排除 `keystore.properties`、`.signing/`、`*.jks` 和 `*.keystore`。

如需构建自己的正式版本，请在项目根目录创建仅供本机使用的 `keystore.properties`：

```properties
storeFile=.signing/your-release-key.jks
storePassword=your_store_password
keyAlias=your_key_alias
keyPassword=your_key_password
```

然后运行：

```powershell
.\gradlew.bat assembleRelease
```

请妥善备份自己的签名密钥。同一应用后续版本必须使用相同密钥签名，才能覆盖安装和正常升级。

## 隐私与安全

- 登录凭据仅保存在用户设备本地，并通过 Android Keystore 加密。
- 项目不应包含真实账号、密码、Cookie、签名密钥或其他个人隐私数据。
- 应用直接访问学校教务系统，教务网站接口或页面结构发生变化时，相关解析功能可能需要同步调整。
- 发布截图前请遮挡学号、姓名、成绩、考试地点等个人信息。

## 开源说明与致谢

课表功能的实现参考了 [GiuseppeLR/njtech_timetable](https://github.com/GiuseppeLR/njtech_timetable)，原项目采用 Apache License 2.0。公开发布或继续分发相关衍生代码时，请保留原项目的许可证及必要署名。

当前仓库尚未添加用于声明本项目整体授权方式的根目录 `LICENSE`。如需允许他人复制、修改和分发，请在确认所有素材及参考代码授权兼容后，选择并添加合适的开源许可证。

## 开发人员

- Spirituel
- codex
- deepseek
- trae

## 免责声明

本项目仅供学习交流使用。使用者应遵守所在学校的规章制度及相关法律法规，并对自己的操作负责。开发者不对因不当使用、教务系统变更、网络异常或数据解析差异造成的后果承担责任。

## 反馈

如遇到问题，欢迎通过 GitHub Issues 提交。请勿在 Issue 中公开账号、密码、Cookie、学号、成绩或其他个人信息。
