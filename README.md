

![PNSTYLE_23png](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/15f9ebaf-b205-4cbd-928e-eca1a0cacb7f)


# ComfyUI PhotoMaker

Unofficial implementation of [PhotoMaker](https://github.com/TencentARC/PhotoMaker) for ComfyUI

<!---
![Dingtalk_20240117150313](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/da664c2b-cb30-44e2-85ec-d6070fcfa8f0)


![Dingtalk_20240117161736](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/07c924ab-3ee5-4919-87bc-ac49c28914f1)
--->
![Dingtalk_20240118163802](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/0292bf55-21b7-4025-bc27-7e3e7ccc2af3)

<!---
![Dingtalk_20240118163953](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/9b8a665f-6c9c-441c-aa81-fc56423de89e)
--->

单张参考与多张参考的对比：

![Dingtalk_20240117201650](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/e7bccd61-7855-46c2-a6bc-31b34e742927)

![Dingtalk_20240117201201](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/6bbcfcf9-9027-4c6f-9be1-750971b7848c)


## 项目介绍 | Info

- 来自对[PhotoMaker](https://github.com/TencentARC/PhotoMaker)的非官方实现
  
- 版本：V2.0 节点拆分 + 支持本地模型 + 支持自定义尺寸 +提速3倍


## 视频演示

<!---
https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/8718a70e-a5d7-463b-b36e-de1ffefad9ed
--->



https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/d58af6e7-d0f3-41ff-ab33-195cb6d66e9e



## 节点说明 | Features

- 基础模型加载 | base model loader
    - 📷Base Model Loader from hub🤗：支持从 huggingface hub 自动下载模型，输入模型名称（如：SG161222/RealVisXL_V3.0）即可
    - 📷Base Model Loader locally：支持加载本地模型（需 SDXL 系列模型）

- PhotoMaker Adapter 模型加载 | PhotoMaker Adapter Loader
    - 📷PhotoMaker Adapter Loader from hub🤗：支持从 huggingface hub 自动下载模型
    - 📷PhotoMaker Adapter Loader locally：支持加载本地模型，输入 photomaker-v1.bin 模型所在路径即可

- 参考图预处理 | 📷Ref Image Preprocessing
    - 单图模式 | Single：接入单张图像（非必要项）
    - 多图模式 | Multiple：自动读取路径中的所有图像

- PhotoMaker 生成 | 📷PhotoMaker Generation
    - pipe：接入模型
    - pil_image：接入预处理图像
    - ptompt、negative：正负提示词
    - style_name：支持官方提供的10种风格
        - (No style)
        - Cinematic
        - Disney Charactor
        - Digital Art
        - Photographic (Default)
        - Fantasy art
        - Neonpunk
        - Enhance
        - Comic book
        - Lowpoly
        - Line art
    - style_strength_ratio：风格混合强度（高于30按30计算）
    - step：步数，官方默认50步，但毕竟是基于SDXL模型，我实测下来30步足够了
    - guidance_scale：提示词相关度，一般默认为5
    - seed：种子
    - width、height：尺寸设置（需1024维度）

<!---
- base_model_path：支持输入huggingface模型名称自动下载模型（如：SG161222/RealVisXL_V3.0）
- ref_images_path：支持批量读取参考图像，放入文件夹中即可
- ptompt、negative：正负提示词
- style_name：支持官方提供的10种风格
    - (No style)
    - Cinematic
    - Disney Charactor
    - Digital Art
    - Photographic (Default)
    - Fantasy art
    - Neonpunk
    - Enhance
    - Comic book
    - Lowpoly
    - Line art 
- style_strength_ratio：风格混合强度（高于30按30计算）
- step：步数，官方默认50步，但毕竟是基于SDXL模型，我实测下来30步足够了
- guidance_scale：提示词相关度，一般默认为5
- seed：种子
--->

## 风格 | Styles

![PNSTYLE_2](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/dc675478-47a0-456d-946b-0cf781aa4c28)


## 安装 | Install

<!---
- 推荐使用管理器 ComfyUI Manager 安装
--->

- 手动安装：
    1. `cd custom_nodes`
    2. `git clone https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker.git`
    3. `cd custom_nodes/ComfyUI-PhotoMaker`
    4. `pip install -r requirements.txt`
    5. 重启 ComfyUI


## 工作流 | Workflows

- [V2.0 本地模型 locally](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/blob/main/PhotoMaker%20Workflows/PhotoMaker_locally%E3%80%90Zho%E3%80%91.json)

  ![QQ截图20240118163432](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/bf6a55ae-767e-4aaf-9f75-6f752bb5b530)

  
- [V2.0 自动下载 huggingface hub](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/blob/main/PhotoMaker%20Workflows/PhotoMaker_fromhub%E3%80%90Zho%E3%80%91.json) 

  ![QQ截图20240118163252](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/f645c1b7-2548-45fc-b388-0ebe62e2724d)


## 更新日志

- 20240118

  更新为 V2.0：节点拆分 + 支持本地模型 + 支持自定义尺寸 +提速3倍

  新增本地、hub加载工作流

- 20240117

  新增单张图输入，并给出对比图

  修复bug，初版上线

- 20240116

  创建项目


## 速度实测 | Speed

- V2.0 提速 3 倍

    - A100 50步 7s

    ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/4ae13ffc-c770-4551-bcb2-ce0b0ddc1367)

- V1.5

    - A100 50步 23s

    ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/df6eacda-2640-425b-b5ca-1ab5a8a61a66)

    - v100 50步 90s

    ![image](https://github.com/ZHO-ZHO-ZHO/ComfyUI-PhotoMaker/assets/140084057/973b8b6b-9195-4044-b75d-bd833bd6421e)


## Stars 

[![Star History Chart](https://api.star-history.com/svg?repos=ZHO-ZHO-ZHO/ComfyUI-PhotoMaker&type=Date)](https://star-history.com/#ZHO-ZHO-ZHO/ComfyUI-PhotoMaker&Date)



## Credits

感谢[@erLin](https://twitter.com/eviljer)对ComfyUI 的图像张量 Shape (N, H, W, C)的提醒，帮助我成功修复了bug！

[PhotoMaker](https://github.com/TencentARC/PhotoMaker)
