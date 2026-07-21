## ADDED Requirements

### Requirement: 三类模型 Provider
系统 SHALL 抽象三类模型 provider：多模态 API（必选）、文字 API（可选）、本地 LLM（可选），通过统一接口定义，配置切换。

#### Scenario: 配置多模态 API provider
- **WHEN** 用户在系统设置中配置多模态 API 的 endpoint 和 key
- **THEN** 系统使用该 provider 处理图片/PDF 输入

#### Scenario: 配置文字 API provider
- **WHEN** 用户配置文字 API 的 endpoint 和 key
- **THEN** 系统使用该 provider 处理纯文字输入

#### Scenario: 配置本地 LLM provider
- **WHEN** 用户配置本地 LLM（如 Ollama）的 endpoint
- **THEN** 系统将纯文字输入路由到本地 LLM 处理，不调用云端 API

### Requirement: 多模态 API 为必选依赖
系统 SHALL 将多模态 API 标记为必选依赖，未配置时报告导入功能不可用，但文字咨询功能仍可通过文字 API 或本地 LLM 运行。

#### Scenario: 未配置多模态 API 时报告导入不可用
- **WHEN** 用户未配置多模态 API 就尝试上传报告
- **THEN** 系统提示"报告导入需要配置多模态 API，请前往系统设置配置"

#### Scenario: 未配置多模态 API 时文字咨询可用
- **WHEN** 用户未配置多模态 API 但配置了文字 API 或本地 LLM
- **THEN** AI 咨询、手动录入等纯文字功能正常运行

### Requirement: 本地 LLM 仅兜文字线
系统 SHALL 明确本地 LLM 只能处理纯文字输入，不支持多模态；多模态线必须依赖多模态 API，本地 LLM 无法替代。

#### Scenario: 本地 LLM 不处理图片输入
- **WHEN** 用户配置了本地 LLM 但未配置多模态 API，尝试上传图片报告
- **THEN** 系统提示"图片报告需要多模态 API，本地 LLM 不支持图片处理"

### Requirement: Provider 路由逻辑
系统 SHALL 根据输入类型自动路由到对应 provider：含视觉内容（图片/PDF）路由到多模态 API；纯文字内容路由到文字 API 或本地 LLM（按用户配置优先级）。

#### Scenario: 视觉输入路由多模态
- **WHEN** 输入包含图片或 PDF
- **THEN** 系统路由到多模态 API provider，不受文字 provider 配置影响

#### Scenario: 文字输入按配置路由
- **WHEN** 输入为纯文字且同时配置了文字 API 和本地 LLM
- **THEN** 系统按用户配置的优先级选择 provider 处理
