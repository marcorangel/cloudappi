![alt text](http://rangelmarco.com/images/logo.png) 
# Code Challenge - DevOps - Marco Rangel

## Sumario
Instalación y Configuracion de una instancia en AWS como server nodejs para una api, utilizando un [swagger](https://gitlab.com/marcorangel/cloudappi/tree/master/api)

La api obedece peticiones GET, POST, PUT, DELETE

```
http://rangelmarco.com
```

La instancia se autoescala al sobrepasar 10% del uso de la CPU. Para esto se genero un script de estrés en [jMeter](https://gitlab.com/marcorangel/cloudappi/blob/master/jMeter) 


## Recursos y Herramientas
*  EC2 AWS
*  Launch configuration AWS
*  Auto scaling group AWS
*  CloudFormation AWS
*  CloudWatch AWS
*  Gitlab, Git
*  Jmeter
*  Postman
*  Ansible (proceso de documentación y aprendizaje)


## Deployed
Se configuro y personalizo una Ami con ubuntu 18, nodejs, npm, para luego ser utilizada como plantilla al Launch Configuration. El autoescalado inicialmente parte con una instancia t2.micro en la region de Irlanda. Auto scaling group esta configurado con un minimo 1 instacia y máximo 2, al sobrepasar el 10 % de uso del CPU lanza una segunda instancia y al decrementase elimina el auto scaling elimina la mas nueva conservando la original. Todas las metricas son visibles en CloudWatch. Para el código de esta infraestructura se utilizo [CloudFormation](https://gitlab.com/marcorangel/cloudappi/tree/master/cloudFormation)

La api se pude observar en: http://rangelmarco.com

Peticiones de la api:
```
http://rangelmarco.com/users/getusers
http://rangelmarco.com/users/getusersById/1

```
Toda la gestión, automatización, versiones y procesos del proyecto esta desplegada en Gitlab. [Jmeter](https://gitlab.com/marcorangel/cloudappi/blob/master/jMeter) es la herramienta utilizada para crear cargas al server y comprobar el autoescalado.

Las peticiones GET, POST, PUT, DELETE se pueden apreciar mejor con un collection en [Postman](https://gitlab.com/marcorangel/cloudappi/tree/master/postman)

Actualmente me estoy documentando en Ansible, a pesar que realice unas pruebas infructuosa para este proyecto, preferi no compartir el YML.

## Resultados
*  URL => http://rangelmarco.com
*  Gitlab => https://gitlab.com/marcorangel/cloudappi
*  CloudFormation => https://gitlab.com/marcorangel/cloudappi/tree/master/cloudFormation
*  Jmeter => https://gitlab.com/marcorangel/cloudappi/blob/master/jMeter
*  Postman => https://gitlab.com/marcorangel/cloudappi/tree/master/postman

