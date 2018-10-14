# Setting up Drupal 8 locally
Friendly tips on how to run Drupal 8 locally using Lando. Lando let's you run Drupal in a virtual machine in your computer. 

1) Download and Install Lando
  - A prerequisite is installing Docker (Install Docker for your Operating System (https://store.docker.com/search?type=edition&offering=community)
  - Go to Lando installation page (https://docs.devwithlando.io/installation/installing.html), it will direct you to the Lando Github page to download the Lando installation files. Install Lando. After Lando is installed, it is run using commands in your terminal. 

2) Install Composer. Composer is a tool for dependency management in PHP. Composer is a command line tool that can be used to download Drupal, Drupal contributed projects (modules, themes, etc.), and all of their respective dependencies.
  - Download Composer (https://getcomposer.org/download/)
  - Then you can install Composer globally with the following command (https://getcomposer.org/doc/00-intro.md#installation-linux-unix-macos): ```mv composer.phar /usr/local/bin/composer```

3) Download and Install Drupal 8 site
  - recommend you create a new directory in your computer where you will keep your local Drupal sites
  - Download and create a Drupal 8 site with composer: ```composer create-project drupal-composer/drupal-project:8.x-dev my_site_name_dir --stability dev --no-interaction```
  
 4) Start site with Lando
   - Initialize site: ```Lando init```
   - Start site: ```Lando start```
     - The terminal will display the url of the site where you can visit it locally on your web browser
     - When you visit the site, you will finish installing it. These should be the settings to set-up your database: ```Database host: database   Database name:drupal8   username:drupal8   password:drupal8```
   - Other useful commands:
     - SSH into site: ```Lando start```
       - useful for running commands within Drupal, for example the Drush command to clear your cache (```drush cache-rebuild```)
     - Stop site: ```Lando stop```
     - Destroy site: ```Lando destroy```
       - useful if you would like to start completely over with a new site, for example if you messed up adding additional modules. This will destroy the existing database.
