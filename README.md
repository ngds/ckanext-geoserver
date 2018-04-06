###Geoserver Extension for CKAN

custom configurations:

- geoserver.rest_url = 'geoserver://admin:geoserver@localhost:8080/geoserver/rest'
- geoserver.default_workspace = 'ckan'
- geoserver.workspace_name = ckan
- geoserver.workspace_uri = 'http://localhost:5000/ckan'

Also requires this to be set:

ckan.datastore.write_url = 'postgresql://ckanuser:pass@localhost/datastore'

## Debugging

Every time you pull new changes into your existing repository, you should restart services to make sure all the files are compiled. You can use the following command for this:

```
$ supervisorctl restart all
```
If you run into issues while pulling new changes into your existing repository, you should run setup.py which will set up the environment correctly. See below:

```
$ python setup.py egg_info
```
Also, if you run into issues with the website being inaccessible, you can restart the http service by using the following command:

```
$ service httpd restart
```
