How to import
=============

**NOTE: THIS DOCUMENT IS A WORK IN PROGRESS**

**ALSO: THE IMPORT HAS NOT YET BEEN APPROVED BY THE OPENSTREETMAP COMMUNITY**

**DO NOT IMPORT ANY DATA UNTIL THESE INSTRUCTIONS HAVE BEEN FINALIZED AND THE IMPORT HAS BEEN APPROVED**

## Getting started

### Creating an import account

 * OSM best practices require that you do not use your normal OSM account for the imports. Create a new account for this purpose. 
 Usually, it's your existing OSM username followed by `_imports` (e.g. `maning_imports)`.
 Post your import account username in this [ticket](http://github.com/osmlab/labuildings/issues/40).

### Getting familiar with JOSM

To contribute to this project, you need to use the JOSM editor.  Here are some resources to get you started:
 * LearnOSM - http://learnosm.org/en/josm/
 * Mapbox Mapping wiki - https://www.mapbox.com/blog/making-the-most-josm/

### Check out a task on the tasking manager

 * Tasks will be available on this **[Tasking Manager](http://52.74.49.58:6543/project/15 link soon)**.
 * Priority: we are working on Los Angeles City first, which is broken down by census block groups. Each task performed is one block group within the city boundaries.
 * why? because different parts of the county have different data problems to watch out for. If we all run into the same problems at the same time, it will be easier for us to help each other and improve the processing scripts and the import workflow.

## Import workflow
 * Choose which area you want to work on. (Browse the tasking manager and visualization of existing building and address data).
 * Load the `.osm` file from the tasking manager.
 
 ![getdata](https://cloud.githubusercontent.com/assets/353700/12942521/ddcbf232-d001-11e5-96c4-5223bd633647.gif)

 * Review the `.osm` file for inconsistencies and FIXME tags.
 * Run JOSM **Validator**, fix the data.

![validator](https://cloud.githubusercontent.com/assets/353700/12942520/ddc572f4-d001-11e5-8cf6-399511cd47fa.gif) 

 * Download the current OSM data for the bounding box of the `.osm` file.
 
 ![getosmdata](https://cloud.githubusercontent.com/assets/353700/12942519/ddc04c2a-d001-11e5-978a-b441c2607fcd.gif)
 
 * Compare both data for conflicts.
 * If there are any problems you don't know how to deal with, do not proceed. Instead flag the `.osm` file for a more advanced user to look at. (Use github [issues](http://github.com/osmlab/labuildings/issues) to flag concerns, and/or create [OSM notes](http://wiki.openstreetmap.org/wiki/Notes)). Then unlock your task on the tasking manager and pick a new area to work on.
 * Manually merge the layers together: preserve the work of previous mappers wherever possible. Copy address information and building height to existing building shapes if they are of higher quality.
 * Use **Replace geometry** to merge.
 
![replace](https://cloud.githubusercontent.com/assets/353700/12942518/ddba87a4-d001-11e5-9441-2561f67b45bc.gif) 

*  Run JOSM Validator again, fix the data.

### Finally, upload it

 * Add the tag `#labuildings` to your changesets.
 
![upload](https://cloud.githubusercontent.com/assets/353700/12942517/ddb5c930-d001-11e5-826a-342c3f80f014.gif) 

## What to watch out for

### Validate the import with your eyes before uploading!

 * Run the [JOSM validator](http://wiki.openstreetmap.org/wiki/JOSM/Validator). Check for any errors it detects.
 * Look for any [FIXME](http://wiki.openstreetmap.org/wiki/Key:fixme) tags that the processing scripts generated. These are areas that need human oversight.
 * Check for small building parts that should be joined to the main building. We've already found a few examples of these in the data (see [issue #19](https://github.com/osmlab/labuildings/issues/19)), so make sure you keep an eye out for these.
 * Inspect everything else with a critical eye! Don't trust that the validator or FIXME tags will catch everything. There may be other bugs that only you can detect. Use your human smarts!
 
### Conflating with existing data
 * Look for any overlaps with existing buildings. Existing buildings in OSM are probably _more_ up-to-date than our imported data. Do not assume the imported data is better, mostly likely it is worse! 
 * Carefully combine the import data with the existing OSM data. If you aren't sure about some tags, ask someone! Especially ask the original mapper! 
 
### How to ground-truth the data
 * Up-to-date aerial imagery... try several sources
 * See if the street is on [Mapillary](http://www.mapillary.com/map/im/bbox/33.65806700735439/34.410308669603495/-119.10278320312499/-117.3504638671875)
 * Go out and check it out yourself! Take a field trip!
 * **DO NOT USE GOOGLE MAPS OR GOOGLE STREET VIEW**

### Identifying New Buildings with imported and existing data
* Aerial Imagery used as a basemap should help to identify and draw newer buildings not found in the imported an existing data.
* Newer building should be identified and flagged. (This process should not be done, pending approval and recommendations from the OSM Community.)
 
## Communicate communicate communicate!

### How to ask for help

 * Create [issues](http://github.com/osmlab/labuildings/issues) on this github repo.
 * Ask questions on the [gitter channel](http://gitter.im/osmlab/labuildings).
 * Contact [@almccon](http://twitter.com/almccon), [@cityhubla](http://twitter.com/cityhubla),  [@jschleuss](http://twitter.com/jschleuss),  [@maningsambale](http://twitter.com/maningsambale).

### How to share your progress

 * Make sure you close your task on the tasking manager

### How to communicate with other mappers

 * JOSM [GeoChat](http://wiki.openstreetmap.org/wiki/JOSM/Plugins/GeoChat) feature
 * Twitter hashtag (TBD)
 * Befriend other mappers on openstreetmap.com
