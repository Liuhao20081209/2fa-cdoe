# TOTP‑2FA
纯静态浏览器端TOTP二次验证码生成工具，无需后端，所有运算在浏览器本地完成

## 预览
https://code-2fa.netlify.app

## 功能特性
1. 支持标准TOTP算法，SHA‑1 / SHA‑256哈希，6位/8位验证码，30秒/60秒周期
2. 本地存储账号列表，数据保存在浏览器localStorage
3. 主题切换，亮色/暗色模式，自动跟随系统主题偏好
4. 导出加密备份：使用AES‑GCM + PBKDF2对备份文件加密
5. 导入加密备份：仅支持本工具生成的加密备份文件，导入为追加模式，不会覆盖已有账号。
6. 单条账号删除，验证码复制

## 部署要求
本工具依赖浏览器`crypto.subtle`安全密码学API，**必须运行在HTTPS环境或者本机localhost HTTP环境**
- 推荐部署平台: Netlify、GitHub Pages，平台默认提供HTTPS
- 本地调试（仅本机127.0.0.1访问加密功能可用，局域网其他设备http访问加密API失效）：
```bash
python -m http.server 8080
