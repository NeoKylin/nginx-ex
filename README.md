# Nginx HTTP server and reverse proxy (nginx) S2I Sample Application

This is a very basic sample application repository that can be built and deployed
on [OpenShift](https://www.openshift.com) using the [Nginx HTTP server and a reverse proxy builder image](http://10.1.60.22/NCCP/nginx-container).

The application serves a single static html page via nginx.

To build and run the application:

```
$ s2i build http://10.1.60.22/NCCP/nginx-ex cs2cdocker/nginx-112-neokylin7 mynginximage
$ docker run -p 8080:8080 mynginximage
$ # browse to http://localhost:8080
```

You can also build and deploy the application on OpenShift, assuming you have a
working `oc` command line environment connected to your cluster already:

`$ oc new-app cs2cdocker/nginx-112-neokylin7~http://10.1.60.22/NCCP/nginx-ex`

You can also deploy the sample template for the application:

`$ oc new-app -f http://10.1.60.22/NCCP/nginx-ex/master/openshift/templates/nginx.json`
