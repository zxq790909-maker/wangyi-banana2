# WangYi Banana - OPENCLAW Skill

武镜画家（短剧制作机）的 OPENCLAW SKILLS 版本，支持图片和视频生成。

## 📥 安装技能

1. 打开 [ClawHub](https://clawhub.ai/)
2. 搜索并安装 **wangyi-banana2** 技能
3. 安装成功后，会弹出**模型列表**，说明安装成功 ✅

## 📝 注册与配置（不会配置？按下面来）

### 第一步：注册账号并获取 API Key

1. **打开链接注册**：[https://ai.t8star.cn/register?aff=253d8a45349](https://ai.t8star.cn/register?aff=253d8a45349)
2. **添加令牌**：点击左侧「令牌」→「添加令牌」（名字随便写，其它默认）→ 提交
3. **充值算力**：点击左侧「钱包」→ 充值算力（汇率约 5 刀=6.75 RMB，最低 5 刀起充）
4. **复制 API Key**

### 第二步：在 OPENCLAW 中配置

回到 OPENCLAW，发送以下指令：（强烈建议在发送前先备份 openclaw.json以防不测）

> 对小龙虾说：帮我配置好，根据龙虾提示，进行下一步的操作，发的指令必须加上”注意是在 openclaw.json 添加，不可覆盖或删除原来里面的配置参数“

等待一会儿，配置就完成了。

**赶紧生一张图片试试吧！** 🎨

有了这个 SKILLS，把 QQ 或飞书接入 OPENCLAW，就可以随时随地调用贞贞工坊的 API 来生成图片和视频啦～ ComfyUI 暂时可以下岗了！

---

如果配置正确，打开openclaw.json，在最后会显示：

   }
  },
  "skills": {
    "entries": {
      "wangyi-banana": {
        "apiKey": "XXXXXXXXXXXXXXXXXXXXXX"
      }
    }
  }
}


## 📖 使用示例

### 生成图片

```powershell
python3 scripts\wangyi-banana.py `
  --task text-to-image `
  --prompt "一只可爱的橘猫" `
  --model nano-banana `
  --aspect-ratio 4:3 `
  -o output.png
```

### 生成视频

```powershell
python3 scripts\wangyi-banana.py `
  --task text-to-video `
  --prompt "一只猫在窗台上走动" `
  --model sora-2 `
  --duration 10 `
  --aspect-ratio 16:9 `
  -o output.mp4
```

## 📚 更多文档

- [API Key 设置指南](references/api-key-setup.md)
- [图片生成指南](references/image-generation.md)
- [视频生成指南](references/video-generation.md)
- [输出交付指南](references/output-delivery.md)

## 🔧 支持的功能

- ✅ 文生图（Text-to-Image）
- ✅ 图生图（Image-to-Image）
- ✅ 文生视频（Text-to-Video）
- ✅ 图生视频（Image-to-Video）
- ✅ 角色创建（Character Creation）

## 📝 支持的模型

### 图片模型
- `nano-banana` - banana1 直接返图（单次 0.08）：文生图/图生图/多图参考；参考图支持 b64/URL/data:image/*
- `nano-banana-hd` - banana1 直接返图（单次 0.12）：文生图/图生图/多图参考；参考图支持 b64/URL/data:image/*
- `nano-banana-edit` - banana1 图生图编辑（单次 0.08）：图生图/多图参考；直接返图
- `nano-banana-2` - BANANA2 直返图（文生图/图生图编辑，费用 0.2）
- `nano-banana-2-2K` - BANANA2 2K 直返图（文生图/图生图编辑，费用 0.2）
- `nano-banana-2-4k` - BANANA2 4K 直返图（文生图/图生图编辑，费用 0.2）
- `nano-banana-pro` - BANANA2 Pro 直返图（文生图/图生图编辑，费用 0.2）
- `gemini-2.5-flash-image` - Gemini 2.5 Flash 绘图模型（费用 0.04）
- `gemini-2.5-flash-image-preview` - Gemini 2.5 Flash 预览版（费用 0.04）
- `gemini-3.1-flash-image-preview` - Gemini 3.1 Flash 图片预览（费用 0.1）
- `gemini-3.1-flash-image-preview-2k` - Gemini 3.1 Flash 2K 图片预览（费用 0.1）
- `gemini-3.1-flash-image-preview-4k` - Gemini 3.1 Flash 4K 图片预览（费用 0.1）

> `gemini-2.5-flash-image*` 适用于文生图与图编辑，支持多张参考图（最多 14 张），参考图可用路径/URL/b64/data URI；通常先返回链接（脚本会自动下载），单张费用约 0.04。
> `gemini-3.1-flash-image-preview*` 可用于文生图与图编辑，支持多图组合（最多 14 张）。
> 与直接 BANANA2 相比：预览版通常先返回链接（脚本会自动下载），单张费用约 0.1；直接 BANANA2 常可直接返图，单张费用约 0.2。

### 视频模型
- `sora-2` - 标准版本（10s, 15s；按次计费单次 0.1）；更准确、更逼真、更可控；支持对话/音效（在提示词里写要求即可）
- `grok-video-3` - 15s/次（费用 0.5）

## 🌐 API 地址

脚本会自动尝试以下备份地址：
1. https://ai.t8star.cn（主地址）
2. http://104.194.8.112:9088（备份1）
3. https://hk-api.gptbest.vip（备份2）
4. https://api.gptbest.vip（备份3）

## 📞 获取 API Key

前往 [贞贞的AI工坊](https://ai.t8star.cn/register?aff=253d8a45349) 注册并充值即可获取 API Key。详见上方「注册与配置」步骤。
