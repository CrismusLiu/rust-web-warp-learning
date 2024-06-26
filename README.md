# Rust Web With Warp Project Learning

## 环境设置

### 安装 Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### 安装 VSCode 插件

- crates: Rust 包管理
- Even Better TOML: TOML 文件支持
- Better Comments: 优化注释显示
- Error Lens: 错误提示优化
- GitLens: Git 增强
- Github Copilot: 代码提示
- indent-rainbow: 缩进显示优化
- Prettier - Code formatter: 代码格式化
- REST client: REST API 调试
- rust-analyzer: Rust 语言支持
- Rust Test lens: Rust 测试支持
- Rust Test Explorer: Rust 测试概览
- TODO Highlight: TODO 高亮
- vscode-icons: 图标优化
- YAML: YAML 文件支持

### 安装 cargo generate

cargo generate 是一个用于生成项目模板的工具。它可以使用已有的 github repo 作为模版生成新的项目。

```bash
cargo install cargo-generate
```

在我们的课程中，新的项目会使用 `tyr-rust-bootcamp/template` 模版生成基本的代码：

```bash
cargo generate tyr-rust-bootcamp/template
```

### 安装 pre-commit

pre-commit 是一个代码检查工具，可以在提交代码前进行代码检查。

```bash
pipx install pre-commit
```

安装成功后运行 `pre-commit install` 即可。

### 安装 Cargo deny

Cargo deny 是一个 Cargo 插件，可以用于检查依赖的安全性。

```bash
cargo install --locked cargo-deny
```

### 安装 typos

typos 是一个拼写检查工具。

```bash
cargo install typos-cli
```

### 安装 git cliff

git cliff 是一个生成 changelog 的工具。

```bash
cargo install git-cliff

# 初始化，创建cliff.toml
git-cliff --init

# 生成 changelog
git-cliff

# 使用 git --tag 命令时生成 changelog
git tag -a v0.1.0
```

### 安装 cargo nextest

cargo nextest 是一个 Rust 增强测试工具。

```bash
cargo install cargo-nextest --locked
```


### 注意

- 项目根目录一定要先执行：`pre-commit install`
- 修改配置文件 [cliff.toml] 49 行的 replace 改为当前项目地址
- 修改配置文件 [deny.toml] 设置如下
```
[advisories]
# The path where the advisory databases are cloned/fetched into
db-path = "$CARGO_HOME/advisory-dbs"
# The url(s) of the advisory databases to use
db-urls = ["https://github.com/rustsec/advisory-db"]

[licenses]
# List of explicitly allowed licenses
# See https://spdx.org/licenses/ for list of possible licenses
# [possible values: any SPDX 3.11 short identifier (+ optional exception)].
allow = [
    # "MIT",
    # "Apache-2.0",
    #"Apache-2.0 WITH LLVM-exception",
    "MIT",
    "Apache-2.0",
    "Unicode-DFS-2016",
    "MPL-2.0",
    "BSD-2-Clause",
    "BSD-3-Clause",
    "ISC",
    "CC0-1.0",
]
```
- 添加 .rustfmt.toml 文件，统一代码格式
- 执行示例命令：`cargo run --example [example name]`


### sqlx-mysql

[Rust & Actix Web – Build a CRUD API with SQLX and MySQL](https://codevoweb.com/rust-actix-web-build-crud-api-with-sqlx-and-mysql/)

[源码](https://github.com/wpcodevo/rust-mysql-crud-sqlx/tree/master)
