# pytest 使用

```bash
pip install pytest coverage
```

- 测试代码位于 `tests` 文件夹中
- 单元测试模块都以 `test_` 开头
- 测试函数都以 `test_` 开头
- 测试配置文件为 `setup.cfg`

```properties
[tool:pytest]
testpaths = tests

[coverage:run]
branch = True
source = src
```

```bash
pytest
pytest -v
```

```bash
coverage run -m pytest
coverage report
```
