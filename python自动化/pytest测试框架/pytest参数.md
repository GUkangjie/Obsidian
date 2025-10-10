**常见组合命令：**

| 场景     | 命令                                                 | 说明                         |
| ------ | -------------------------------------------------- | -------------------------- |
| 最常见调试  | pytest -s -v                                       | 详细输出 + 显示 print            |
| 运行指定文件 | pytest test_xx.py -v                               | 指定文件运行                     |
| 按关键字运行 | pytest -k "login" -v                               | 模糊匹配测试名                    |
| 按标记运行  | pytest -m "smoke" -v                               | 执行带 @pytest.mark.smoke 的用例 |
| 生成报告   | pytest -v --html=report.html --self-contained-html | 生成独立 HTML 报告               |
| 并行运行   | pytest -n auto -v                                  | 多核加速执行                     |
| 失败重试   | pytest --reruns 2                                  | 失败自动重试两次                   |

**pytest 常用命令行参数汇总：**

| **分类**      | **参数**                                      | **含义**                              | **示例**                                      |
| ----------- | ------------------------------------------- | ----------------------------------- | ------------------------------------------- |
| **基础输出**    | -v                                          | 显示更详细的信息（verbose）                   | pytest -v                                   |
|             | -q                                          | 简化输出（quiet）                         | pytest -q                                   |
|             | -s                                          | 显示 print 输出（不捕获输出）                  | pytest -s                                   |
|             | --tb=short                                  | 简化 traceback 显示                     | pytest --tb=short                           |
| **控制执行范围**  | -k "关键字"                                    | 按函数名或类名筛选执行                         | pytest -k "login"                           |
|             | -m "标记名"                                    | 按 @pytest.mark 标记执行                 | pytest -m "smoke"                           |
|             | --maxfail=n                                 | 遇到 n 个失败后停止                         | pytest --maxfail=2                          |
|             | -x                                          | 第一个失败就停止执行                          | pytest -x                                   |
|             | --lf / --last-failed                        | 只执行上次失败的用例                          | pytest --lf                                 |
|             | --ff                                        | 优先执行上次失败的用例                         | pytest --ff                                 |
| **报告与日志**   | --html=report.html                          | 生成 HTML 报告（需 pytest-html 插件）        | pytest --html=report.html                   |
|             | --junitxml=report.xml                       | 生成 JUnit XML 报告                     | pytest --junitxml=report.xml                |
|             | --result-log=log.txt                        | 记录执行日志（旧版支持）                        | pytest --result-log=log.txt                 |
| **性能与并行**   | -n 4                                        | 并行运行 4 个进程（需 pytest-xdist）          | pytest -n 4                                 |
|             | -n auto                                     | 自动分配核数并行运行                          | pytest -n auto                              |
|             | --durations=10                              | 显示最慢的 10 个用例                        | pytest --durations=10                       |
| **过滤警告与错误** | --disable-warnings                          | 隐藏警告信息                              | pytest --disable-warnings                   |
|             | --maxfail=1 -q                              | 遇到一个失败就停止（调试常用）                     | pytest --maxfail=1 -q                       |
| **调试和重试**   | --pdb                                       | 失败时进入交互式调试                          | pytest --pdb                                |
|             | --reruns n                                  | 失败重跑 n 次（需 pytest-rerunfailures 插件） | pytest --reruns 2                           |
| **运行路径**    | pytest tests/                               | 运行 tests 目录下所有用例                    | pytest tests/                               |
|             | pytest test_login.py                        | 运行指定文件                              | pytest test_login.py                        |
|             | pytest test_login.py::TestLogin::test_case1 | 精确运行某个类或方法                          | pytest test_login.py::TestLogin::test_case1 |
