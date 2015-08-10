# Wp-database
# Learning the WordPress database

Full database description documentation: https://codex.wordpress.org/Database_Description

## The 11 Main Tables
* wp_commentmeta: Metadata for comments
* wp_comments: Contains all comments
* wp_links: Contains added links and link data
* wp_options: The blog options
* wp_postmeta: Metadata for posts
* wp_posts: The actual posts
* wp_terms: Categories and tags
* wp_term_relationships: Associates categories and tags with posts
* wp_term_taxonomy: Descriptions for categories and tags
* wp_usermeta: User metadata
* wp_users: The actual users

All these tables are important, of course, but if you need to fix or change something directly in the database, chances are that it is in wp_options(for blog settings, like URLs and such), wp_posts (for mass editing of your blog posts), or wp_users (for password resets and such).
