### Tauri环境搭建

按照[官方文档](https://tauri.studio/docs/get-started/intro),选择自己的平台搭建，这里以mac为例

**安装命令行工具**

```javascript
xcode-select --install
```

**安装gcc**

```javascript
brew install gcc
```

**安装配置rust环境**

```javascript
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

rust环境配置完成后可以通过查询版本确认安装情况

```javascript
rustc --version
```



### 设置镜像

之前被中科大的镜像给坑了，后面找了很久发现字节跳动的镜像不错

**crates.io Mirror**

在**~/.cargo/config**中输入以下内容

```javascript
[source.crates-io]
replace-with = 'rsproxy'

[source.rsproxy]
registry = "https://rsproxy.cn/crates.io-index"

[registries.rsproxy]
index = "https://rsproxy.cn/crates.io-index"

[net]
git-fetch-with-cli = true
```

**Rustup Mirror**

在**~/.zshrc or ~/.bashrch**中输入以下内容

```javascript
export RUSTUP_DIST_SERVER="https://rsproxy.cn"
export RUSTUP_UPDATE_ROOT="https://rsproxy.cn/rustup"
```

### 模板使用

1. 克隆模板

   ```javascript
   git@github.com:Kerinlin/vue-tauri-template.git
   ```

2. 安装依赖

   ```javascript
   yarn
   ```

3. 运行项目

   ```javascript
   yarn tauri:serve
   ```

4. 打包项目

   ```javascript
   yarn tauri:build
   ```

   
