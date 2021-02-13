# Jekyll

> Jekyll 是一个将纯文本内容转化为静态网站或博客的工具。

## Ruby

> Jekyll 要求 Ruby > 2.4.0。由于 macOS Mojave 10.14 仅附带 ruby 2.3.x，因此您必须安装较新版本的 Ruby。

* 安装

```bash
brew install ruby

```
* 检查 ruby 版本

```bash
which ruby
# /usr/local/opt/ruby/bin/ruby

ruby -v
# ruby 3.0.0p0 (2020-12-25 revision 95aff21468) [x86_64-darwin20]
```

* 配置环境变量

`vim ~/.zshrc`

```vim
# ruby
export PATH=$HOME/.local/share/gem/ruby/3.0.0/bin:$PATH
export PATH="/usr/local/opt/ruby/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/ruby/lib"
export CPPFLAGS="-I/usr/local/opt/ruby/include"
# openssl
export PATH="/usr/local/opt/openssl/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/openssl/lib"
export CPPFLAGS="-I/usr/local/opt/openssl/include"
# readline
export LDFLAGS="-L/usr/local/opt/readline/lib"
export CPPFLAGS="-I/usr/local/opt/readline/include"
# libffi
export LDFLAGS="-L/usr/local/opt/libffi/lib" 
export PKG_CONFIG_PATH="/usr/local/opt/libffi/lib/pkgconfig"
```

`source .zshrc`

## Jekyll

* 安装

```bash
gem install --user-install bundler jekyll
```

* 要检查您的gem路径指向您的主目录运行：

```bash
gem env
```

* 并检查`GEM PATHS:`指向主目录中的路径

## 配置 Jekyll

* 安装插件

```bash
bundle install 
```

* 运行 jekyll

```bash
bundle exec jekyll build
bundle exec jekyll server
```