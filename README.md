## Menu routes for WordPress REST API v2

**This is a fork of [nekojiras wp-api-menus](https://github.com/nekojira/wp-api-menus) plugin which worked with legacy versions of the WP REST API (v1.2 and earlier).**

**This fork works with the most up to date version of the WP REST API (v2)**

[WordPress](http://www.wordpress.org/) plugin that extends the JSON REST [WP API](https://github.com/WP-API/WP-API) with new routes pointing to WordPress registered menus. Read the [WP API documentation](http://wp-api.org/).

#### New routes available:

- `/menus` list of every registered menu.
- `/menu/<id>` data for a specific menu.
- `/menu-locations` list of all registered theme locations.
- `/menu-location/<location>` data for menu in specified menu in theme location. 

Currently, the `menu-locatios/<location>` route for individual menus will return a tree with full menu hierarchy, with correct menu item order and listing children for each menu item. The `menu/<id>` route will output menu details and a flat array of menu items. Item order or if each item has a parent will be indicated in each item attributes, but this route won't output items as a tree. 

#### Examples

The URL's you hit to retreive data will be as follows:
**`/menus`:**
http://www.Example.com/wp-json/wp-api-menus/v1/menus
**`/menu/<id>`:**
http://www.Example.com/wp-json/wp-api-menus/v1/menu/<id>
**`/menu-locations`:**
http://www.Example.com/wp-json/wp-api-menus/v1/menu-locations
**`/menu-location/<location>`:**
http://www.Example.com/wp-json/wp-api-menus/v1/menu-location/<location>

#### Sample Response

##### `/menus` Endpoint:

The following is an example of the returned json data, when the `/menus` endpoint is hit:

`
[
  {
    "term_id": "4",
    "name": "Main Nav",
    "slug": "main-nav",
    "term_group": "0",
    "term_taxonomy_id": "4",
    "taxonomy": "nav_menu",
    "description": "",
    "parent": "0",
    "count": "2",
    "ID": "4",
    "meta": {
      "links": {
        "collection": "http://www.Example.com/wp-reaction/wp-json/menus/",
        "self": "http://www.Example.com/wp-json/menus/4"
      }
    }
  }
]
`
#### `/menu/<id>` Endpoint:

The following is an example of returned json data when the `/menu/<id>` endpoint is hit:

`
{
  "ID": 4,
  "name": "Main Nav",
  "slug": "main-nav",
  "description": "",
  "count": 2,
  "items": [
    {
      "ID": 74,
      "order": 1,
      "parent": 0,
      "title": "Sample Page",
      "url": "http://www.Example.com/sample-page/",
      "attr": "",
      "target": "",
      "classes": "",
      "xfn": "",
      "description": "",
      "object_id": 2,
      "object": "page",
      "type": "post_type",
      "type_label": "Page"
    },
    {
      "ID": 76,
      "order": 2,
      "parent": 0,
      "title": "Google",
      "url": "http://www.google.com",
      "attr": "",
      "target": "",
      "classes": "",
      "xfn": "",
      "description": "",
      "object_id": 76,
      "object": "custom",
      "type": "custom",
      "type_label": "Custom Link"
    }
  ],
  "meta": {
    "links": {
      "collection": "http://www.Example.com/wp-json/menus/",
      "self": "http://www.Example.com/wp-json/menus/4"
    }
  }
}
`

#### Contributing

* Submit a pull request or open a ticket here on Github. 