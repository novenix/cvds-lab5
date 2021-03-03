cvds-lab5
parte2

3. Revise en el pom.xml para qué puerto TCP/IP está configurado el servidor embebido de Tomcat (ver sección de plugins).

puerto 8080

4. Compile y ejecute la aplicación en el servidor embebido Tomcat, a través de Maven con:

mvn package
mvn tomcat7:run

10. Recompile y ejecute la aplicación. Abra en su navegador en la página del formulario, y rectifique que la página hecha anteriormente sea mostrada. Ingrese los datos y verifique los resultados. Cambie el formulario para que ahora en lugar de POST, use el método GET . Qué diferencia observa?
GET= llega como param a la pagina que creamos 
POST= se envia por debajo, no llega como param

pruebas calculadora
Si todo funcionó correctamente, realice las siguientes pruebas:
http://localhost:8080/faces/calculadora.xhtml

- Abra la aplicación en un explorador. Realice algunas pruebas de aceptación con la aplicación.
[](/images/aceptacion1.PNG)

- Abra la aplicación en dos computadores diferentes. Si no dispone de uno, hágalo en dos navegadores diferentes (por ejemplo Chrome y Firefox; incluso se puede en un único navegador usando una ventana normal y una ventana de incógnito / privada). Haga cinco intentos en uno, y luego un intento en el otro. ¿Qué valor tiene cada uno?
los mismos
[](/images/aceptacion2.PNG)

- Aborte el proceso de Tomcat-runner haciendo Ctrl+C en la consola, y modifique el código del backing-bean de manera que use la anotación @SessionScoped en lugar de @ApplicationScoped. Reinicie la aplicación y repita el ejercicio anterior.
Dado la anterior, ¿Cuál es la diferencia entre los backing-beans de sesión y los de aplicación?
la diferencia es que aplicacition scoped hace que el bean mientras que la apliacion este viva o el servidor este vivo, y el sessionscoped funcionara mientras que la sesion este viva

-Por medio de las herramientas de desarrollador del explorador (Usando la tecla "F12" en la mayoría de exploradores):
Ubique el código HTML generado por el servidor.
[](/images/aceptacion3.PNG)
Busque el elemento oculto, que contiene el número generado aleatoriamente.(supongo que el de la moda porque nunca se hablo de un numero aleatorio)
[](/images/aceptacion4.PNG)
En la sección de estilos, deshabilite el estilo que oculta el elemento para que sea visible.
[](/images/aceptacion5.PNG)
Observe el cambio en la página, cada vez que se realiza un cambio en el estilo.
- Revise qué otros estilos se pueden agregar a los diferentes elementos y qué efecto tienen en la visualización de la página.
se pueden aplicar muchos estilos, para que se vea mas bonito
- Actualice la página. Los cambios de estilos realizados desaparecen, pues se realizaron únicamente en la visualización, la respuesta del servidor sigue siendo la misma, ya que el contenido de los archivos allí almacenados no se ha modificado.
cuando se actualiza se vuelve a cargar el xhtml a lo cual los estilos que se pongan en la ventana del desarrollador no se guardan
- Revise qué otros cambios se pueden realizar y qué otra información se puede obtener de las herramientas de desarrollador.
se puede obtener informacion de red,cuando esxiste codigo javascript se puede obtener el codigo en sources, se puede tener la consola para ver warnings de ejecucion de la pagina web asi como para correr comandos, entre otros