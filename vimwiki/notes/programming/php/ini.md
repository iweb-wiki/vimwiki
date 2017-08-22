# PHP - 错误报告

## 开发环境

```ini
display_errors = On
display_startup_errors = On
error_reporting = -1
log_errors = On
```

**不同 PHP 版本下开启全部错误显示**

- < 5.3 `-1` 或 `E_ALL`
- 5.3 `-1` 或 `E_ALL | E_STRICT`
- \> 5.3 `-1` 或 `E_ALL`

## 生产环境

```ini
display_errors = Off
display_startup_errors = Off
error_reporting = E_ALL
log_errors = On
```
# PHP - 上传设置

```php
upload_max_filesize = 2G;
post_max_size = 2000M;
memory_limit = 1024M;
max_execution_time = 120;
```