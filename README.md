# 东磁21700 电池计算器 · PWA 部署指南

## 文件结构
```
battery-pwa/
├── index.html      ← 主程序
├── manifest.json   ← PWA 配置
├── sw.js           ← Service Worker（离线缓存）
├── icons/          ← 应用图标
│   ├── icon-72.png
│   ├── icon-96.png
│   ├── icon-128.png
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

---

## 方法一：GitHub Pages（免费，推荐）

1. 注册/登录 [github.com](https://github.com)
2. 新建仓库，点击 **New repository**，名称随意如 `battery-calc`
3. 上传本文件夹所有文件
4. 进入仓库 **Settings → Pages → Source** 选 `main` 分支，保存
5. 几分钟后访问：`https://你的用户名.github.io/battery-calc/`

### 手机安装 PWA（Chrome）
- Android：打开网址 → 浏览器菜单 → **添加到主屏幕**
- iOS Safari：分享按钮 → **添加到主屏幕**

---

## 方法二：PWABuilder 生成真正的 APK

1. 先完成方法一，获得 HTTPS 网址
2. 访问 [pwabuilder.com](https://www.pwabuilder.com)
3. 输入你的网址，点击 **Start**
4. 选择 **Android → Generate Package**
5. 下载 `.apk` 文件，传到手机安装（需开启"允许未知来源"）

---

## 方法三：本地运行（测试用）

需要一个本地服务器（PWA 不能直接双击打开）：

```bash
# Python 方式
cd battery-pwa
python3 -m http.server 8080
# 浏览器打开 http://localhost:8080
```

---

## 离线功能说明

首次在线访问后，Service Worker 会缓存所有资源。
之后断网也可正常使用，适合户外骑行场景。
