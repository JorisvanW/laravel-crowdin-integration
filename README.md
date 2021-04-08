# Laravel-Crowdin Integration
Automate uploading/downloading translations 
## Installation

Install the package via composer:

```composer require georgii-web/laravel-crowdin-integration --dev```

By default, the package uses the following environment variables
```
CROWDIN_PROJECT_ID
CROWDIN_API_KEY
```
  
## Config Files

In order to edit the default configuration for this package you may execute:

```
php artisan vendor:publish --provider="MacPaw\LaravelCrowdinIntegration\CrowdinServiceProvider"
```

After that, `config/crowdin.php` will be created. Inside this file you will find all the fields that can be edited in this package.

## Full scenario
Add/update lang-file from "/resources/lang/en/{file}" to crowdin.com, translate and <b>approve</b> rows there, download translates to the projects "/resources/lang/{language}/{file}".
### Commands
```
php artisan crowdin:add/update default.php
```
Translate and approve it on the crowdin.com
```
php artisan crowdin:download
```
Check translation in "/resources/lang/{language}/default.php"

### FYI
> If row was deleted in file, after update it'll be deleted in crowdin.com too.
> Only approved rows wil be downloaded to the project.

## Usage

You can see all the commands in the list of command:
```
php artisan list
```
### Add File
Add a file from project to Crowdin repository:
```
php artisan crowdin:add {fileName.ext}
```
> It is work only for adding file, not for updating
### Update File
Update exist file from project to Crowdin repository
```
php artisan crowdin:update {fileName.ext}
```
> It is work only for updating file, not for adding
### Upload File
This is command add or update all origin files from a project in Crowdin repository:
```
php artisan crowdin:upload
```
> No matter file exists or not in Crowdin repository
### Build 
Build ZIP archive with the latest translations.
```
php artisan crowdin:build
```
### Download Files
Download translations files from Crowdin repository to your.
```
php artisan crowdin:download
```
