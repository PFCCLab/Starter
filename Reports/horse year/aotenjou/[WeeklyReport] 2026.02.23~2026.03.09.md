### 姓名

白玉韬

### 本双周工作

1. **PaddleOCR错题本项目**
实现错题库REST API端点：
- GET /api/history: 分页查询历史题目(全部),支持日期范围筛选
- GET /api/search: 关键字/知识点/题型搜索
- GET /api/stats: 知识点统计
- DELETE /api/question/{id}: 删除题目


2. **UI测试场景对比silicon PaddleOCR与官方原生OCR**
- 在 https://excalidraw.com/，https://the-internet.herokuapp.com/，https://jykoh.com/vwa的网页/公式等组件上使用PlayWright组合两种PaddleOCR接口，比较模型效果。

- 重复测试silicon PaddleOCR接口，比较结果是否稳定可复现。

- 测试发现硅基流动PaddleOCR API幻觉率远高于官方原生接口，且效果不稳定，已经向上汇报。

### 未来双周计划

1. 继续探索PaddleOCR在UI自动化测试中的场景。
