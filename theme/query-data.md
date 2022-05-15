### Query data from view

- **get_posts($type, $options = {})**
    - Get post type list data
    - `@param string $type` : Post type
    - `@param  array $options`
      - `paginate` : Row per page if you would like paginate
      - `taxonomies` : Filter by taxonomies
      - `taxonomy` : Filter by taxonomy
      - `limit` : Limit posts
      - `metas` : Filter by meta
      - `order_by` : Order by. Default id DESC
    - `@return array`
- **get_post_taxonomy($post, $taxonomy = null, $params = [])**
    - Get taxonomy of post
    - `@param array $post` Post data
    - `@param string|null $taxonomy` Taxonomy filter, E.x: categories, tags,...
 
- **get_post_taxonomies($post, $taxonomy = null, $params = [])**
    - Get taxonomies of post
    - `@param array $post` Post data
    - `@param string|null $taxonomy` Taxonomy filter, E.x: categories, tags,...

- **get_related_posts($post, $limit = 5, $taxonomy = null)**

- **get_post_resource($resource, $id)**
  
- **get_post_resources($resource, $options = [])**
  
- **get_previous_post($post): array**
    - `@param array $post` Post data
- **get_popular_posts($type = null, $post = null, $limit = 5, $options = [])**
    - `@param array $type` Post type. E.x: posts, pages
    - `@param array $post` Post except (Skip this post)

