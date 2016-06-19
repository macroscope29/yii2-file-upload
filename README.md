# Yii2 File Upload

[![Stable Version](https://poser.pugx.org/vlaim/yii2-file-upload/v/stable)](https://packagist.org/packages/vlaim/yii2-file-upload) [![License](https://poser.pugx.org/vlaim/yii2-file-upload/license)](https://packagist.org/packages/vlaim/yii2-file-upload)

**Yii2 FileUpload** – PHP library for uploading files to your server or [Amazon S3](https://aws.amazon.com/ru/documentation/s3). It makes easy for developers to handle with yii2 UploadedFile instances. It's also possible to upload files via URLs.

## Getting Started

### Installation

The preferred way to install this extension is through [composer](https://getcomposer.org/download/).

> Note: Check the [composer.json](https://github.com/kartik-v/yii2-mpdf/blob/master/composer.json) for this extension's requirements and dependencies. Read this [web tip /wiki](http://webtips.krajee.com/setting-composer-minimum-stability-application/) on setting the `minimum-stability` settings for your application's composer.json.

Either run

`$ php composer.phar require vlaim/yii2-file-upload "dev-master"`

or add

`"vlaim/yii2-file-upload": "dev-master"`

to the `require` section of your `composer.json` file.

## Quick Examples

### Do not forget include Composer autoloader and define namespace for library

`php require 'vendor/autoload.php'; use vlaim\fileupload\FileUpload;`

### Upload a file to your local server

`php //... $photo = UploadedFile::getInstance($model, 'photo'); $uploader = new FileUpload(FileUpload::S_LOCAL);`

### Upload a file to Amazon S3

This code uploads a file to Amazon S3\. You must provide an associative array as second argument in FileUpload constructor.

`php //... $photo = UploadedFile::getInstance($model, 'photo'); $uploader = new FileUpload(FileUpload::S_S3,[ 'version' => 'latest', 'region' => '<regiongoeshere>', 'credentials' => [ 'key' => '<keygoeshere>', 'secret' => '<secretgoeshere>' ], 'bucket'=>'<bucketgoeshere>' ]);`

## Methods

### setUploadFolder(string $folder)

Sets folder name in which files will be uploaded to.

**Default to 'uploads'**

`php $uploader->setUploadFolder('photos');`

### setFsPath(string $fsPath)

Sets path in which files will be uploaded to. **(Local mode)**

**Default to '/'**

`php $uploader->setFsPath('/var/www/path/to/your/app/');`

### setFsUrl(string $url)

Sets path in which files will be uploaded to. **(Local mode)** For example, if you set path to 'http://static.example.com' File after uploading will have URL http://static.example.com/pathtoyourfile

**Default to '/'** `php $uploader->setFsPath('http://pathtoyoursite.com');`

### useTreeStructure(boolean $treeStructure)

### hashFilename(boolean $hash)

Defines **Default to true**

`php $uploader->hashFilename(false);`

## License

**yii2-file-upload** is released under the MIT License. See the bundled LICENSE.md for details.