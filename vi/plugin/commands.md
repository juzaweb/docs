## Commands
- **Make model** Tạo Model cho plugin được chỉ định.
```
php artisan plugin:make-model ModelName author/plugin-name
```
- **Make controller** Tạo Controller cho plugin được chỉ định.
```
php artisan plugin:make-controller ModelName author/plugin-name
```
- **Make resource** Tạo Juza CMS Resource cho plugin được chỉ định.
```
php artisan plugin:make-jw-resource table_name author/plugin-name
```
- **Migrate**: Migrate plugin đã cho hoặc không có đối số plugin Migrate tất cả các plugin
```
php artisan plugin:migrate author/plugin-name
```
- **Migrate rollback**: Khôi phục Migrate plugin đã chạy hoặc không có đối số khôi phục tất cả các plugin.
```
php artisan plugin:migrate-rollback author/plugin-name
```
