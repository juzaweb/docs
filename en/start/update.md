### Update CMS

#### Update in browser
Go to **Admin -> Dashboard -> Updates** to Update CMS

#### Update with command

Run command
```
php artisan juzacms:update
```

#### Common problems
- Server timeout: Edit timeout in your server, Cloudflare DNS (if use) and try again.
- Service provider not found: Run command `composer dump-autoload` and try again.
