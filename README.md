# Geospatial_Posts
A feature to define areas for sending posts

### Skill set Needed: Moderate or expert Drupal 8 and Drupal 7 developers that have experience with Drupal modules and PHP. This feature will be prioritized to be built on Drupal 8.

### Getting Involved

#### Environment
* Any basic vanilla Drupal 8 environment is acceptable for development. Look at guide here if you need help: https://github.com/hopeonesource/geospatial_posts/blob/master/setting_up_Drupal8_locally.md

* Guide on how to install and run the Geocoder Nominatum Module (https://www.drupal.org/project/geolocation_nominatim): https://github.com/hopeonesource/geospatial_posts/blob/master/install_geolocation_nominatim_module.md

### Why do we need Geospatial Search and Querying capabilities?
1.	Allowing HopeOneSource to scale. HopeOneSource will expand to different regions while retaining a single Drupal instance. Therefore we will need to have geospatial querying capabilities to limit posts being sent and received to selected regions in addition to just the distance based limits we place on sent posts. Users in the system will either have the capability to select regions based on searching for them (based on Nominatim search) and/or selecting pre-defined regions (such as using GADM).
2.	This added functionality will also be part of one of the requirements when building our regional data dashboards, enabling metrics through an API per region, therefore limiting the amount of data being sent to the dashboard and speeding up load times. 

### UI updates related to this User Story:
1.	Minimum Viable Product (MVP): When providers send posts, they will have the option of who will receive posts based on all posts within x region (based on returned polygon on Nominatim search). There will also be a map that shows where the post will be sent. Future development: users will also have additional options to send messages 1) within user-defined polygon 3) or x distance away. 
2.	Future development: More architectural planning is needed...Clients will be able to adjust through their settings, the areas in which they will receive posts: 1) all posts within x region 2) within user-defined polygon 3) or x distance away

### Basic system components:
- UI modifications will be modified on select pages on HopeOneSource. The new Map Module will have to be integrated with Drupal 8.
  - This has started being developed and includes the following 2 repos: 1) https://github.com/d3netxer/geolocation_nominatim 2) https://github.com/d3netxer/leaflet-control-geocoder
- PostGIS database will be set up on AWS that will contain client lat/lon points
- Drupal code in Drupal will process the form and send select PostGIS spatial queries to remote PostGIS database on AWS and be able to receive back results.


### Detailed implementation plan link:
https://docs.google.com/document/d/1HMQ2J9ikfK7IR1aI4ef6alnWBPNncKgik5iK3SJ8lPo/edit#

### Doc outlining potential Drupal Modules to integrate
https://docs.google.com/document/d/1zcPsljPYsGa6f9JvfJ9B2c6Y3lzTl04do2RBhmsbyVo/edit


## FAQs

### Are we developing for both Drupal 7 and 8?
yes, the plan would be to develop 2 versions of the feature, with anything that is common between the two be located in a common module.

### Is there an overall system diagram?
https://docs.google.com/presentation/d/19ySapxChDHorljTLOP4pI5nmlQfstlNOHCR0pHGQeBk/edit?usp=sharing 

### What do the providers and clients see in the system?
providers making posts: https://www.youtube.com/watch?v=5qKlJFEQJlI

clients registering: https://www.youtube.com/watch?v=FJwb6KX30G0 

### How is user location stored at present?
We store lat/long of 1.) every client registered (person experiencing homelessness), and from 2.) every service provider's post (available service such as food and legal assistance).

### Any tips for local development?
The project is hosted on Pantheon. Developers have used Kalabox in the past, but the new generation of it is Lando, which is the main tool we use locally now.
