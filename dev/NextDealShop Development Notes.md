# 添加功能组件
比如添加carbon组件，可使用下面命令：

    ./develop.sh composer require carbon
    
这种方式添加组件会自动修改 composer.json 文件

# 自动加载文件
比如在创建 utils/helpers.php，让系统自动加载，这个时候要修改 composer.json 文件：

```
	"autoload": {
	        "psr-4": {
	            "App\\": "app/"
	        },
	        "files": [
	            "app/utils/helpers.php"
	        ]
	    },
```

然后在 composer.json 所在的文件夹运行命令：

    composer dump-auto

# 添加中间件 Middleware

1. 创建Middleware中间件文件，比如formatInputKeyMiddleware.php

```
<?php

namespace App\Http\Middleware;

use Closure;

class formatInputKeyMiddleware
{
    /**
     * Handle an incoming request.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  \Closure  $next
     * @return mixed
     */
    public function handle($request, Closure $next)
    {
    	//这里写入中间件操作逻辑
        return $next($request);
    }
}
```
2. 修改 bootstrap/app.php，加入新建的中间件，一个中间件类对应一个别名

```
$app->routeMiddleware([
    'auth' => App\Http\Middleware\Authenticate::class,
    'formatinput' => App\Http\Middleware\ formatInputKeyMiddleware::class,
]);
```

3. 在 routes.php 使用中间件

```
$app->group([
    'prefix' => 'api/v1',
    'middleware' => [
      	'auth',
      	'formatinput',
    ]
], function($app)
{
    $app->get('/ideas', 'IdeaController@index');
}
```
    
# 数据库开发
### 创建数据表
1. 进入应用程序目录

        cd /Users/panyongde/Documents/nextdealshop/profiteer
   
2. 生成表格迁移
        
        ./develop.sh art make:migration create_ideas_table
        
    然后编写表格的迁移结构

3. 运行迁移

        ../develop.sh art migrate
       
4. 修改表格的迁移结构

   先对表格迁移结构的文件进行修改，然后运行：
   
        ./develop.sh art migrate:refresh
       
### 对表格填充数据
1. 编写填充器

        ./develop.sh art make:seeder UserTableSeeder
       
2. 填充数据

        ./develop.sh art db:seed
       
       