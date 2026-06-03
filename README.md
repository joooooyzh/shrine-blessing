# 摇签祈福

一个像素风「摇签祈福」应用，包含手机端 H5 预览和 M5Stack StickS3 硬件固件。

当前版本风格参考《星露谷物语》《开罗游戏》《动物森友会》：温暖米色纸张、日式神社、寺庙卡片 Carousel、像素风签文桶、摇动出签动画。

## 本地预览

直接打开 `index.html` 即可，也可以用任意静态服务器托管整个文件夹。

```bash
npm install
npm run dev
```

## 部署到静态托管

把这些文件一起上传即可：

- `index.html`
- `styles.css`
- `app.js`
- `assets/`
- `plugins/`
- `npm-animation.js`

网页首页目前包含 4 个寺庙卡片：

- 浅草寺
- 清水寺
- 明治神宫
- 北海道神宫

浅草寺与京都清水寺签文数据保存在 `assets/asakusa-fortunes.js` 和 `assets/kiyomizu-fortunes.js`，页面可以离线运行。

## StickS3 硬件版本

硬件固件在 `firmware/sticks3`。它面向 M5Stack StickS3 / M5StickC Plus2 小屏幕、IMU 和实体按键设计：

- 左右摇动 StickS3 抽签
- 按键出签、翻页、返回首页
- 内置签文数据，离线运行，不需要 Wi-Fi
- 像素风签文桶、签号、吉凶、签诗和分项解读

### 烧录到 StickS3

```bash
cd firmware/sticks3
chmod +x quick_upload.sh
./quick_upload.sh
```

第一次安装依赖或上传失败时，可以使用：

```bash
cd firmware/sticks3
chmod +x install_upload.sh
./install_upload.sh
```

如果 macOS 阻止访问串口，请在终端里运行上传命令，并确认设备已经连接到 `/dev/cu.usbmod101` 或脚本提示的可用串口。

## GitHub 上传建议

本仓库已经配置 `.gitignore`，不会把安装缓存、虚拟环境、PlatformIO 编译目录和 `node_modules` 上传到 GitHub。

创建 GitHub 仓库后，在本地运行：

```bash
git remote add origin git@github.com:你的用户名/你的仓库名.git
git push -u origin main
```
