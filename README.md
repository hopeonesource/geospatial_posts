# Geospatial_Posts
define areas for sending posts

### Skill set Needed: Moderate or expert Drupal 8 and Drupal 7 developer that has experience with Drupal modules and PHP. This module will be built with Drupal 8 methods (all of the logic and functionality), and include a plugin in the same module for Drupal 7 to connect with current Drupal 7 sites. All Drupal 8 sites will ignore the module's Drupal 7 plugin Hook.

### Why do we need Geospatial Search and Querying capabilities?
1.	Allowing HopeOneSource to scale. HopeOneSource will expand to different regions while retaining a single Drupal instance. Therefore we will need to have geospatial querying capabilities to limit posts being sent and received to selected regions in addition to just the distance based limits we place on sent posts. Users in the system will either have the capability to select regions based on searching for them (based on Nominatim search) and/or selecting pre-defined regions using GADM.
2.	This added functionality will also be part of one of the requirements when building our regional data dashboards, enabling metrics through an API per region, therefore limiting the amount of data being sent to the dashboard and speeding up load times. 

### UI updates related to this User Story:
•	When providers send posts, they will have the option of who will receive posts based on 1) all posts within x region (based on returned polygon on Nominatim search); be able to select multiple regions 2) x distance away 3) or within user-defined polygon. There will also be a map that shows where the post will be sent.
•	Think about this, it would add a lot more complexity, including adding subqueries and storing individual polygons per clients Clients will be able to adjust through their settings, how they receive posts: 1) all posts within x region 2) x distance away 3) or within user-defined polygon

### Basic system components:
•	UI modifications will be modified on select pages on HopeOneSource. New Map Module will have to be integrated with Drupal 8.
•	Drupal code in Drupal module will process form and send select PostGreSQL spatial queries to remote PostGIS database on AWS and be able to receive back results.
•	PostGIS database will be set up on AWS 

### Detailed implementation plan link:
https://docs.google.com/document/d/1HMQ2J9ikfK7IR1aI4ef6alnWBPNncKgik5iK3SJ8lPo/edit#

### Environment
* Any basic vanilla Drupal 8 environment is acceptable for development. 

### Doc outlining potential Drupal Modules to integrate
https://docs.google.com/document/d/1zcPsljPYsGa6f9JvfJ9B2c6Y3lzTl04do2RBhmsbyVo/edit
