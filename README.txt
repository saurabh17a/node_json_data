#Get Node data in JSON Format using Site API Key.

  *Introduction
  *Requirements
  *Installation
  *Configuration
  *Resources Used
  

INTRODUCTION
----------------------

Get Node data in JSON Format using Site API Key.


REQUIRMENTS
----------------------

This module needs to alter the existing Drupal "Site Information" form. Specifics:

* A new form text field named "Site API Key" needs to be added to the "Site Information" form with the default value of “No API Key yet”.
* When this form is submitted, the value that the user entered for this field should be saved as the system variable named "siteapikey".
* A Drupal message should inform the user that the Site API Key has been saved with that value.
* When this form is visited after the "Site API Key" is saved, the field should be populated with the correct value.
* The text of the "Save configuration" button should change to "Update Configuration".
* This module also provides a URL that responds with a JSON representation of a given node with the content type "page" only if the previously submitted API Key and a node id (nid) of an appropriate node are present, otherwise it will respond with "access denied".

## Example URL

http://localhost/data/{api-key}/{content-type}/{node-id}


INSTALLATION
----------------------

1. Install as you would  normally install a Druapl contributed module. 
* Visit: https://www.drupal.org/docs/8/extending-drupal-8/installing-drupal-8-modules
for further informtaion.


CONFIGURATION
----------------------

1. Go to Administrator > Configuration > System > Basic site settings.
or visit '/admin/config/system/site-information'.

2. In the SITE DETAILS section add 'Site API Key'.

3. Configure permissions at /admin/people/permissions under 
'Axelerant Site API Key Custom Module'.

3. Access the json representation of respective page type node by visiting the 
url '/data/{site_api_key}/{content-type}/{node_id}'.


RESOURCES USED
----------------------

https://api.drupal.org/api/drupal/core%21lib%21Drupal%21Core%21Form%21form.api.php/function/hook_form_FORM_ID_alter/8.2.x
https://www.drupal.org/node/2407153
https://api.drupal.org/api/drupal/core!includes!bootstrap.inc/function/drupal_set_message/8.2.x
https://www.drupal.org/docs/8/api/routing-system/structure-of-routes
https://www.drupal.org/docs/8/api/routing-system/using-parameters-in-routes
https://api.drupal.org/api/drupal/vendor%21symfony%21http-foundation%21JsonResponse.php/class/JsonResponse/8.2.x
