# magento-modman-deployment-script


Handy bash script to (remotely) deploy Magento extensions using modman.

 Use this script to deploy Magento extensions to your (remote) Magento setup. 
 Optionally, specify files and folders to exclude from deployment, such as the 
 .git folder.

## How it works
 
 This script copies your Magento extension to the .modman directory of your
 destination Magento projects and deploys it there using modman. In addition,
 it exludes files and folders (such as .git) so that only relevant files are
 copied.
 
 This script uses rsync to copy files to your (remote) Magento project.

 Example:

 1) Let's say you develop a Magento extension in 
    /home/my_user/workspace/MyExtension
 
 2) Your development Magento setup is located at /var/www/magento-dev1/

 3) This script copies your Magento extension from 
    /home/my_user/workspace/MyExtension 
    to
    /var/www/magento-dev1/.modman/
    and deploys it using modman.

 4) You're done! 


## Requirements

 - rsync
 - modman

## Usage

 1) Set the modman configuration file to meet your extension's requirements.
    Check out the modman Tutorial for more information.

 2) Set configuration options to your needs:

    - EXTENSION_NAME
    - MODMAN_PATH
    - EXTENSION_PROJECT_PATH
    - DST_MAGE_PROJECT_PATH

 3) Optionally specify files and folders to exclude:
    
    - EXCLUDE_FILES_AND_FOLDERS

    Entries are relative to EXTENSION_PROJECT_PATH.

 4) Run deployment script, e.g. from within your EXTENSION_PROJECT_PATH.

 5) Check your Magento setup for your new or updated extension :)


## Improvements

 Possible improvements for this script are:

 - auto cache clear
 - auto path detection

## CHANGELOG

### 1.0 

Initial release

### 1.1

+ added --delete option for rsync 
 