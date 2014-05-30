My Tests Using Eclipse Luna RC1
===============================

Environment
-----------

* Linux: Ubuntu-12.04 64bit
* Java: Java7u21 from Oracle

Preparations
------------

* Download and install eclipse-jee-luna-RC1
* Start eclipse using a fresh workspace
* Close the Welcome Screen

Import The Git Project
----------------------

Within Eclipse, do this

* File - Import - Git - Projects from Git - Clone URI - Next
* Source Git Repository
    * Location - URI: https://github.com/MulgaSoft/e4macs.git
    * Next
* Branch Selection
    * dev
    * master
    * Next
* Local Destination
    * Directory: .../git/e4macs
    * Initial branch: master
    * Next
* Select a wizard...
    * Import existing projects
    * Next
* Import Projects
    * Make sure all projects are selected
    * Search for nestes projects
    * Finish

Switch To The Dev Branch
------------------------

* Within 'Project Explorer' select 'Emacs+'
* Team - Switch to... - Other...
* Branches
    * Remote Tracking
    * origin/dev
    * Checkout...
* Check out
    * Checkout as New Local Branch
* Create Branch
    * Branch name: dev
    * Finish

Build The Update Site
---------------------

* Within 'Project Explorer' select 'Emacs+Update'
* Open 'site.xml'
* site.xml
    * Synchronize...
* Feature Properties Synchronization
    * Synchronize all features on the size
    * Finish
* site.xml
    * Save
    * Build All

Package The Update File
-----------------------

Open a command line window and do this:

* `cd e4macs`
* `cd Emacs+Update`
* `zip -r /tmp/emacs+-dev-20140530.zip .`

You can install the zip file within eclipse via

* Help - Install New Software...
* Add - Archive...

Doing A Release On GitHub
-------------------------

* Create a tag on GitHub - for example v0.1-pre
* Pull the tag: `git pull --tags`
* Checkout the tag: `git checkout v0.1-pre`
* Within Eclipse: Build The Update Site (see above for details)
* Package The Update File: `cd Emacs+Update; zip -r /tmp/emacs-plus-v0.1-pre.zip .`
* Attach the Update File To The Github Tag/Release
