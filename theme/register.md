

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
            "label": "Footer column"
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