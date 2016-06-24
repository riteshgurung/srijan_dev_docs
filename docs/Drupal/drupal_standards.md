## Drupal Guidelines
--------

## Modules
  Drupal 7
  * Custom Modules
    * sites/all/modules/custom
  * Contrib Modules
     * sites/all/modules/contrib
  * Features
     * sites/all/modules/features

  * Patches
    * sites/all/patches
    * Its very important to keep track of all the patches you have used in the project, this helps in long run maintenance of project, later when you do upgrade of Drupal. Keeping all at one place later helps in the upgradation path.

  * Theme
    * sites/all/themes
    
# Custom Module Architecture

 * Most of times we end up having custom modules which have dependency on each other, which makes it quiet hard to uninstall a module when not needed, which defeats the purpose of building modules, as the name says modules should be modular enough to allow us to switch a functionality on/off with the module status. The important thing is to build to independent modules.
 * An easy way to maintain custom module could be 
   * Create a library module, role of this module would be to contain all helper functions which includes database queries like get_node_title_by_nid(). Rest of our custom modules will have dependency on library module, but not among each other.
   