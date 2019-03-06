# OpenAPIClient-php
No description provided (generated by Openapi Generator https://github.com/openapitools/openapi-generator)

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.0
- Build package: org.openapitools.codegen.languages.PhpClientCodegen

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/ProcessMaker/bpm-php-sdk.git"
    }
  ],
  "require": {
    "ProcessMaker/bpm-php-sdk": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
    require_once('/path/to/OpenAPIClient-php/vendor/autoload.php');
```

## Tests

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: pm_api_bearer
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\CommentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$comments_editable = new \OpenAPI\Client\Model\CommentsEditable(); // \OpenAPI\Client\Model\CommentsEditable | 

try {
    $result = $apiInstance->createComments($comments_editable);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CommentsApi->createComments: ', $e->getMessage(), PHP_EOL;
}

?>
```

## Documentation for API Endpoints

All URIs are relative to *http://localhost/api/1.0*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CommentsApi* | [**createComments**](docs/Api/CommentsApi.md#createcomments) | **POST** /comments | Save a new comment
*CommentsApi* | [**deleteComments**](docs/Api/CommentsApi.md#deletecomments) | **DELETE** /comments/id | Delete a comments
*CommentsApi* | [**getCommentById**](docs/Api/CommentsApi.md#getcommentbyid) | **GET** /comments/commentId | Get single comment by ID
*CommentsApi* | [**getComments**](docs/Api/CommentsApi.md#getcomments) | **GET** /comments | Returns all comments for a given type
*CommentsApi* | [**updateComment**](docs/Api/CommentsApi.md#updatecomment) | **PUT** /comments/commentId | Update a comment
*EnvironmentVariablesApi* | [**createEnvironmentVariables**](docs/Api/EnvironmentVariablesApi.md#createenvironmentvariables) | **POST** /environment_variables | Save a new environment_variables
*EnvironmentVariablesApi* | [**deleteEnvironmentVariables**](docs/Api/EnvironmentVariablesApi.md#deleteenvironmentvariables) | **DELETE** /environment_variables/{environment_variables_id} | Delete a environment_variables
*EnvironmentVariablesApi* | [**getEnvironmentVariables**](docs/Api/EnvironmentVariablesApi.md#getenvironmentvariables) | **GET** /environment_variables | Returns all environmentVariables that the user has access to
*EnvironmentVariablesApi* | [**getEnvironmentVariablesById**](docs/Api/EnvironmentVariablesApi.md#getenvironmentvariablesbyid) | **GET** /environment_variables/{environment_variables_id} | Get single environment_variables by ID
*EnvironmentVariablesApi* | [**updateEnvironmentVariables**](docs/Api/EnvironmentVariablesApi.md#updateenvironmentvariables) | **PUT** /environment_variables/{environment_variables_id} | Update a environment_variables
*FilesApi* | [**createFile**](docs/Api/FilesApi.md#createfile) | **POST** /requests/{request_id}/files | Save a new media file
*FilesApi* | [**deleteFile**](docs/Api/FilesApi.md#deletefile) | **DELETE** /requests/{request_id} | Delete a media file
*FilesApi* | [**getFiles**](docs/Api/FilesApi.md#getfiles) | **GET** /requests/{request_id}/files | Returns the list of files associated to a request
*FilesApi* | [**getFilesById**](docs/Api/FilesApi.md#getfilesbyid) | **GET** /requests/{request_id}/files/{file_id} | Get a file uploaded to a request
*FilesApi* | [**updateFile**](docs/Api/FilesApi.md#updatefile) | **PUT** /requests/{request_id}/files/{file_id} | Update a media file
*GroupMembersApi* | [**createGroupMembers**](docs/Api/GroupMembersApi.md#creategroupmembers) | **POST** /group_members | Save a new group_members
*GroupMembersApi* | [**deleteGroupMembers**](docs/Api/GroupMembersApi.md#deletegroupmembers) | **DELETE** /group_members/group_memberId | Delete a group_members
*GroupMembersApi* | [**getGroupMemberById**](docs/Api/GroupMembersApi.md#getgroupmemberbyid) | **GET** /group_members/group_memberId | Get single group_member by ID
*GroupMembersApi* | [**getGroupMembers**](docs/Api/GroupMembersApi.md#getgroupmembers) | **GET** /group_members | Returns all groups for a given member
*GroupMembersApi* | [**getGroupMembersAvailable**](docs/Api/GroupMembersApi.md#getgroupmembersavailable) | **GET** /group_members_available | Returns all groups available for a given member
*GroupMembersApi* | [**getUserMembersAvailable**](docs/Api/GroupMembersApi.md#getusermembersavailable) | **GET** /user_members_available | Returns all users available for a given member
*GroupUsersApi* | [**getMembers**](docs/Api/GroupUsersApi.md#getmembers) | **GET** /group_users | Returns all users of a group
*GroupsApi* | [**createGroup**](docs/Api/GroupsApi.md#creategroup) | **POST** /groups | Save a new groups
*GroupsApi* | [**deleteGroup**](docs/Api/GroupsApi.md#deletegroup) | **DELETE** /groups/groupId | Delete a group
*GroupsApi* | [**getGroupById**](docs/Api/GroupsApi.md#getgroupbyid) | **GET** /groups/groupId | Get single group by ID
*GroupsApi* | [**getGroups**](docs/Api/GroupsApi.md#getgroups) | **GET** /groups | Returns all groups that the user has access to
*GroupsApi* | [**updateGroup**](docs/Api/GroupsApi.md#updategroup) | **PUT** /groups/groupId | Update a group
*NotificationsApi* | [**createNotification**](docs/Api/NotificationsApi.md#createnotification) | **POST** /notifications | Save a new notifications
*NotificationsApi* | [**deleteNotification**](docs/Api/NotificationsApi.md#deletenotification) | **DELETE** /notifications/notificationId | Delete a notification
*NotificationsApi* | [**getNotificationById**](docs/Api/NotificationsApi.md#getnotificationbyid) | **GET** /notifications/notificationId | Get single notification by ID
*NotificationsApi* | [**getNotifications**](docs/Api/NotificationsApi.md#getnotifications) | **GET** /notifications | Returns all notifications that the user has access to
*NotificationsApi* | [**processMakerHttpControllersApiNotificationControllerUpdateAsRead**](docs/Api/NotificationsApi.md#processmakerhttpcontrollersapinotificationcontrollerupdateasread) | **PUT** /read_notifications | Mark notifications as read by the user
*NotificationsApi* | [**processMakerHttpControllersApiNotificationControllerUpdateAsReadAll**](docs/Api/NotificationsApi.md#processmakerhttpcontrollersapinotificationcontrollerupdateasreadall) | **PUT** /read_all_notifications | Mark notifications as read by id and type
*NotificationsApi* | [**updateNotification**](docs/Api/NotificationsApi.md#updatenotification) | **PUT** /notifications/notificationId | Update a notification
*PermissionsApi* | [**processMakerHttpControllersApiPermissionControllerUpdate**](docs/Api/PermissionsApi.md#processmakerhttpcontrollersapipermissioncontrollerupdate) | **PUT** /permissions | Update the permissions of an user
*ProcessApi* | [**createProcess**](docs/Api/ProcessApi.md#createprocess) | **POST** /processes | Save a new process
*ProcessApi* | [**deleteProcess**](docs/Api/ProcessApi.md#deleteprocess) | **DELETE** /processes/processId | Delete a process
*ProcessApi* | [**getProcessById**](docs/Api/ProcessApi.md#getprocessbyid) | **GET** /processes/processId | Get single process by ID
*ProcessApi* | [**getProcessById_0**](docs/Api/ProcessApi.md#getprocessbyid_0) | **GET** /processes/processId/export | Export a single process by ID
*ProcessApi* | [**getProcessById_1**](docs/Api/ProcessApi.md#getprocessbyid_1) | **GET** /processes/import | Import a process
*ProcessApi* | [**getProcesses**](docs/Api/ProcessApi.md#getprocesses) | **GET** /processes | Returns all processes that the user has access to
*ProcessApi* | [**restoreProcess**](docs/Api/ProcessApi.md#restoreprocess) | **PUT** /processes/processId/restore | Restore an inactive process
*ProcessApi* | [**startProcesses**](docs/Api/ProcessApi.md#startprocesses) | **GET** /start_processes | Returns the list of processes that the user can start
*ProcessApi* | [**updateProcess**](docs/Api/ProcessApi.md#updateprocess) | **PUT** /processes/processId | Update a process
*ProcessCategoriesApi* | [**createProcessCategory**](docs/Api/ProcessCategoriesApi.md#createprocesscategory) | **POST** /process_categories | Save a new process Category
*ProcessCategoriesApi* | [**deleteProcessCategory**](docs/Api/ProcessCategoriesApi.md#deleteprocesscategory) | **DELETE** /process_categories/process_category_id | Delete a process category
*ProcessCategoriesApi* | [**getProcessCategories**](docs/Api/ProcessCategoriesApi.md#getprocesscategories) | **GET** /process_categories | Returns all processes categories that the user has access to
*ProcessCategoriesApi* | [**getProcessCategoryById**](docs/Api/ProcessCategoriesApi.md#getprocesscategorybyid) | **GET** /process_categories/process_category_id | Get single process category by ID
*ProcessCategoriesApi* | [**updateProcessCategory**](docs/Api/ProcessCategoriesApi.md#updateprocesscategory) | **PUT** /process_categories/process_category_id | Update a process Category
*ProcessRequestsApi* | [**deleteProcessRequest**](docs/Api/ProcessRequestsApi.md#deleteprocessrequest) | **DELETE** /requests/process_request_id | Delete a process request
*ProcessRequestsApi* | [**getProcessRequestById**](docs/Api/ProcessRequestsApi.md#getprocessrequestbyid) | **GET** /requests/process_request_id | Get single process request by ID
*ProcessRequestsApi* | [**getProcessesRequests**](docs/Api/ProcessRequestsApi.md#getprocessesrequests) | **GET** /requests | Returns all process Requests that the user has access to
*ProcessRequestsApi* | [**updateProcessRequest**](docs/Api/ProcessRequestsApi.md#updateprocessrequest) | **PUT** /requests/process_request_id | Update a process request
*ProcessWebhooksApi* | [**createProcessWebhook**](docs/Api/ProcessWebhooksApi.md#createprocesswebhook) | **POST** /processes/{process_id}/webhooks/ | Save a new webhook for a start node
*ProcessWebhooksApi* | [**deleteProcessWebhook**](docs/Api/ProcessWebhooksApi.md#deleteprocesswebhook) | **DELETE** /processes/{process_id}/webhooks/ | Delete (revoke) a webhook for a start node
*ProcessWebhooksApi* | [**getProcessWebhook**](docs/Api/ProcessWebhooksApi.md#getprocesswebhook) | **GET** /processes/{process_id}/webhooks/ | Get the webhook for a start node
*ScreenCategoriesApi* | [**createScreenCategory**](docs/Api/ScreenCategoriesApi.md#createscreencategory) | **POST** /screen_categories | Save a new Screen Category
*ScreenCategoriesApi* | [**deleteScreenCategory**](docs/Api/ScreenCategoriesApi.md#deletescreencategory) | **DELETE** /screen_categories/screen_category_id | Delete a screen category
*ScreenCategoriesApi* | [**getScreenCategories**](docs/Api/ScreenCategoriesApi.md#getscreencategories) | **GET** /screen_categories | Returns all screens categories that the user has access to
*ScreenCategoriesApi* | [**getScreenCategoryById**](docs/Api/ScreenCategoriesApi.md#getscreencategorybyid) | **GET** /screen_categories/screen_category_id | Get single screen category by ID
*ScreenCategoriesApi* | [**updateScreenCategory**](docs/Api/ScreenCategoriesApi.md#updatescreencategory) | **PUT** /screen_categories/screen_category_id | Update a screen Category
*ScreensApi* | [**createScreens**](docs/Api/ScreensApi.md#createscreens) | **POST** /screens | Save a new screens
*ScreensApi* | [**deleteScreen**](docs/Api/ScreensApi.md#deletescreen) | **DELETE** /screens/screensId | Delete a screen
*ScreensApi* | [**getScreens**](docs/Api/ScreensApi.md#getscreens) | **GET** /screens | Returns all screens that the user has access to
*ScreensApi* | [**getScreensById**](docs/Api/ScreensApi.md#getscreensbyid) | **GET** /screens/screensId | Get single screens by ID
*ScreensApi* | [**updateScreen**](docs/Api/ScreensApi.md#updatescreen) | **PUT** /screens/screensId | Update a screen
*ScreensApi* | [**updateScreen_0**](docs/Api/ScreensApi.md#updatescreen_0) | **PUT** /screens/screensId/duplicate | duplicate a screen
*ScriptsApi* | [**createScript**](docs/Api/ScriptsApi.md#createscript) | **POST** /scripts | Save a new script
*ScriptsApi* | [**deleteScript**](docs/Api/ScriptsApi.md#deletescript) | **DELETE** /scripts/scriptsId | Delete a script
*ScriptsApi* | [**getScripts**](docs/Api/ScriptsApi.md#getscripts) | **GET** /scripts | Returns all scripts that the user has access to
*ScriptsApi* | [**getScriptsById**](docs/Api/ScriptsApi.md#getscriptsbyid) | **GET** /scripts/scriptsId | Get single script by ID
*ScriptsApi* | [**getScriptsPreview**](docs/Api/ScriptsApi.md#getscriptspreview) | **GET** /scripts/ew | Returns all scripts that the user has access to
*ScriptsApi* | [**updateScreen**](docs/Api/ScriptsApi.md#updatescreen) | **PUT** /scripts/scriptsId/duplicate | duplicate a script
*ScriptsApi* | [**updateScript**](docs/Api/ScriptsApi.md#updatescript) | **PUT** /scripts/scriptsId | Update a script
*TaskAssignmentsApi* | [**createTaskAssignments**](docs/Api/TaskAssignmentsApi.md#createtaskassignments) | **POST** /task_assignments | Save a new task assignments
*TaskAssignmentsApi* | [**updateTaskAssignments**](docs/Api/TaskAssignmentsApi.md#updatetaskassignments) | **PUT** /task_assignments/{task_assignments_id} | Update a task assignments
*UsersApi* | [**createUser**](docs/Api/UsersApi.md#createuser) | **POST** /users | Save a new users
*UsersApi* | [**deleteUser**](docs/Api/UsersApi.md#deleteuser) | **DELETE** /users/userId | Delete a user
*UsersApi* | [**getUsers**](docs/Api/UsersApi.md#getusers) | **GET** /users | Returns all users
*UsersApi* | [**getUsersById**](docs/Api/UsersApi.md#getusersbyid) | **GET** /users/userId | Get single user by ID
*UsersApi* | [**updateUsers**](docs/Api/UsersApi.md#updateusers) | **PUT** /users/userId | Update a user


## Documentation For Models

 - [Comments](docs/Model/Comments.md)
 - [CommentsEditable](docs/Model/CommentsEditable.md)
 - [EnvironmentVariables](docs/Model/EnvironmentVariables.md)
 - [EnvironmentVariablesEditable](docs/Model/EnvironmentVariablesEditable.md)
 - [GroupMembers](docs/Model/GroupMembers.md)
 - [GroupMembersEditable](docs/Model/GroupMembersEditable.md)
 - [Groups](docs/Model/Groups.md)
 - [GroupsEditable](docs/Model/GroupsEditable.md)
 - [InlineObject](docs/Model/InlineObject.md)
 - [InlineObject1](docs/Model/InlineObject1.md)
 - [InlineObject2](docs/Model/InlineObject2.md)
 - [InlineObject3](docs/Model/InlineObject3.md)
 - [InlineObject4](docs/Model/InlineObject4.md)
 - [InlineResponse200](docs/Model/InlineResponse200.md)
 - [InlineResponse2001](docs/Model/InlineResponse2001.md)
 - [InlineResponse20010](docs/Model/InlineResponse20010.md)
 - [InlineResponse20011](docs/Model/InlineResponse20011.md)
 - [InlineResponse20012](docs/Model/InlineResponse20012.md)
 - [InlineResponse20013](docs/Model/InlineResponse20013.md)
 - [InlineResponse20014](docs/Model/InlineResponse20014.md)
 - [InlineResponse20015](docs/Model/InlineResponse20015.md)
 - [InlineResponse20016](docs/Model/InlineResponse20016.md)
 - [InlineResponse20017](docs/Model/InlineResponse20017.md)
 - [InlineResponse20018](docs/Model/InlineResponse20018.md)
 - [InlineResponse2002](docs/Model/InlineResponse2002.md)
 - [InlineResponse2003](docs/Model/InlineResponse2003.md)
 - [InlineResponse2004](docs/Model/InlineResponse2004.md)
 - [InlineResponse2005](docs/Model/InlineResponse2005.md)
 - [InlineResponse2006](docs/Model/InlineResponse2006.md)
 - [InlineResponse2007](docs/Model/InlineResponse2007.md)
 - [InlineResponse2008](docs/Model/InlineResponse2008.md)
 - [InlineResponse2009](docs/Model/InlineResponse2009.md)
 - [Media](docs/Model/Media.md)
 - [MediaEditable](docs/Model/MediaEditable.md)
 - [Metadata](docs/Model/Metadata.md)
 - [Notifications](docs/Model/Notifications.md)
 - [NotificationsEditable](docs/Model/NotificationsEditable.md)
 - [Process](docs/Model/Process.md)
 - [ProcessCategory](docs/Model/ProcessCategory.md)
 - [ProcessCategoryEditable](docs/Model/ProcessCategoryEditable.md)
 - [ProcessEditable](docs/Model/ProcessEditable.md)
 - [ProcessPermissions](docs/Model/ProcessPermissions.md)
 - [ProcessPermissionsEditable](docs/Model/ProcessPermissionsEditable.md)
 - [ProcessWebhook](docs/Model/ProcessWebhook.md)
 - [ProcessWebhookEditable](docs/Model/ProcessWebhookEditable.md)
 - [Requests](docs/Model/Requests.md)
 - [RequestsEditable](docs/Model/RequestsEditable.md)
 - [ScreenCategory](docs/Model/ScreenCategory.md)
 - [ScreenCategoryEditable](docs/Model/ScreenCategoryEditable.md)
 - [Screens](docs/Model/Screens.md)
 - [ScreensEditable](docs/Model/ScreensEditable.md)
 - [Scripts](docs/Model/Scripts.md)
 - [ScriptsEditable](docs/Model/ScriptsEditable.md)
 - [TaskAssignments](docs/Model/TaskAssignments.md)
 - [TaskAssignmentsEditable](docs/Model/TaskAssignmentsEditable.md)
 - [TaskMetadata](docs/Model/TaskMetadata.md)
 - [Users](docs/Model/Users.md)
 - [UsersEditable](docs/Model/UsersEditable.md)


## Documentation For Authorization


## pm_api_bearer

- **Type**: Bearer authentication


## Author

info@processmaker.com

