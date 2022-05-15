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
Add or edit your `register.json` file
```json
{
    // Your code
    "sidebars": {
        "sidebar": {
            "label": "Sidebar"
        },
        "footer": {
            "label": "Footer"
        }
    },
    // Your code
}
```

### Register `widgets`
Add or edit your `register.json` file
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

### Register page block
Add or edit your `register.json` file
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

### Register page templates
Add or edit your `register.json` file
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
        },
        "support": {
            "label": "Support",
            "view": "theme::templates.support" // View template
        }
    },
    // Your code
}
```

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