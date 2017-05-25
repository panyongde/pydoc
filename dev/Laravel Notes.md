# Dingo

## 安装

执行命令：

    composer require dingo/api:1.0.x@dev
    
对于 Laravel，打开 config/app.php，在 providers 数组中添加服务：

```
'providers' => [
    Dingo\Api\Provider\LaravelServiceProvider::class
]
```

如果你想在配置文件中改变一些配置，你可以使用下面的 Artisan 命令发布配置文件

    php artisan vendor:publish --provider="Dingo\Api\Provider\LaravelServiceProvider"
    
执行的结果为：

    php artisan vendor:publish --provider="Dingo\Api\Provider\LaravelServiceProvider"

    Copied File [/vendor/dingo/api/config/api.php] To [/config/api.php]
    Publishing complete.

遇到坑了，顺便运行一个 Controller 的 Action 都会报错：

> RuntimeException in DingoServiceProvider.php line 82:
> Unable to boot ApiServiceProvider, configure an API domain or prefix.

那是因为 .env 没设置好，在 .env 中加上一行

    API_PREFIX=api
    
搞定，这时候运行正常。

## 配置

**Standards Tree 标准树**

在 .env 文件中，配置 API 标准树，
    API_STANDARDS_TREE=vnd
    
**Subtype 子类型**

你的 subtype 一般是你应用或者项目的简称，全小写。在 .env 文件中

    API_SUBTYPE=myapp
    
**Prefixes and Subdomains 前缀和子域名**   
如果你曾经写过 API，你应该知道大部分的 API 不是有一个子域名就是有一个前缀。一个前缀或者子域名是必要的，但是只能有一个。应避免将版本号作为前缀或者子域名，版本的变更应该由 Accept 头控制。

你可以配置在 .env 文件中。

	API_PREFIX=api
	
或者你可以使用域名

    API_DOMAIN=api.myapp.com
    
**Version 版本**

version 是你 API 的默认版本, 用于某些状况下没有指定版本号的时候。它也用作生成 API 文档的默认版本。

在 .env 中配置

    API_VERSION=v1
    
**Name 名称**

name 只用在你生成文档的时候，当你生成文档的时候用作默认的名字，避免必须去手动定义。在 .env 文件中添加

    API_NAME="My API"
    
其他配置说明，[请参考这里](https://github.com/liyu001989/dingo-api-wiki-zh/blob/master/Configuration.md)。

## 写路由

在 routes/api.php 编写路由，比如：

```
// 接管路由
$api = app('Dingo\Api\Routing\Router');

// 配置api版本和路由
$api->version('v1', [
    'namespace' => 'App\Api\Controllers\v1'
], function ($api) {
    $api->get('test', 'TestController@index');
    $api->get('test/1', 'TestController@show');
});
```
到时候访问的url为

    http://localhost:8000/api/test
    
还以为在 api 后面加上 v1 来访问，其实不是，还没弄明白是什么原因

# 数据库
访问 homestead mysql，配置 .env 文件

    DB_CONNECTION=mysql
	DB_HOST=192.168.10.10
	DB_PORT=3306
	DB_DATABASE=crafttime
	DB_USERNAME=homestead
	DB_PASSWORD=secret
