# 解决重复代码


1. 首先在函数里面赋值post参数给request
   ```markdown
   request()->withPost(array_merge(input('post.'), ['delete_file_path' => $file_path]));
    ```
   
2. 然后创建后置中间件处理

```markdown
<?php

namespace application\http\middleware;

use Closure;

class After
{
    public function handle($request, Closure $next)
    {
        $response = $next($request);
        $delete_file_path = $request->delete_file_path;
        if (is_file("." . $delete_file_path) && $response->getData()['type'] != 1) {
            unlink("." . $delete_file_path);
        }
        return $response;
    }
}

```

3. 在控制器里面设置仅针对单个方法生效

```markdown

<?php


class App
{
    protected $middleware = ['中间件位置' => ["only" => ['方法名', '方法名']]]
}
```

