# Odoo 说明文档（中文）

## 文档构建

### 环境依赖

- [Git](https://git-scm.com/install)
- [Python 3.10 to 3.14](https://www.python.org/downloads/).
- Make
- `requirements.txt`中列明的Python依赖（详见下文说明）
- 一份从[odoo/odoo](https://github.com/odoo/odoo)官方仓库下载的代码（可选）
- 一份从[odoo/upgrade-util](https://github.com/odoo/upgrade-util)官方仓库下载的代码
  （可选）

### 快速开始

1. 创建并激活一个虚拟环境。
   - Linux 和 macOS 运行：`python3 -m venv .venv && source .venv/bin/activate`
   - Windows（Powershell）运行：`py3 -m venv .venv; .\.venv\Scripts\Activate.ps1`
2. 安装Python依赖：`pip install -r requirements.txt`
3. 构建文档：`make html` (see more commands with `make help`)
4. 在浏览器中打开 `documentation/_build/html/index.html` 

### 其他构建命令

- `make fast` 构建浅层菜单（更快）。
- `make clean` 清除构建时产生的文件。 
- `make test` 运行测试指引/指南。
- `make html CURRENT_LANG=fr` 指定仅构建法文文档。
- `make html CURRENT_LANG=fr LANGUAGES=en,fr,de` 构建法文文档并开启
  语言切换开关，支持切换为LANGUAGES中列明的语言选项。每个你想构建的CURRENT_LANG都必须要调用该命令。
- `make html VERSIONS=17.0,18.0,saas-18.4,19.0,master` 构建文档的**当前版本**并启用语言切换开关，
  支持VERSIONS中指明的版本。每一个想构建的VERSIONS版本都要调用该命令。

在`conf.py`中可以找到支持的构建语言列表，具体在`languages_names`变量部分。

当构建一个指定语言类型和版本的文档时，构建生成的文件会位于
`documentation/_build/html/<language>/`，`documentation/_build/html<verison>/` 或
`documentation/_build/html/<version>/<language>/`目录中。

### 使用Odoo本地源码

如果你本地有`odoo/odoo` 和/或 `odoo/upgrade-util`的检出版，请将他们放在：
- 与本项目相同的目录里（在父目录），或
- 放在`documentation`目录中

当这些路径存在时，如果那些仓库的版本与文档版本匹配，他们的Python文档字符串将纳入构建构成。

### 问题排查

- 检查你的Python版本：`python3 --version` 必须为 3.10-3.14
- 确保你的虚拟环境已激活，且已安装相关依赖
- 如果你改变了文件的结构，在构建之前请运行`make clean`命令以清除缓存
- 如果语言或语言切换开关指向了一个不存在的文件，请检查确认你已经构建了所有支持的对应的语言和版本
- “Developer”文档文档仅支持英文

## 文档贡献
## Contribute to the documentation

关于文档内容贡献，请查阅
[Introduction Guide](https://www.odoo.com/documentation/latest/contributing/documentation.html).

提报文档问题，请求新内容，或提问，使用
[issue tracker](https://github.com/odoo/documentation/issues).
