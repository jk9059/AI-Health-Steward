## 1. V0.1 - 项目骨架与数据地基

- [ ] 1.1 初始化开源项目结构（目录、README、LICENSE、.env.example、docker-compose）
- [ ] 1.2 技术栈选型与脚手架搭建（后端框架、前端框架、数据库选型）
- [ ] 1.3 实现 model-provider 能力：三类 provider 抽象接口与配置切换
- [ ] 1.4 实现 model-provider 能力：多模态 API provider（必选）接入
- [ ] 1.5 实现 model-provider 能力：文字 API provider 与本地 LLM provider 接入
- [ ] 1.6 实现 model-provider 能力：输入类型路由逻辑（视觉->多模态，文字->文字模型）
- [ ] 1.7 实现 health-profile 能力：健康画像数据模型（A-H 字段族建表）
- [ ] 1.8 实现 health-profile 能力：家庭成员 CRUD 与数据隔离
- [ ] 1.9 实现 health-profile 能力：手动录入数据入档（含来源标记）
- [ ] 1.10 实现 channels 能力：WebUI 基础框架（成员管理页、手动录入页、画像展示页）

## 2. V0.2 - AI 咨询能力

- [ ] 2.1 实现 ai-consultation 能力：意图路由器框架
- [ ] 2.2 实现 ai-consultation 能力：工具调用框架（统一工具接口、画像读写工具）
- [ ] 2.3 实现 ai-consultation 能力：指标查询意图与 query_metrics 工具
- [ ] 2.4 实现 ai-consultation 能力：诊断/用药查询意图与 query_profile 工具
- [ ] 2.5 实现 ai-consultation 能力：异常项查询意图与 query_abnormal 工具
- [ ] 2.6 实现 ai-consultation 能力：指标解读意图（参考范围查询+推理）
- [ ] 2.7 实现 ai-consultation 能力：用药咨询意图（含免责声明）
- [ ] 2.8 实现 ai-consultation 能力：症状咨询意图（含免责声明）
- [ ] 2.9 实现 ai-consultation 能力：聊天抽取回填意图与 extract_and_save 工具（含用户确认）
- [ ] 2.10 实现 ai-consultation 能力：角色知识边界约束（超出能力拒绝、兜底回应）
- [ ] 2.11 实现 channels 能力：WebUI 对话界面（完整意图路由与工具调用）

## 3. V0.3 - 报告导入与可视化

- [ ] 3.1 实现 report-ingestion 能力：图片/PDF 上传接口（WebUI + API）
- [ ] 3.2 实现 report-ingestion 能力：多模态结构化抽取（调用多模态 API，输出 JSON）
- [ ] 3.3 实现 report-ingestion 能力：抽取结果用户确认与编辑修正
- [ ] 3.4 实现 report-ingestion 能力：报告姓名识别与归属匹配（默认本人+匹配+手动覆盖）
- [ ] 3.5 实现 health-profile 能力：报告数据入档（含原始文件引用溯源）
- [ ] 3.6 实现 visualization 能力：第一梯队指标趋势图（血压/血糖/血脂/心率/体重BMI）
- [ ] 3.7 实现 visualization 能力：异常项标识（基于参考范围）
- [ ] 3.8 实现 visualization 能力：画像看板（基础信息+指标摘要+异常项+诊断用药）
- [ ] 3.9 实现 health-profile 能力：向量化知识库（原始报告文本+自由摘要，RAG 检索）
- [ ] 3.10 实现 channels 能力：WebUI 报告上传页与可视化看板页

## 4. V0.4 - 飞书渠道

- [ ] 4.1 实现 channels 能力：渠道适配层抽象接口
- [ ] 4.2 实现 channels 能力：飞书 Bot 接入与消息收发
- [ ] 4.3 实现 channels 能力：飞书资料收集（发图->多模态抽取->入档->回复确认）
- [ ] 4.4 实现 channels 能力：飞书报告归属识别（复用 report-ingestion 姓名匹配）
- [ ] 4.5 实现 channels 能力：飞书轻问答（复用 ai-consultation 意图路由，文本回复，不渲染图表）

## 5. V1.0 - 开源发布

- [ ] 5.1 完善部署文档（docker-compose 一键启动、配置说明、飞书 Bot 配置指南）
- [ ] 5.2 编写隐私声明（数据本地存储 vs 模型 API 调用边界、本地 LLM 完全离线方案说明）
- [ ] 5.3 准备示例数据与快速体验流程
- [ ] 5.4 编写开发者文档（二次开发、渠道扩展、provider 扩展）
- [ ] 5.5 项目 README 完善（功能介绍、截图、快速开始、技术栈、贡献指南）
