# Install GeoLocation Nominatim Module

site url: https://www.drupal.org/project/geolocation_nominatim

The GeoLocation Nominatim Module has a patch that should be applied. Also, it seems to leverage the leaflet-control-geocoder javascript library (https://github.com/perliedman/leaflet-control-geocoder).

1. Install using composer: ```composer require drupal/geolocation_nominatim```
  - It will also automatically installed the required dependencies such as leaflet and geolocation modules. 
  
2. Apply the patch **add_more_option-2820891-2.patch** here: https://www.drupal.org/node/2820891#comment-11742599
  - in your terminal navigate inside the geolocation_nominatum module directory and run this command: ```patch -p1 < add_more_option-2820891-2.patch```
  - rebuild your cache by ssh'ing (```lando ssh```) and running this Drush command: ```drush cache-rebuild```
  
3. Download https://github.com/perliedman/leaflet-control-geocoder/releases/tag/v1.5.1 (https://github.com/perliedman/leaflet-control-geocoder/releases/tag/v1.5.1) and extract the download to /web/libraries/leaflet-control-geocoder/
  - create a libraries directory if it does not already exist
  - if the extracted library is named something like leaflet-control-geocoder-1.5.1, don't forget to rename the directory to leaflet-control-geocoder
  
4. Using your browser, in the Drupal site go to the extend menu and add the leaflet, geolocation, geofield and geolocation nominatim modules. Then go to the Structure menu, add new a content type and add the geolocation field. Then manage the fields, and add a new field as a geolocation type. Then manage the form display, and change the widget to the Geolocation nominatum widget and now you can also adjust settings. Finally, you can add your content to your site.
