# geospatial_posts
define areas for sending posts

### Skill set Needed: Moderate or expert Drupal developer, experience with Drupal modules, PHP

### Why do we need Geospatial Search and Querying capabilities?
1.	Allowing HopeOneSource to scale. HopeOneSource will expand to different regions while retaining a single Drupal instance. Therefore we will need to have geospatial querying capabilities to limit posts being sent and received to selected regions in addition to just the distance based limits we place on sent posts. Users in the system will either have the capability to select regions based on searching for them (based on Nominatum search) and/or selecting pre-defined regions.
2.	This added functionality will also be part of one of the requirements when building the Gap Finder 2.0. It will enable us to request metrics through our API per region, therefore limiting the amount of data being sent to the dashboard and speeding up load times.
UI updates related to this User Story:
1.	When providers send posts, they will have the option of who will receive posts based on 1) all posts within x region (based on returned polygon on Nominatum search); be able to select multiple regions 2) x distance away 3) or within user-defined polygon. There will also be a map that shows where the post will be sent.
2.	think about this, it would add a lot more complexity, including adding subqueries and storing individual polygons per clients Clients will be able to adjust through their settings, how they receive posts: 1) all posts within x region 2) x distance away 3) or within user-defined polygon
### Basic system components:
•	UI modifications will be modified on select pages on HopeOneSource. New Map Module will have to be integrated with Drupal 8.
•	Drupal code in Drupal module will process form and send select PostGreSQL spatial queries to remote PostGIS database on AWS and be able to receive back results.
•	PostGIS database will be set up on AWS 
### Detailed implementation plan link:
https://docs.google.com/document/d/1HMQ2J9ikfK7IR1aI4ef6alnWBPNncKgik5iK3SJ8lPo/edit#

