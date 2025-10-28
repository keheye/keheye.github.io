# RubyGems 国内镜像源配置

## 问题
bundle install 在国外的 rubygems.org 下载速度很慢或卡住

## 解决方案

### 方案 1: Ruby China 镜像 (推荐,最快)

```bash
# 1. 更换 gem 源
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/

# 2. 验证源
gem sources -l

# 3. 修改 Gemfile 第一行
# source 'https://rubygems.org'
# 改为:
# source 'https://gems.ruby-china.com'

# 4. 清理并重新安装
rm -rf .bundle vendor Gemfile.lock
bundle config set --local path 'vendor/bundle'
bundle install
```

### 方案 2: 清华大学镜像

```bash
# 1. 更换 gem 源
gem sources --add https://mirrors.tuna.tsinghua.edu.cn/rubygems/ --remove https://rubygems.org/

# 2. 配置 bundle
bundle config mirror.https://rubygems.org https://mirrors.tuna.tsinghua.edu.cn/rubygems

# 3. 修改 Gemfile
source 'https://mirrors.tuna.tsinghua.edu.cn/rubygems'

# 4. 安装
bundle install
```

### 方案 3: 阿里云镜像

```bash
gem sources --add https://mirrors.aliyun.com/rubygems/ --remove https://rubygems.org/
```

## 当前配置状态

已配置为使用 **Ruby China** 镜像源 (https://gems.ruby-china.com)

Gemfile 已修改为:
```ruby
source 'https://gems.ruby-china.com'
```

## 安装步骤

```bash
cd /home/agiuser/Application/keheye.github.io

# 清理旧配置
rm -rf .bundle vendor Gemfile.lock

# 配置本地安装路径
bundle config set --local path 'vendor/bundle'

# 安装依赖 (使用国内镜像)
bundle install

# 启动服务器
bundle exec jekyll serve
```

## 验证镜像源

```bash
# 查看当前 gem 源
gem sources -l

# 应该显示:
# *** CURRENT SOURCES ***
# https://gems.ruby-china.com/

# 查看 bundle 配置
bundle config list
```

## 如果还是慢

可以尝试设置 HTTP 代理:
```bash
export http_proxy=http://your-proxy:port
export https_proxy=http://your-proxy:port
bundle install
```

## 注意事项

- `vendor/bundle` 目录包含所有依赖,已添加到 .gitignore
- Gemfile.lock 会在首次安装时生成
- 如果遇到权限错误,使用 `bundle config` 设置本地路径而不是 sudo
