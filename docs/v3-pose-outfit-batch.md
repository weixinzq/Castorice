# 遐蝶 V3 多姿势与换装出图

本次在 RTX 3080 Ti 与 ComfyUI 0.42.0 上生成并校验了 96 张 832 × 1216 的 PNG。首轮 52 张，补跑 44 张，最终交付 52 张。

## 出图矩阵

- 原服、休闲卫衣、校园制服各覆盖 8 种视角或动作，每组各用种子 42 和 2026。
- 深色晚礼服和冬季风衣各生成两个种子的正面站姿。
- `summary_poses_default.png` 展示原服的 8 种动作，`summary_outfits_comparison.png` 使用同一正面构图和种子 42 比较 5 套服装。

## 复现参数

使用 Hassaku XL v3 WIP（Illustrious）。ComfyUI 日志确认了 `model_type EPS`。角色 LoRA 使用 V3 的 1,200 步版本，触发词为 `cstriceHSR`。[Hassaku XL 模型文件](https://modelscope.cn/models/ModelE/Hassaku-XL/files) · [Castorice V3 Release](https://github.com/weixinzq/Castorice/releases/tag/v3-noobai-xl)

使用 Euler a、normal 调度、26 步和 CFG 6。V3 权重只包含 U-Net 参数，工作流用 `LoraLoaderModelOnly` 加载。原服强度为 0.75，换装首轮为 0.68，辨识度补跑为 0.73，同时加入浅紫长发、尖耳和紫瞳提示。

## 验收

换装补跑改善了发色和服装一致性，并对晚礼服颜色、雪景、制服手势和伸手构图做了补充。姿势以提示词控制，回眸幅度、镜头内的手指和五官细节随种子变化。

`run_report.json` 记录全部生成尝试、最终入选图对应的 API 参数以及模型和成图的 SHA‑256。单图尺寸和内嵌工作流逐张核对，交付压缩包通过完整性校验。
