# Naikai-WJYD-project
南开大学本科生创新科研计划—国家级大学生创新训练计划：“问津有道——基于天津市非物质文化遗产的数字人交互平台”

# 🏮 天津非遗数字人交互系统 · Tianjin Heritage Avatar

> 一个融合非遗文化与AI数字人的交互式小程序平台  
> 以天津方言、文化导览、语音互动为核心，实现非遗的沉浸式数字化传承  

---

![Banner](./assets/banner.png)

## 📌 项目简介

本项目聚焦**天津市国家/市级非物质文化遗产**，结合生成式大语言模型（LLM）、方言语音合成（TTS）、图像生成（SDXL）、数字人驱动技术（Unity）等手段，打造具备“可对话、可感知、可换脸”的数字人导览交互平台，助力非遗文化在数字时代的**青年传播与地域再表达**。

---

## 🧱 项目架构

```mermaid
graph TD
  subgraph 后端
    A1[PostgreSQL<br>非遗数据库] --> A2[FAISS 向量检索]
    A2 --> A3[LLM 微调模型<br>(Qwen2 + LoRA)]
    A3 --> A4[FastAPI 接口]
    A4 --> B1
    A4 --> B2
    A4 --> B3
  end

  subgraph 云端前端
    B1[/search<br>语义检索]
    B2[/chat<br>知识问答]
    B3[/tts<br>方言语音]
    B4[MinIO 图文视频资源]
  end

  subgraph 用户设备
    C1[微信小程序<br>UniApp]
    C1 --> B1
    C1 --> B2
    C1 --> B3
  end
