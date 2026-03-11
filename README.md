🧾 Interactive 3D Physics Receipt (交互式 3D 物理小票)

一个基于 Three.js 和 Verlet 物理积分 (Verlet Integration) 构建的交互式 3D 网页实验项目。它在浏览器中完美模拟了一张被夹在顶部的热敏纸小票，你可以用鼠标随意抓取、拖拽、揉捏它，体验极具解压感的真实物理形变与回弹。

✨ 想要看效果？ > [点击这里查看在线 Demo] (<!-- 提示：上传到 GitHub Pages 或 Vercel 后，将链接粘贴在这里 -->)

🎮 核心特性 (Features)

🧲 Verlet 物理约束系统：纯手写弹簧-质点（Mass-Spring）模型，包含结构约束（Structural）、剪切约束（Shear）和弯曲约束（Bending），完美还原纸张的柔韧度，防止过度拉伸。

📌 顶边绝对固定：顶部的所有顶点采用 反质量(invMass) = 0 的绝对约束，表现出像被票夹死死夹住的效果，拒绝劣质的“晾衣绳”式中心下垂。

💨 热敏纸物理特性：加入了基于深度坐标的非线性向内卷曲力，以及随时间变化的微风扰动，让小票在静止时也能保持自然的呼吸感和纸张特有的卷曲态。

🖱️ 光线追踪交互：使用 THREE.Raycaster 进行精准的鼠标拾取。抓取时，该点质量无限大并跟随鼠标移动，松手后约束系统会自动将其弹回。

🖨️ Canvas 动态纹理生成：小票表面的文字并非静态图片，而是利用 Canvas 2D API 动态绘制的高清贴图，自带条形码生成和极简的排版系统。

🚀 快速开始 (Getting Started)

本项目无需复杂的构建工具（Webpack/Vite 等），开箱即用：

克隆本仓库到本地：

git clone [https://github.com/你的用户名/你的仓库名.git](https://github.com/你的用户名/你的仓库名.git)


由于使用了 ES6 Module (type="module") 来引入 Three.js，直接双击打开 HTML 文件可能会被浏览器的跨域策略（CORS）拦截。

推荐运行方式：

使用 VS Code 的 Live Server 插件，右键点击 receipt.html 选择 "Open with Live Server"。

或使用 Python 快速启动本地服务：

python -m http.server 8000


然后在浏览器访问 http://localhost:8000/receipt.html。

🛠️ 自定义你的“恶趣味”清单 (Customization)

厌倦了普通的购物清单？你可以在代码中轻松修改小票的内容，把它变成你的赛博受难地、游戏吐槽板或是任何展现你个人性格的媒介。

找到代码中的 createReceiptTexture() 函数，修改以下部分即可：

// 修改超市名称
ctx.fillText('你的恶趣味超市名字', 256, y);

// 修改商品清单与价格
drawItem('1x 修复不了的 Bug', '无价');
drawItem('3x 掉光的头发', 'OUT OF STOCK');


📂 文件结构 (Project Structure)

📦 3d-physics-receipt
 ┣ 📜 receipt.html   # 核心入口文件（包含所有的 HTML/CSS/JS 与物理逻辑）
 ┣ 📜 README.md      # 项目说明文档
 ┗ 📜 LICENSE        # 开源协议


🤝 贡献与感谢 (Credits)

3D 渲染引擎使用 Three.js (通过 CDN 引入，版本 r160)。

物理引擎部分参考了传统的 Verlet 积分算法与布料模拟（Cloth Simulation）理论。

如果你觉得这个小项目很有趣，欢迎给个 ⭐️ Star！如果你有更多好玩的物理模拟想法，也欢迎提交 Pull Request 或者 Issue 一起交流！

📄 开源协议 (License)

本项目基于 MIT License 开源，你可以自由地学习、修改和用于个人/商业项目。
