# Repository Apps Templates for Portainer.

## Build and host your own templates
You can build your own container that will use Nginx to serve the templates definitions.

Clone the Portainer templates repository, edit the templates file, build and run the container:

```
$ git clone https://github.com/Vozro/portainer-templates.git portainer-templates
$ cd portainer-templates
# Edit the file templates.json
$ docker build -t portainer-templates .
$ docker run -d -p "8080:80" portainer-templates
```
Now you can access your templates definitions at http://docker-host:8080/templates.json.


You can also mount the templates.json file inside the container, so you can edit the file and see live changes:

```
$ docker run -d -p "8080:80" -v "${PWD}/templates.json:/usr/share/nginx/html/templates.json" portainer-templates
```
