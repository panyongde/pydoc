# 字符串连接

两种方式，一个是用 `.` 来连接，一个是使用大括号 `{}` ，大括号代码看起来更干净，记得用双引号（“”）而不是单引号（‘’）来包起字符串，因为在单引号（''），你会得到所提供的变量litaral名称。

```php
<?php

  $a = '12345';

  // This works:
  echo "qwe{$a}rty"; // qwe12345rty, using braces
  echo "qwe" . $a . "rty"; // qwe12345rty, concatenation used

  // Does not work:
  echo 'qwe{$a}rty'; // qwe{$a}rty, single quotes are not parsed
  echo "qwe$arty"; // qwe, because $a became $arty, which is undefined

?>
```