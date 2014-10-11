phpUpdateSystem
===============

### Description
phpUpdateSystem is an script that makes updating versions easier for php system.
The script uses a server where you have all the different versions of your php system, also a client class that can help you to build an auto-update feature.

### Requeriments
* PHP5
* cURL

### Usage
1. Create a folder in a server that contains:
  * A version.txt file which includes the last version of your system
  * A sub-folder for each version you release, eachone includes a package.zip file (that has an snapshot of that version) and an update.php file (that gets executed when the system is upgraded to that version)
2. Include the Updater Class (class.updater.php) in your client and create an object to update it.
3. You can see an example about how it works at example/ folder

### Updater Class
* **connect(server_url)** connects to the server url; returns *true* if succeed, else returns a string with the error
* **get_last_version()** returns the last version of the system (server_url/version.txt). It must be already connected
* **is_last(actual_version)** returns true if the version passed as parameter is the lastest
* **upgrade(actual_version, root_path, options_array)** it upgrades de system located in folder *root_path* which as the version *actual_version* and *options_array* is an array of custom properties that can be used by *update.php* located in the server that will be executed. It returns *true* if succeed, otherwise it will return a string with the error


### License and Credits
Created by Ivan Diaz under MIT License.
