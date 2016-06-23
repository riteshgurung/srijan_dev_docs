# Feature Guidelines

All the projects should use [Features](https://drupal.org/project/features) Module for deployment. All the team members should go through 
*Drupal Deployment with Features and Drush Series* from Drupalize.me.

## Dos and Don'ts with Features.
* Feature module is not for porting your configurations from one instance to other but to bundle up your functionality/feature.
* Everytime you create new feature think it like any other custom/contrib module which is in place to serve specific functionality.
* The way you build features is depends on agreement of your team. The most important thing is the complete team follow the same guidliness, its very important to discuss feature architecture with in team before you start a project.
* The best way to decide what a feature will have is to look around configurations for specific set of functionalities. Consider this with an example: You want to have image carousel on your sight, so what we do is create a content type called Image Slider, Install views module Install silder display plugin, create view, create image cache. So basically all of these configuration build one feature "Carousel". This makes this complete bundle of functionalities to go in one feature which you even install  on vanilla drupal gives you all you want to start with.
* Features should be independent of each other, so if they are created of specific set of functionality there is less chance of ending up of dependencies.
* Its good to have multiple features broken into small set of standalone functionalties rather than one mamoth feature. A feature with lot of configuration is really hard to maintain and also it creates chances to wipe configuration and hence **client data**.
* Its important to maintain your features in default state, otherwise features which are not updated for long can cause loss of data and configuration.
* Features are never supposed to get direct deployed on production, they always need a prior testing. So workflow could be create feature on your local and deploy it to dev, get it tested and then move it to stg/prod.
* Always think twice before you decide to revert or recreate feature, revert will update your database to match with your codebase and recreate/update will update your codebase as per your database configurations.
* While reverting a feature make sure you are not deleting important configuration. [Feature Diff](https://www.drupal.org/project/features_diff) is a good module to see the difference in feature code and what is there in database.
* Always make sure you take latest feature codebase before you are updating it.
* Git helps a lot in making sure we are not overring someone else configuration via feature, always look at git diff on your features file if multiple people working on same project.
* Always create a base field feature which helps a lot in keeping base settings and instance settings of fields at two places and hence less chances of overriding one module because of other. [Good Read](https://www.phase2technology.com/blog/new-field-bases-and-instances-in-features/).

## What should go inside a feature

* Less is more in case of feature.
* The bare minimum. Do not get the configurations you get out of the box, for example we are not supposed to pull a body field in content type as this is what Drupal gives out of the box, soon you install the feature which if creates a content type, body field will create by itself, it does not need to be part of features.
* So if we are exporting a content type with features settings like create/edit/comment permission, comment settings, publishing settings should only go inside a feature if you are configuring it what the drupal does not give by defaul, else no need to get the things in feature what drupal gives by default.
* 

## Naming Conventions
* All features should be saved to /sites/all/modules/features/
* All features should be prefixed with <project_name> when being named
* Features should be named appropriate to what they are. Take example of feature mentioned above about image_slider, so if we are workign on project called test so our feature name could be test_image_slider. Now catch is if you are building a feature which is generic enough to be reused in other projects than do not prefix feature module with project name, so all such generaised and resusable feature module might start with "feature_" itself, in our case it would be "feature_image_silder".

## Resources
* slides.com/arpitrastogi/agenda
* https://www.phase2technology.com/blog/new-field-bases-and-instances-in-features/
