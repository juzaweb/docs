### Query data from view

- **get_posts(type, options = {})**
    - Get post type list data
    - `@param string $type` : Post type
    - `@param  array $options`
    -  `paginate` : Row per page if you would like paginate
    -  `taxonomies` : Filter by taxonomies
    -  `taxonomy` : Filter by taxonomy
    -  `limit` : Limit posts
    -  `metas` : Filter by meta
    -  `order_by` : Order by. Default id DESC
    - `@return array`
- **get_post_taxonomy()**
- **get_post_taxonomies()**
- **get_related_posts()**
- **get_post_resource()**
- **get_post_resources()**
- **get_previous_post()**
- **get_popular_posts()**

