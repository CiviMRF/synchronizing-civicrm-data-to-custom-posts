# Synchronizing CiviCRM data to Custom Posts

Provides an tool for synchronizing CiviCRM data to custom posts in Wordpress. 
You can use this plugin with [Connector to CiviCRM with CiviMcRestFace plugin](https://wordpress.org/plugins/connector-civicrm-mcrestface/)
which gives you the ability to connect to an CiviCRM installation on a different server.

## Funded by

* [Article 19](https://www.article19.org/)

# Reporting bugs

Bugs can be reported at [Github](https://github.com/CiviMRF/synchronizing-civicrm-data-to-custom-posts).

# Contributing

The code of this plugin is published and maintained at [Github](https://github.com/CiviMRF/synchronizing-civicrm-data-to-custom-posts).
The plugin is also published at [Wordpress.org](https://wordpress.org/plugins/synchronizing-civicrm-data-to-custom-posts) (**NOT YET**)
and this requires that we submit each release to the [Wordpress SVN](https://plugins.svn.wordpress.org/synchronizing-civicrm-data-to-custom-posts)

**Workflow for development**

1. Fork the repository at Github
1. Create a new branch for the functionality you want to develop, or for the bug you want to fix.
1. Write your code and test it, once you are finished push it to your fork.
1. Create a Pull Request at Github to notify us to merge your changes.

**Workflow for creating a release**

Based on the instruction from [Learn with Daniel](https://learnwithdaniel.com/2019/09/publishing-your-first-wordpress-plugin-with-git-and-svn/)

1. Update `readme.txt` with the new version number (also update the Changelog section)
1. Update `synchronizing-civicrm-data-to-custom-posts.php` with the new version number
1. Create a new version at [Github](https://github.com/CiviMRF/synchronizing-civicrm-data-to-custom-posts).
1. To publish the release at Wordpress Plugin directory follow the following steps:
    1. Create a temp directory: `mkdir synchronizing-civicrm-data-to-custom-posts-tmp`
    1. Go into this directory: `cd synchronizing-civicrm-data-to-custom-posts-tmp`
    1. Do an SVN checkout into SVN directory: `svn checkout --depth immediates https://plugins.svn.wordpress.org/synchronizing-civicrm-data-to-custom-posts svn`
    1. Clone the Github repository into Github directory: `git clone https://github.com/CiviMRF/synchronizing-civicrm-data-to-custom-posts.git github`
    1. Go into the Github directory: `cd github`
    1. Checkout the created release (in our example 1.0.0): `git checkout 1.0.0`
    1. Go into the svn directory: `cd ../svn`
    1. Copy the files from github to SVN: `rsync -rc --exclude-from="../github/.distignore" "../github/" trunk/ --delete --delete-excluded`
    1. Add the files to SVN: `svn add . --force`
    1. Tag the release in SVN (in our example 1.0.0): `svn cp "trunk" "tags/1.0.0"`
    1. Now submit to the Wordpress SVN with a message: `svn ci -m 'Adding 1.0.0'`


# License

The plugin is licensed under [AGPL-3.0](LICENSE.txt).