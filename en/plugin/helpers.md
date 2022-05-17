### Helper functions
#### 
```php
<?php
$ip = get_client_ip() {}
```
- Get client ip (Support cloudflare dns)

```php
<?php
$config = get_config($key, $default = null) {}
```
- Get database config
  - `string $key` : Config key in database (E.x: `title`)
  - `mixed $default` : Default value if not isset config

```php
<?php
set_config($key, $value) {}
```

- Set database config
- `string $key` : Config key in database (E.x: `title`)
- `string|array|null $value`: Config value

```php
<?php
is_url(string $string): bool {}
```
- Check string is url
  - `string $string` : Url
  - `@return bool`: `true` if string is a url

```php
<?php
function e_html($str): string{}
```
- Esc html (XssCleaner)
    - `string $str` : Html/text/string
    - `@return string`