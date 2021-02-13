# MySQL
> MySQL 是最流行的关系型数据库管理系统。

## 安装 MySQL

* 安装 `mysql@5.7`

```bash
brew install mysql@5.7
```

* 配置环境变量

`vim ~/.zshrc`

```vim
# openssl
export PATH="/usr/local/opt/openssl@1.1/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/openssl@1.1/lib"
export CPPFLAGS="-I/usr/local/opt/openssl@1.1/include"

# mysql
export PATH="/usr/local/opt/mysql@5.7/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/mysql@5.7/lib"
export CPPFLAGS="-I/usr/local/opt/mysql@5.7/include"
```

`source .zshrc`

## 启动 MySQL 服务

```bash
brew services start mysql@5.7
```

## MySQL 初始化

```bash
mysql_secure_installation
```

```bash
Securing the MySQL server deployment.

Connecting to MySQL using a blank password.

VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No: n
Please set the password for root here.

New password:

Re-enter new password:
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.

Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
Success.


Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.

Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
Success.

By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.


Remove test database and access to it? (Press y|Y for Yes, any other key for No) :

 ... skipping.
Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.

Reload privilege tables now? (Press y|Y for Yes, any other key for No) :

 ... skipping.
All done!
```

## MySQL 修改密码

* 正常模式

```bash
mysql -u root -p
```

* 安全模式

```bash
mysqld_safe --skip-grant-tables
```

* 修改密码

```bash
UPDATE mysql.user SET authentication_string=PASSWORD('admin') WHERE User='root';
```

* 刷新权限

```bash
FLUSH PRIVILEGES;
```
