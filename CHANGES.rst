Version 2.2.0 (2021-12-11)
--------------------------

Features
~~~~~~~~~
* From this release, users are able to define remote_workspace in sdf file and use remote scenario

Enhancements
~~~~~~~~~~~~
* Make env variables available during Orchestrate and execute stage of Teflo run 
* Added __hash__ and __eq__ for Teflo Resource class

Bug Fixes
~~~~~~~~~~~~~
* Fixed notification to display passed and failed tasks for the entire scenario_graph 
* Fixed "for running You have to provide a valid scenario file. fails with 'skip-fail' KeyError" 


Version 2.1.0 (2021-11-05)
--------------------------

Documentation
~~~~~~~~~~~~
* Modified quickstart page and flowchart for teflo

Enhancements
~~~~~~~~~~~~
* Make the data folder and results folder available to users in the form of environment variables 
* Added support usage of variables in the variables files in message notification templating
* Add skip failures ability during the graph run 
* Allow iterate_method from cli 
* Added check for installing ansible roles when running ansible playbooks under resource_check method 

Bug Fixes
~~~~~~~~~~~~~
* Fixed syntax warnings in CI
* Fix same file error 
* Fixed test result summary does not take into account error test case elements 
* Fixed the ansible nested var issue 
* Fix issues of jinja templating in include


Version 2.0.0 (2021-08-02)
--------------------------

Features
~~~~~~~~~~~~
* Recursive include of child scenarios is supported with scenario graph implementation
* Replaced scenario_streams with the newly added scenario graph
* teflo show -s sdf_file.yml --show-graph added, users can see the whole scenario graph structure
* Added term color to display log messages red(for errors) and green for other information
* Added support for selecting the scenario execution order __by_level__ and __by_depth__ using the *included_sdf_iterate_method* parameter in teflo.cfg

Enhancements
~~~~~~~~~~~~
* Redesigned teflo execution pipeline
* Redesigned the cleanup logic for scenarios
* Redesigned the validate logic for scenarios
* Redesigned the results generation
* Redesigned the inventory generation(output inventory stays the same, the logic behind the scene changed)
* Added typing for many functions(e.x *def func(param:list=[]):->str*)
* Added tostring,path,pullpath,inventory methods to scenario class

Documentation
~~~~~~~~~~~~~
* Added explanation about how to use scenario graph
* Added explanation about how *include* works with scenario graph

Version 1.2.5 (2021-11-05)
--------------------------

Enhancements
~~~~~~~~~~~~
* Enabled ci for version 1.2.x

Bug Fixes
~~~~~~~~~
* Fix for: custom resource_check does not honor the ansible_galaxy_options
* Fixed the ansible nested var issue with ansible_facts


Version 1.2.4 (2021-09-23)
--------------------------

Enhancements
~~~~~~~~~~~~
* beaker provisioner total attempts to an integer data type 
* add space to beaker warning 
* Allow users to set ansible verbosity using ansible environment variable 

Bug Fixes
~~~~~~~~~
* invalid inventory generated when groups contains the machine name \
* Report task fails when executes attribute is used and No asset is present 

Version 1.2.3 (2021-08-02)
--------------------------

Features
~~~~~~~~~~~~
* Add the var-file declared by user as an extra_vars in the ansible orchestrate and execute task
* teflo_rppreproc_plugin to support RPV5 instances

Enhancements
~~~~~~~~~~~~
* support --vars-data w/show command
* Added support bkr's ks-append(s) option in beaker-client plugin

Bug Fixes
~~~~~~~~~
* Added a generic exception handling during ssh to hosts
* Added fix for resource ordering issue in results.yml
* update import_results list when is not None
* Using variable files with variables as list/dict causes an exception

Documentation
~~~~~~~~~~~~~
* Correction in documentation to point to fixed gh_pages
* Added release cadence to Contribution.rst
* Added workaround(use of shell script) to allow make docs-wiki work correctly using makefile

Version 1.2.2 (2021-07-16)
--------------------------

Features
~~~~~~~~~~~~
* Added teflo init command (It will generate a genralized teflo workspace for you with examples)
* Added openstack instance metadata field for os_libcloud_plugin

Version 1.2.1 (2021-06-28)
--------------------------

Features
~~~~~~~~~~~~
* Introduced teflo_notify_service_plugin, users can use this plugin to send out messages to many platforms now

Enhancements
~~~~~~~~~~~~
* Added new default location for the usage of variables, you can now put varfile in default locations without specifying the with --vars-data
* Added nested recursive variable support, now the users can use variable inside a variable in your variable file
* Added ability to pass multiple files to the extra_vars module
* Create root users ssh directory for beaker provisioner when non existing
* Added teflo_notify_service_plugin, terraform-plugin and webhook-notification-plugin to setup.py extra require, users can do something like 'pip install teflo[teflo_notify_service_plugin]' now

Bug Fixes
~~~~~~~~~
* Fixed Ansible version bug

Documentation
~~~~~~~~~~~~~
* Updated compatibility matrix
* Updated some installation guide for some plugins
* Update teflos package classifiers

Version 1.2.0 (2021-05-10)
--------------------------

Features
~~~~~~~~~~~~
* Introduced teflo_terraform_plugin, users can use terraform during provision phase now

Enhancements
~~~~~~~~~~~~
* Use pyssh over paramiko library

Bug Fixes
~~~~~~~~~
* Hosts are not correctly resolved when groups are mentioned in the orchestrate task 
* Change the copyright license to 2021
* Fix the ansible stderr issue

Documentation
~~~~~~~~~~~~~
* Modified compatibility matrix
* removed jenkins folder
* Added example in execute.rst

Version 1.1.0 (2021-03-29)
--------------------------

Enhancements
~~~~~~~~~~~~
* Improved error messaging for syntax errors in SDF
* Allow jinja templating within teflo.cfg
* Allow multiple --vars-data arguments
* Removed backward compatibility support for using name field under orchestrate block as script/playbook path
* Removed backward compatibility support for using ansible_script as a boolean
* Removed backward compatibility support to remove role attribute from assets, and use only groups

Bug Fixes
~~~~~~~~~
* Modified ansible-base version in setup.py
* Fixed issue during generation inentory for static host with no groups attribute
* Fixed issue where Teflo was improperly exiting with a return code of 0 when the
  scenario descriptor file was invalid

Documentation
~~~~~~~~~~~~~
* Added more details and diagram on the teflo readme page
* Corrected the vars-data info page
* Use github pages for teflo plugins

Version 1.0.1 (2021-02-10)
--------------------------

Enhancements
~~~~~~~~~~~~
* Update teflo config code to not make defaults section mandatory
* For Openstack, display instance IDs
* Alter error message to not contain the words "fail" and "success" simultaneously
* The openstack lincloud schema needs two additional keys project_id and project_domain_id

Bug Fixes
~~~~~~~~~
* asset delete fails when using native provisioner (os libcloud) without provider attribute

Documentation
~~~~~~~~~~~~~
* Updated provision and examples docs to remove provider key and update examples
* Updated contribution page to add plugin template info

Version 1.0.0 (2021-01-07)
--------------------------

This is the first version of Teflo project (formerly known as Carbon)
