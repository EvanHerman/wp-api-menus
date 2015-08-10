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


#### Contributing

* Submit a pull request or open a ticket here on Github. 