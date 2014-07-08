---
layout: post
title:  "Drupal 7: Remove database prefixes"
date:   2014-06-19 21:11:00
categories: D7
---

When I started at General Data, I began building the company's new website with Drupal 7, and assumed nothing. Any precaution I could think to take, I took.

One such precaution was how I initialized the database. When you install Drupal, you're asked whether you want to prefix the table names in the database for your site. This is a handy little convenience if you might be using this database for other applications that may or may not want to ignore the Drupal tables therein. If you set your DB prefix to `my_site_`, anytime Drupal creates a table (at installation or otherwise) it'll append `my_site_` to the front of it.

This way, Drupal's tables will look like `my_site_node`, and if another application using the same database needs to create/use a table called `node	`, all is quiet on the western front. Drupal's tables are all namespaced because you chose a prefix. If you chose a prefix that a module you're installing also uses, you've got a problem, but that's another story.

Seems like a legit precaution to take, but I happened to run into a case where my table prefix prevented me from installing something I needed and had to disappear. Nobody wants to rename a bunch of tables manually, so I found a script online that did the trick. Thing was, it was written for Drupal 6, as D7 was still quite youthful at the time.

I tweaked a line or two to get it to work for Drupal 7, and here it is. Credit goes to the [Open Leaf][openleaf] gang for doing the heavy lifting here.

This script is meant to be run via Drush. If you're not familiar with Drush, get there. It's awesome, and it makes me wish every Web framework/CMS came with a robust command line utility.

As always, back up that database before doing anything else.

{% highlight php %}
<?php
  
// current table prefix to be removed
$prefix = "drp";
// echo generated statements rather than run them
$pretend = FALSE;

$table_list = db_query("SHOW TABLES");
$prefix = strtolower($prefix);

//while ($r = db_fetch_array($table_list)) {
while ($r = $table_list->fetchAssoc()) {
  $table_old = strtolower(current($r));
  // check for $prefix on this table
  if(substr($table_old,0,strlen($prefix)) == $prefix) {
    $table_new = substr($table_old, strlen($prefix));
    // first drop $table_new incase it already exists
    $clean_sql = "DROP TABLE IF EXISTS {$table_new}";
    // rename prefix table to standard/nonprefix name
    $rename_sql = "RENAME TABLE {$table_old} TO {$table_new}";

    if($pretend) {
      print $clean_sql."\n";
      print $rename_sql."\n";
    } else {
      if(!db_query($clean_sql)) {
        die("Aborting - $clean_sql \n");
      }
      if(!db_query($rename_sql)) {
        die("Aborting - $rename_sql \n");
      }
    }
  } else {
    print "$table_old skipped \n";
  }
}

print "\nDone \n\n";
?>
{% endhighlight %}

Drop this code into a file, run `drush php-script file_name.php`, remove the $db_prefix from your site's settings.php and clear all caches by running `drush cc all`. Boom. 

It's been a while since I ran this, and things in this industry don't sit still for more than a few days. If you're hitting a wall, just holler. The original post from Open Leaf has more details, but if you're trying to figure this out for Drupal 8 or something, let me know. I'd be happy to work through the problem with you.

[openleaf]: http://openleafstudios.com/blog/remove-database-prefix-existing-drupal-site