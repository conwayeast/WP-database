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

All these tables are important, of course, but if you need to fix or change something directly in the database, chances are that it is in wp_options (for blog settings, like URLs and such), wp_posts (for mass editing of your blog posts), or wp_users (for password resets and such).

## Mass edit posts

Maybe you've got a new domain and want to change the source for all images you've used over the years, from olddomain.com/wp-content/image.jpg to newdomain.com/wp-content/image.jpg. You can run a SQL query to search for all these elements and replace them with the new ones. It could be something like this:

    UPDATE wp_posts SET post_content = REPLACE (
    post_content,
    'olddomain.com/wp-content/',
    'newdomain.com/wp-content/');
  
This code searches the wp_posts table for any mention of olddomain.com/wp-content/ and replaces it with newdomain.com/wp-content/. That in turn fixes all the image links in the example. Nifty little SQL queries for batch editing can come in handy, but remember: There are no undos here - what's done is done - so make sure you've made a backup of the database before even considering doing these things. 

