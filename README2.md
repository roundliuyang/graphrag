# 启动命令

```bash
cd /Users/xx/graphrag
uv sync --all-packages
uv run --package graphrag graphrag index --root ./ragtest
```

# 测试命令

```bash
# Local：关联查询
uv run --package graphrag graphrag query \
  "星河汽车面临哪些供应链风险？这些风险可能如何影响其客户？请用中文回答。" \
  --root ./ragtest --method local --community-level 0

# Global：全局归纳
uv run --package graphrag graphrag query \
  "这些文档涉及哪些主要业务风险，以及哪些应对措施？请用中文回答。" \
  --root ./ragtest --method global --community-level 0

# Basic：基础向量检索
uv run --package graphrag graphrag query \
  "星河汽车面临哪些供应链风险？这些风险可能如何影响其客户？请用中文回答。" \
  --root ./ragtest --method basic

# DRIFT：探索型查询
uv run --package graphrag graphrag query \
  "分析星河汽车第四季度计划面临的风险，以及可能的应对措施。请用中文回答。" \
  --root ./ragtest --method drift --community-level 0
```
