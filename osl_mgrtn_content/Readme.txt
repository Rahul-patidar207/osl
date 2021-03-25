This module uses the Migration csv plugin and import
Article nodes and Authors/users from csv files.

Author and Article CSV files are placed under osl_mgrtn_content/assets/csv
directory, we can update them to import new content on site.

I used Drupal8.9.7 while developing this module, so while testing use the same
version, otherwise we may get some errors in migration import, related to Ids.

Here are some commands to install the module and import the migrations:
  Run below command to install module:
	- drush8 en osl_mgrtn_content -y
  Run below command to import authors:
	- drush8 migrate:import osl_mgrtn_content_authors
  Run below command to import articles:
	- drush8 migrate:import osl_mgrtn_content_articles

For article Author name, and user First name & Last name, I created new fields
and added field config along with migration config in module. So on module install
all these new fields will get created and I also added module dependencies in this
configs so on uninstall these fields will get deleted.

=========================================================================================

NOTE: As we added fields new to the Article and Use account which are created by
Default. So I've not added entity form display config into module, as it will create
problems when we uninstall and re-installation module. So therefore we have to
update the manage Form Display settings for Article and user account and enable them
manually after installing the module.

=========================================================================================
