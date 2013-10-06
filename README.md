simple_service_webapp
================

Taller de Programación 2: Prueba de concepto para la interacción entre la capa de Usuario y Presentación

# Documentación POC client-server tp taller 2

Requerimientos:


	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install maven
	sudo apt-get install tomcat7
	sudo apt-get install tomcat7-admin 

Agregar usuarios en el conf file "tomcat-users.xml", ie:
	
    <role rolename="admin-gui"/>
    <user username="admin" password="admin" roles="admin-gui"/>

Recursos:

	http://www.mkyong.com/webservices/jax-rs/jersey-hello-world-example/
	http://blog.bdoughan.com/2010/08/creating-restful-web-service-part-55.html
	http://maven.apache.org/guides/getting-started/maven-in-five-minutes.html
	http://www.techzoo.org/how-to/restful-java-web-service-with-xml-response.html
	http://www.techzoo.org/how-to/how-to-create-simple-rest-web-service-using-jersey.html
	http://www.techzoo.org/tutorials/java-tutorials/consuming-restful-web-service-using-jquery-ajax-client.html
	
	https://jersey.java.net/
	https://jersey.java.net/documentation/latest/index.html

	http://www.w3schools.com/xml/xml_http.asp
	


Eclipse: 
	http://www.eclipse.org/downloads/packages/eclipse-standard-431/keplersr1

	- plugins desde eclipse_marketplace o "install new software":
	
  		m2eclipse
  		Web XML, Jave EE,... (algunos paquetes se pueden sacar)

	- Si da error al importar el projecto (click derecho->import->maven project), hacer en approot/ :
		  mvn eclipse:clean
	
	- Setearlo como DWM:
  
	  http://blog.teamextension.com/maven-as-eclipse-dynamic-web-module-556

Si se quiere hacer el deploy desde el eclipse:

	http://stackoverflow.com/questions/13423593/eclipse-4-2-juno-cannot-create-a-server-using-the-selected-type-in-tomcat-7

Si se quiere hacer el deploy manualmente:

	- Dentro de la carpeta root de la aplicacion ejecutar:
		mvn clean package && sudo cp ./target/simple-service-webapp.war /usr/share/tomcat7/webapps/

	- Hacer el deploy del war en tomcat


Para hacer el deploy a heroku:
  https://devcenter.heroku.com/articles/war-deployment
  
  
  
 Y las vistas??
 
 Se decidió no trabajar con JSP ni templates del lado del servidor, or lo que este expone unicamente una api REST. Las vistas, entonces, se manejaran con client-side templates. A continuación algo de info al respecto:
 
 http://codebrief.com/2012/01/the-top-10-javascript-mvc-frameworks-reviewed/
 http://engineering.linkedin.com/frontend/leaving-jsps-dust-moving-linkedin-dustjs-client-side-templates
 http://engineering.linkedin.com/frontend/client-side-templating-throwdown-mustache-handlebars-dustjs-and-more
 http://www.bymichaellancaster.com/blog/basic-overview-of-client-side-templating/
 
 La idea del templating es hacer GET/POST al server, recibiendo y enviando JSON únicamente o xml si es necesario.
 
