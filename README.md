# Disk Space Plugin
This plugin allows to get information about disk space in Android / iOS / Windows 10 platforms.

## Installation
To use this plugin in a project, you have to do:

	cordova plugin add https://github.com/sqli/sqli-cordova-disk-space-plugin.git

Add your platforms targeted:

	cordova platform add android
	cordova platform add ios
	cordova platform add windows

## Usage

1- You can get disk information by executing the info function:

	DiskSpacePlugin.info(options, successCallback, errorCallback);

Where options is a javascript object:

	location: 1
		// To get information about external storage (For Android only)
	location: 2
		// or missing, or any other value (default)
		// To get information about internal storage (For Android only)

	appFilesPath: cordova.file.dataDirectory
	appFilesPath: cordova.file.externalDataDirectory
		// examples using cordova-plugin-file constants here, but can be any path to other app's `files`
		// To get information about any storage by path, like internal, external, or removable externals / SD cards (For Android only)

The result object is like that:

	{
		"app": 29887, // Space occupied by the current application
		"total": 98717873000, // Total space of the storage
		"free": 76556280  // Free space of the storage
	}
