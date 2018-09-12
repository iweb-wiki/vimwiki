# Composer 命令

## install

`composer install`

如有 composer.lock 文件，直接安装，否则从 composer.json 安装最新扩展包和依赖

## require 

`composer require vendor/package` 

添加安装 vendor/package, 可以指定版本

## update

`composer update` 

更新所有依赖，从 composer.json 安装最新扩展包和依赖

`composer update vendor/package`

更新指定的包，从 composer.json 或者对应包的配置，并更新到最新

## remove

`composer remove vendor/package`

移除一个包及其依赖

## search

`composer search package`

进行包的搜索 

> 如果只是想匹配名称可以使用 `--only-name` 选项

## show

`composer show`

列出所有已经安装的包

`composer show vendor/*`

可以通过通配符进行筛选

`composer show vendor/package`

显示具体某个包的信息