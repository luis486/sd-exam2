# Luis Murcia - Examen 2

Desplegar una aplicación simple hecha en Golang, la cual se despliegue a través de un recurso de tipo Deployment y gestione 5 replicas de esa aplicación. Además, la aplicación debería de tener un servicio de tipo ClusterIP para exponer la app. Adicional a eso, crear un healtcheck de tipo livenessprobe para la aplicación. El healtcheck es libre.

use helm para el despliegue de la app

Cada ejercicio debe de ser desplegado en un namespace que contenga el nombre del estudiante. Adicionalmente, para validar que la app funciona se le va a solicitar al estudiante crear un POD de ubuntu el cual haga request a la aplicación a través del DNS que proporciona el servicio asociado a esa app.

### Pasos

1. Se crea una aplicación sencilla en go con el siguiente código:

![image](https://github.com/luis486/sd-exam2/assets/71047563/ae12a6d9-0e76-4ed0-b251-76c9cf276c6f)


2. Se crea un archivo Docerfile para crear el manifiesto y se subió al repositorio de Dockerhub luis486/go

![image](https://github.com/luis486/sd-exam2/assets/71047563/00ad0223-adc4-40af-a8b0-629c04cee6ff)


3.  Luego con el comando helm create se crea la carpeta donde se guardará nuestro chart con las configuraciones propuestas para el examen

![image](https://github.com/luis486/sd-exam2/assets/71047563/3ba970a0-1579-4385-a4e6-ef9912dd5a1c)

4. Se instala el chart con _helm -n luismurcia install go ._  (donde primero debemos crear el namespace como lo conocemos siempre).

5. Por último, se prueba con el comando _kubectl get svc,po,deploy_ y como se tiene el servicio de ClusterIP, se debe hacer un port-forward con _kubectl -n luismurcia port-forward svc/go 8080:8080_ y listo

#### Evidencias

![image](https://github.com/luis486/sd-exam2/assets/71047563/afe0149a-9072-43a1-a174-11435bf65371)

![image](https://github.com/luis486/sd-exam2/assets/71047563/94d8da43-533e-4de3-9a6b-d53cbb617d4e)



