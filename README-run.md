本地搭建 Jekyll 环境
1.安装 Ruby
访问RubyInstaller 官网，下载
https://rubyinstaller.org/downloads/
2.安装 RubyGems
RubyGems 是 Ruby 的包管理器，一般在安装 Ruby 时会一并安装，可以打开命令提示符（CMD），输入gem -v ，如果能显示出版本号，说明安装成功。
3.安装 Jekyll
gem install jekyll
4.安装项目依赖
bundle install
5.启动 Jekyll 服务
bundle exec jekyll serve

【3、4这样分工清晰，既保证系统有 Jekyll 基础能力，又让每个项目的依赖独立可控，完全不冲突 。】
类比理解：

gem install jekyll ≈ 给电脑装 “浏览器”（基础工具）
bundle install ≈ 给浏览器装 “插件”（项目专属功能）

# 查看当前镜像源
gem sources

#切换源
(base) PS C:\Users\xy> gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/

# 移除有问题的清华镜像源（如果存在）
gem sources --remove https://mirrors.tuna.tsinghua.edu.cn/rubygems/

# 添加 Ruby China 镜像源（国内常用，较稳定）
gem sources --add https://gems.ruby-china.com/

# 确保只保留一个镜像源（避免冲突）
gem sources --clear-all
gem sources --add https://gems.ruby-china.com/

# 清除 Bundler 缓存
bundle clean --force

# 重新安装依赖（会使用新配置的镜像源）
bundle install

#启动服务 
bundle exec jekyll serve

#关闭代理和防火墙（Windows 常见问题）