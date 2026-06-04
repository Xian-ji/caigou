彩构寻踪
中国古建筑色彩可视化系统

彩构寻踪是一组面向中国传统建筑色彩研究、交互展示与创意转化的可视化工具。项目以苏派、皖派、京派、晋派、闽派等建筑派系为线索，整合建筑色卡、地域分布、词云、图片资料、色彩分析、明信片生成、填色创作与 Unity 结构拆解演示，适合用于课程设计、竞赛展示、数字文保可视化和传统建筑色彩研究汇报。



项目特色
建筑派系色彩看板：展示不同建筑派系的代表色、色彩比例、冷暖关系、色相分布与色彩共现关系。
中国地图交互：通过地图查看建筑派系在省市层面的分布，并联动建筑图片与说明。
词云与图表分析：使用 ECharts、ECharts WordCloud 和 D3.js 呈现建筑色彩语义、色相环、和弦图等可视化内容。
图片采色与档案导出：支持上传建筑图片，批量提取主色，导出 CSV、JSON 和 HTML 报告。
色彩档案再分析：可导入 plot_data.json，进行色彩筛选、AI 推演、报告生成和模块化导出。
文创生成工具：提供古建明信片生成器和建筑色彩填色工具，可导出 PNG 作品。
结构拆解演示：内置 Unity 可执行程序“见筑仪”，用于展示皇家建筑与闽派民居的结构层级、构件说明和色卡联动。
在线/本地入口
文件	功能
index.html	主入口：彩构寻踪中国古建筑色彩可视化系统
采色仪.html	建筑图片色彩分析工作站，支持批量上传、主色提取与数据导出
定析仪.html	古建筑色彩分析仪，导入 JSON 档案后进行图表分析与报告导出
筑色绘衣.html	建筑色彩填色工具，支持派系色卡、调色盘、图片取色和作品保存
筑色绘衣-jing.html	京派主题填色示例版本
古邮映画.html	古建明信片生成器，支持上传图片、提炼色卡和导出正反面明信片
data/彩构寻踪-整合版.html	采色与定析合并的融贯版工作站
data/明信片-移动版.html	移动端明信片生成器
见筑仪/见筑仪.exe	Unity 结构可视化拆解程序，Windows 可运行
技术栈
本项目以静态前端页面为主，无需安装 Node.js 或后端服务。

HTML / CSS / JavaScript
Canvas / Web Worker / FileReader
ECharts 5
ECharts WordCloud
D3.js
Chart.js
html2canvas
阿里云通义千问 / DashScope 兼容接口（部分 AI 功能）
Unity Windows Build（见筑仪 子程序）
目录结构
.
├── index.html                  # 主可视化系统入口
├── 采色仪.html                  # 图片采色与批量分析工具
├── 定析仪.html                  # 色彩档案分析与报告导出工具
├── 筑色绘衣.html                # 建筑色彩填色工具
├── 筑色绘衣-jing.html           # 京派填色示例版本
├── 古邮映画.html                # 古建明信片生成器
├── building_palettes.json      # 建筑色彩调色板数据
├── logo.png                    # 项目 Logo
├── data/
│   ├── schools.json            # 建筑派系与地域分布数据
│   ├── buildings/
│   │   ├── buildings_data.json # 建筑条目、说明与图片索引
│   │   └── buildings_imgaes/   # 建筑图片素材
│   ├── charts/                 # 各派系图表与解读报告 HTML
│   ├── worldcloud/             # 词云数据
│   ├── 彩构寻踪-整合版.html
│   └── 明信片-移动版.html
└── 见筑仪/
    ├── 见筑仪.exe              # Unity 程序入口
    ├── 见筑仪_Data/            # Unity 数据目录
    ├── UnityPlayer.dll
    ├── MonoBleedingEdge/
    └── 见筑仪_README_使用说明.txt
注：data/buildings/buildings_imgaes 目录名中 imgaes 为当前项目实际目录名，引用路径已按该名称配置。

快速开始
方式一：使用 VS Code Live Server
使用 VS Code 打开项目根目录。
安装插件 Live Server。
右键 index.html。
选择 Open with Live Server。
在浏览器中访问页面。
方式二：使用 Python 本地服务器
如果本机已安装 Python，可在项目根目录运行：

python -m http.server 8000
然后在浏览器中打开：

http://localhost:8000/index.html
方式三：直接打开单个 HTML
部分页面可以直接双击打开，例如 采色仪.html、定析仪.html、筑色绘衣.html。但主入口页面需要加载本地 JSON 数据，直接双击可能因为浏览器 CORS 安全策略导致数据加载失败，因此更推荐使用本地 HTTP 服务。

推荐演示流程
打开 index.html，进入“彩构寻踪”主界面。
切换不同建筑派系，查看地图、色卡、词云、图表与建筑图片。
点击建筑条目，查看建筑图片与色彩说明。
打开“采色仪”，上传建筑图片并导出 plot_data.json。
打开“定析仪”，导入 plot_data.json，生成色彩报告和模块图表。
打开“古邮映画”，上传建筑图片，生成正反面古建明信片。
打开“筑色绘衣”，使用建筑派系色卡进行填色创作并保存 PNG。
运行 见筑仪/见筑仪.exe，展示建筑结构拆解、构件讲解与色卡联动。
核心模块说明
1. 彩构寻踪主系统
入口：index.html

主系统用于集中展示中国古建筑色彩数据，包含：

建筑派系选择
代表色卡与比例条
色相环分布
冷暖色分析
色彩共现和弦图
中国地图交互
建筑图片浏览
词云分析
专属解读报告弹窗
AI 问答辅助说明
2. 采色仪
入口：采色仪.html

用于从建筑图片中提取主色并形成结构化分析数据。

主要能力：

多图片上传
K-Means 主色聚类
天空、植被、阴影过滤
建筑传统色优先保留
冷暖色比例、色相区间、明度饱和度等统计图
导出 color.csv
导出 plot_data.json
导出 HTML 汇览报告
导出的 plot_data.json 可继续导入 定析仪.html 做深度分析。

3. 定析仪
入口：定析仪.html

用于对采色结果进行二次分析、筛选和报告生成。

主要能力：

导入 plot_data.json
选择省份与建筑类型
生成 16 色 / 32 色调色板
色相环、冷暖分析、共现和弦图、排行图
单图色彩解构表
AI 自动选色与色彩分析报告
导出完整报告或单个可视化模块
4. 筑色绘衣
入口：筑色绘衣.html

一个面向文创表达的填色工具。

主要能力：

使用建筑派系色卡进行上色
手动调色
上传建筑照片并提取颜色
点击 Canvas 区域填色
保存作品为 PNG
示例素材：



5. 古邮映画
入口：古邮映画.html

古建明信片生成器，用于将建筑照片、色卡与文字信息组合成具有复古纸本质感的明信片。

主要能力：

上传建筑照片
填写建筑题名、地点、年代、题记等信息
自动/手动提炼色卡
生成明信片正面与背面
导出 PNG 图片
6. 见筑仪
入口：见筑仪/见筑仪.exe

见筑仪是基于 Unity 的古建筑结构可视化拆解程序，当前包含皇家建筑与闽派民居两类展示。

主要能力：

建筑选择
动态结构拆解
整体复原
构件点击讲解
构件双击放大
色卡与构件联动
建筑材料、工艺、色彩象征说明
运行时请保持整个 见筑仪 文件夹结构完整，不要只移动或单独运行 .exe 文件。推荐在 Windows、1920×1080 或更高分辨率下演示。

数据文件说明
路径	说明
building_palettes.json	建筑派系与建筑对象的色彩调色板数据
data/schools.json	建筑派系、地域、省市权重与简介
data/buildings/buildings_data.json	建筑案例、图片路径、建筑说明
data/buildings/buildings_imgaes/	建筑图片素材
data/worldcloud/wordcloud_data.json	主系统词云数据
data/worldcloud/wordcloud/*.txt	各建筑派系词云原始文本
data/charts/*.html	各派系图表页
data/charts/fenxi_*.html	各派系解读报告页
GitHub Pages 部署
本项目是静态页面，可以直接部署到 GitHub Pages。

将项目上传到 GitHub 仓库。
进入仓库 Settings。
找到 Pages。
Source 选择 Deploy from a branch。
Branch 选择 main，目录选择 /root。
保存后等待 GitHub Pages 构建完成。
部署后，访问 GitHub Pages 地址即可打开 index.html。

注意事项
主系统依赖本地 JSON 数据，请优先使用本地 HTTP 服务运行。
部分页面依赖 CDN，离线环境下可能无法加载 ECharts、D3、Chart.js、字体或地图数据。
AI 相关功能依赖 DashScope / 通义千问接口，网络不可用或 API Key 无效时会失败。
浏览器出于安全策略限制，直接双击 HTML 时可能无法正常 fetch 本地 JSON。
Unity 程序仅支持 Windows 可执行环境，且必须保留 见筑仪_Data、UnityPlayer.dll、MonoBleedingEdge 等文件。
发布前安全检查
当前项目部分 HTML 中包含前端直写的 API Key。将仓库公开到 GitHub 前，建议务必完成以下处理：

删除或更换所有已暴露的 API Key。
不要在前端代码中直接保存真实密钥。
将 AI 接口改为由后端代理转发，前端只请求自己的服务端接口。
如果密钥曾经提交到公开仓库，请在服务商控制台立即吊销并重新生成。
可在项目根目录搜索：

sk-
API_KEY
QWEN_KEY
DASH_SCOPE_API_KEY
常见问题
1. 页面打开后没有地图或数据
请使用本地服务器运行项目，例如：

python -m http.server 8000
然后访问：

http://localhost:8000/index.html
2. 采色仪或定析仪从主页面跳转后无法上传文件
可以直接打开对应页面：

采色仪.html
定析仪.html
如果仍有问题，请使用 Chrome、Edge 等现代浏览器，并确认页面不是在受限的内嵌浏览器中运行。

3. AI 功能无响应
请检查：

API Key 是否有效
网络是否可以访问 DashScope 接口
浏览器控制台是否有 CORS、401、429 或网络错误
是否已将前端密钥迁移到后端代理
4. Unity 程序无法启动
请检查：

是否在 Windows 环境运行
是否保留完整 见筑仪 文件夹
见筑仪.exe、UnityPlayer.dll、见筑仪_Data/ 是否位于同一目录
是否被系统安全软件拦截
适用场景
中国传统建筑色彩研究
数字文保与文化遗产可视化
课程设计与学科竞赛展示
建筑图像色彩分析
传统色彩文创设计
交互式展陈与演示汇报
许可证
本仓库暂未声明开源许可证。若需要公开发布或供他人复用，建议补充 LICENSE 文件并明确代码、图片、数据与 Unity 构建产物的授权范围。
