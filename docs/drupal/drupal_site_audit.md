Questions to raise:

- Site usage

    * user count
    * node count
    * site access anayltics

- Site Architecture
 

- Server Architecture

    * hosting provider.
    * Solr in use?
  
    * Failover for web server.
    * Failover for mysql.
    * Failover for solr.

    * Server configuration.

        * RAM, Storage, mysql storage, load balancer

    * Monitoring and notifications


- Current Issues

    * Performance issues on specific pages?


- Access to database and code base


**Audit**

- Setup site on local and run through following tools

1. Performance 

    * Tool: 
      * Blackfire.
    * Mobile Perfomance Tool
      * http://mobitest.akamai.com/m/index.cgi

2. Overall site review

        * Caching
        * Modules unused
        * Unused content types and fields
        * Aggregation of css/js
        * Get file size of files managed by Drupal
        * Cron status(its important we have last cron entry as drupal does lot of cleanup on cron run)
        * Storage Engine(Inno DB)
        * Modules Count enabled
        * Any development module
        * Any hacked modules (core and custom)
        * Update to Drupal Core
        * Update to contrib module
        * Database logging
        * Field Count

     * Tool: Install site_audit, its not a drupal module but kind of library which runs via drush and gets the above information in conjuction with following modules (https://www.drupal.org/project/site_audit)

     * Helper Modules
         1. Hacked Module (https://www.drupal.org/project/hacked).
         2. Drupalgeddon  Drush tool(https://www.drupal.org/project/drupalgeddon).
         3. Security Review (https://www.drupal.org/project/security_review).
         4. Sensitive Data Drush tool(https://www.drupal.org/project/sensitive_data).

3. Coding Standards

    * Drupal directory structure
    * run code sniffer on all custom modules.

4. Helper Commands

     * drush aa --html --bootstrap --detail --skip=insights > ~/Desktop/report.html (when site_audit tool is installed).
     * drush asec  (when Drupalgeddon is installed).
     * phpcs --standard=Drupal <filepath>