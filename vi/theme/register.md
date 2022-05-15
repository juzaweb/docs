At the root of each theme, there is always a `register.json` file. In this file you can add what is needed for your theme.

### Register js and css your theme
You can add js or css to your theme very simple. Add or edit your `register.json` file, Accept `path/to/yourtheme/assets/path` or url remote file. E.x
```json
{
    // Your code
    "styles": {
        "js": [
            "assets/js/main.js"
        ],
        "css": [
            "https://fonts.googleapis.com/css2?family=Montserrat:ital",
            "assets/css/main.css"
        ]
    },
    // Your code
}
```

### Register nav menu
Add nav menu location in your theme. Add or edit your `register.json` file
```json
{
    // Your code
    "nav_menus": {
        "primary": {
            "label": "Primary menu"
        }
    },
    // Your code
}
```
And `Admin -> Menu`, You can choose `location` for your menu

### Register sidebar
Sidebar được đề cập đến một khu vực sẵn sàng cho tiện ích được các Theme sử dụng để hiển thị thông tin không phải là một phần của nội dung chính. Nó không phải lúc nào cũng là một cột dọc ở bên. Nó có thể là một hình chữ nhật nằm ngang bên dưới hoặc phía trên vùng nội dung, chân trang, đầu trang hoặc bất kỳ vị trí nào trong Theme.

Việc sử dụng các Sidebar khác nhau và tùy thuộc vào lựa chọn của người thiết kế Theme. Các Theme hỗ trợ nhiều Sidebar còn được gọi là các khu vực sẵn sàng cho tiện ích.

#### Add sidebar vào Theme
- Add or edit your `register.json` file
```json
{
    // Your code
    "sidebars": {
        "sidebar": {
            "label": "Sidebar"
        }
    },
    // Your code
}
```
- Bây giờ, bạn có thể vào `Admin -> Widgets` đã xuất hiện block `Sidebar` trên cột phía bên phải màn hình.
#### Hiển thị sidebar trên Theme
- Bạn có thể sử dụng hàm `dynamic_sidebar` để gọi Sidebar vào vị trí bạn muốn hiển thị Sidebar
- Ex:
```twig
<div class="sticky-top">
    {{ dynamic_sidebar('sidebar') }}
</div>
```

### Register `widgets`
#### Add `widgets`
- Add or edit your `register.json` file
```json
{
    // Your code
    "widgets": {
        "banner": {
            "label": "Banner",
            "description": "Banner sidebar",
            "view": "theme::widgets.banner.show"
        },
        "popular": {
            "label": "Popular",
            "description": "Popular posts",
            "view": "theme::widgets.popular.show"
        }
    },
    // Your code
}
```
#### Thêm `widgets` vào `sidebars`
- Để thêm `widgets` vào `sidebars` bạn vào `Admin -> Appearance -> Widgets` chọn và nhấn `Add Widget` từ cột bên trái, `widgets` sẽ được thêm vào các `sidebars` tương ứng ở cột bên phải

### Register page templates
- Add or edit your `register.json` file
```json
{
    // Your code
    "templates": {
        "home": {
            "label": "Home",
            "view": "theme::templates.home"
        }
    },
    // Your code
}
```
- Đoạn code trên add một template có key `home`, bạn có thể nhìn thấy nó trong `Admin -> Page -> Edit/Create Form -> Template`. `theme::templates.home` chính là view hiển thị nội dung page. Để hiển thị nội dung template, hãy xem thêm ở mục [Custom Page](custom-page)

### Register page block
`Page Block` giống với `widgets` nhưng nó có thể được tùy chỉnh ở các page cụ thể nếu page đó có sự dụng `Page Block` content

#### Add Page Block
- Add or edit your `register.json` file
```json
{
    // Your code
    "blocks": {
        "popular_news": {
            "label": "Popular news",
            "description": "Popular news",
            "view": "theme::widgets.popular_news.show"
        }
    },
    // Your code
}
```
- Đoạn code trên add một `Page Block` có key là `popular_news`, `theme::widgets.popular_news.show` chính là view hiển thị của block này trên Theme.
#### Sử dụng Page Block trong template
- Để sự Page Block trong template, bạn cần đăng ký các blocks trong phần đăng ký template của mình.
```json
{
    // Your code
    "templates": {
        "home": {
            "label": "Home",
            "view": "theme::templates.home", // View template
            "blocks": { // Define blocks for template
                "content": {
                    "label": "Content"
                }
            }
        }
    },
    // Your code
}
```
- `content` chính là block người dùng có thể thêm các block con khi tạo/chỉnh sửa các page có template `home`

See more document for page templates: 

### Full file demo theme register

```json
{
    "styles": {
        "js": [
            "assets/js/main.js"
        ],
        "css": [
            "https://fonts.googleapis.com/css2?family=Montserrat:ital",
            "assets/css/main.css"
        ]
    },
    "templates": {
        "home": {
            "label": "Home",
            "view": "theme::templates.home",
            "blocks": {
                "content": {
                    "label": "Content"
                }
            }
        },
        "support": {
            "label": "Support",
            "view": "theme::templates.support"
        }
    },
    "nav_menus": {
        "primary": {
            "label": "Primary menu"
        }
    },
    "sidebars": {
        "sidebar": {
            "label": "Sidebar"
        },
        "footer_column": {
            "label": "Footer"
        }
    },
    "widgets": {
        "banner": {
            "label": "Banner",
            "description": "Banner sidebar",
            "view": "theme::widgets.banner.show"
        },
        "popular": {
            "label": "Popular",
            "description": "Popular posts",
            "view": "theme::widgets.popular.show"
        }
    },
    "blocks": {
        "news_slider": {
            "label": "Post slider",
            "description": "Posts slider carousel",
            "view": "theme::widgets.news_slider.show"
        },
        "popular_news": {
            "label": "Popular news",
            "description": "Popular news",
            "view": "theme::widgets.popular_news.show"
        }
    }
}
```