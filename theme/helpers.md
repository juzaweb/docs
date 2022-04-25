### Helpers

#### Query Data From View
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
- **get_post_taxonomy(post, taxonomy = null, params = [])**
    - Get taxonomy of post
        - `@param array post`
        - `@param string taxonomy`
        - `@param array params`
        - `@return array`
    
- **get_post_taxonomies(post, taxonomy = null, params = [])**
    - Get taxonomy list of post
        - `@param array post`
        - `@param string taxonomy`
        - `@param array params`
            -  parent_id
            -  tree
            -  limit
        - `@return array`

- **get_related_posts(post, limit = 5, taxonomy = null)**
    - Get related posts
        - `@param array post`
        - `@param int limit`
            - Default: 5
        - `@param string taxonomy` : Get by taxonomy
            - Example: categories,tags
            - Default: null
        - `@return array`
    
- **get_post_resource(resource, id)**
    - Get post resource detail
        - `@param string resource`
        - `@param int id`
        - `@return array`

- **get_post_resources(resource, options = [])**
    - Get post resource list
        - `@param string resource`
        - `@param array options`
            - id
            - post_id
            - parent_id
            - limit
                - Default 10
        - `@return array`

- **get_previous_post(post)**
    - Get previous post
        - `@param array post`
        - `@return array`

- **get_popular_posts(type = null, post = null, limit = 5)**
    - Get popular posts
        - `@param string type` : Post type
        - `@param array post` : Post exclude
        - `@param int limit` : Rows limit
        

#### Helper Functions

- **dump(...var)**

- **dd(...var)**

- **__(string text)**
    - Get data translation of text 
        - `@param string text`: Text or key translation
        - `@return string`
        
- **url(string path = '')**
    - Get full url from path
        - `@param string path` (Optional) Return url home page if empty
        - `@return string`
        
- **csrf_token()**
    - Get csrf token
        - `@return string`
        
- **csrf_field()**
    - Get csrf token field
        - `@return string`
        
- **upload_url(string path = '')**
    - Get media full url from path
        - `@param string path`
        - `@return string`

- **paginate_links(data, view = null)**
    - Paginate render
        - `@param data`: Paginate data
        - `@param string view`: View paginate item
- **is_string(var)**
    - Finds whether a variable is an string
        - `@param mixed var`: The variable being evaluated.
        - `@return bool` true if var is an string
- **is_array(var)**
    - Finds whether a variable is an array
        - `@param mixed var`: The variable being evaluated.
        - `@return bool` true if var is an array
- **json_encode(array $array)**
    - Returns the JSON representation of a value
        - `@param mixed $value`: The *value* being encoded. Can be any type except a resource.
        - `@return string|false` a JSON encoded string on success or *FALSE* on failure.
- **md5(str)**
    - Calculate the md5 hash of a string
        - `@param string str`
        - `@return string` the hash as a 32-character hexadecimal number.

- **is_home()**
    - Check current page is home page
        - `@return bool` true if current page is home page

- **dynamic_sidebar(key)**
    - Display dynamic sidebar. By default this displays the default sidebar or ‘sidebar-1’. If your theme specifies the ‘id’ or ‘name’ parameter for its registered sidebars you can pass an ID or name as the $index parameter. Otherwise, you can pass in a numerical index to display the sidebar at that index.
        - `@param (int|string) key` Index, name or ID of dynamic sidebar.
        - `@return \Illuminate\Contracts\View\View`
    
- **dynamic_block(post, key)**
    - Display dynamic page block.
        - `@param $post` Data post
        - `@param (int|string) key` Index, name or ID of dynamic sidebar.
        - `@return \Illuminate\Contracts\View\View|string`
 
- **share_url(social, url, text = null)**
    - Get share url social media
        - `@param string social`
        - `@param string url`
        - `@param string text`
        - `@return string`


