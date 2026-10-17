# 银器手艺人的 AI 工具箱

> 白刚（BlaineGale）· 湘西苗寨银器 · 从业 20 年
> 所有项目的 star 数为 2026-10-16 通过 GitHub API 实时核实，非记忆值。

## 一、图像生成 —— 出银器成品效果图的核心

| 项目 | Star | 语言 | 为什么对银器有用 |
|---|---|---|---|
| [ComfyUI](https://github.com/Comfy-Org/ComfyUI) | 137,630 | Python | 节点式工作流，可精确控制纹样生成。银器打样图批量出图的首选 |
| [ControlNet](https://github.com/lllyasviel/ControlNet) | 34,124 | Python | 用线稿图约束生成，保证「线稿和实物纹样逐笔对应」 |
| [InvokeAI](https://github.com/invoke-ai/InvokeAI) | 28,648 | TypeScript | 专业级 WebUI，局部重绘和扩图好用，适合改细节 |
| [sd-webui-controlnet](https://github.com/Mikubill/sd-webui-controlnet) | 17,825 | Python | A1111 的 ControlNet 扩展，本地跑 SD 必备 |
| [Fooocus](https://github.com/lllyasviel/Fooocus) | 53,413 | Python | 提示词直出，界面极简，适合快速试纹样方案 |
| [ComfyUI-Manager](https://github.com/Comfy-Org/ComfyUI-Manager) | 16,461 | Python | ComfyUI 的插件管理器，装节点不用手动拷文件 |

**建议路径**：ComfyUI + ControlNet 组合。先用线稿当控制图，再生成实物效果图——这正好对应本仓库 Skill 里「上栏线稿 + 下栏效果图」的双栏逻辑。

## 二、短视频 —— 抖音小红书种草

### 2.1 自动成片（轻量、云端、AI 初学者友好）

| 项目 | Star | 语言 | 为什么有用 |
|---|---|---|---|
| [MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | 131,102 | Python | 输入主题自动出高清短视频，中文项目，配音字幕全流程 |
| [ShortGPT](https://github.com/RayVentura/ShortGPT) | 8,030 | Python | You Shorts/TikTok 自动化的早期经典，思路值得抄 |

**建议路径**：先用本仓库的 `blainegale-video-studio` Skill 出分镜和文案，再把画面素材喂给 MoneyPrinterTurbo 合成。

### 2.2 文本生成视频（开源大模型，需独显）

> 以下为「输入提示词直接出视频」的开源扩散模型，质量高但极吃显卡。本机无独显无法本地跑，需配 **RTX 4090 级显卡（24GB）** 或租 **A100（约 $1-4/小时）**。

| 项目 | Star | 许可 | 最低显存 | 适用性 |
|---|---|---|---|---|
| [Wan2.2](https://github.com/Wan-Video/Wan2.2) | 17,943 | Apache 2.0（可商用） | TI2V-5B 约 12-24GB | 质量最佳，文/图生视频+视频编辑三合一 |
| [LTX-Video](https://github.com/Lightricks/LTX-Video) | 11,106 | Apache 2.0 | 8-12GB | 低显存、速度快，质量略逊 |
| [HunyuanVideo-1.5](https://github.com/Tencent-Hunyuan/HunyuanVideo-1.5) | 4,570 | 社区许可（商用需读条款） | 14GB | 动作流畅，许可有约束 |

**Wan2.2 安装与调用**（需 RTX 4090 级显卡 / 或租 A100）：

```bash
# 1. 环境：Python 3.10+、CUDA 12.x、PyTorch 2.x
git clone https://github.com/Wan-Video/Wan2.2.git
cd Wan2.2 && pip install -r requirements.txt
# 2. 下载权重（HuggingFace: Wan-AI/Wan2.2-TI2V-5B-Diffusers）
# 3. 文生视频调用
python generate.py --task ti2v-5B --prompt "提示词" --size 720*1280 --frame_num 81
```

**建议路径**：没有独显时直接用本仓库内置视频生成即可；要批量/可控出片再上 Wan2.2 本地部署。

## 三、自动化 —— 无人值守跑流程

| 项目 | Star | 语言 | 为什么有用 |
|---|---|---|---|
| [n8n](https://github.com/n8n-io/n8n) | 207,438 | TypeScript | 可视化工作流自动化，400+ 集成。定时发小红书、拉行情数据都能串 |
| [n8n-mcp](https://github.com/czlonkowski/n8n-mcp) | 23,076 | TypeScript | 让 AI 直接帮你搭 n8n 工作流，不用自己拖节点 |
| [awesome-n8n-templates](https://github.com/enescingoz/awesome-n8n-templates) | 25,939 | - | 280+ 免费模板，含社媒、Notion、OpenAI 类 |
| [Zie619/n8n-workflows](https://github.com/Zie619/n8n-workflows) | 56,974 | Python | 社区工作流合集，抄改最快 |

## 四、资料与文档

| 项目 | Star | 语言 | 为什么有用 |
|---|---|---|---|
| [Stirling-PDF](https://github.com/Stirling-Tools/Stirling-PDF) | 94,241 | TypeScript | 自托管 PDF 工具箱，图纸合同票据都能处理，不外传 |
| [Karakeep](https://github.com/karakeep-app/karakeep) | 29,664 | TypeScript | 自托管书签+ AI 自动标签，收藏的纹样素材和行业情报可检索 |
| [awesome-selfhosted](https://github.com/awesome-selfhosted/awesome-selfhosted) | 326,787 | - | 大量可自托管服务的总目录，想搭本地工具时从这里找 |

## 五、按场景选型

| 我要做的事 | 用什么 |
|---|---|
| 手镯纹样出图，线稿和实物要对得上 | ComfyUI + ControlNet |
| 快速试几个纹样方案 | Fooocus |
| 改图细节、扩背景 | InvokeAI |
| 抖音带货视频 | video-studio Skill + MoneyPrinterTurbo |
| 输入提示词直接生成特写短视频 | 内置视频生成（无独显）；Wan2.2 本地部署（有独显） |
| 小红书图文自动发布 | n8n + awesome-n8n-templates |
| 查贵金属行情、定时盯盘推送 | n8n 定时任务 + 数据源 |
| 整理纹样素材库 | Karakeep |

## 六、门槛提示

本地跑 SD/ComfyUI / 文本生成视频模型需要**独显**（建议 8GB 显存以上，文本生成视频建议 24GB）。没有独显就直接用云端接口，出图质量一样，Skill 本来就走这条路。

## License

MIT
