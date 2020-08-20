
# **Laboratorio N°2**
## **CVDS-1**
### **Ciclos de Vida del Desarrollo de Software**

![](https://github.com/DonSantiagoS/LAB2CVDS/blob/master/Imagenes/Logo.png) "Logo"


## _Maven_

La herramienta Apache Maven se usa para gestionar y manejar proyectos de software. La base de maven para un proyecto es el concepto de un modelo de objeto de proyecto (POM), Maven puede gestionar la compilación, los informes y la documentación de un proyecto a partir de este modelo, que se concreta en el archivo pom.xml.
Tomado de [Apache Maven][2]

**•	Cuál es su mayor utilidad**
Hasta que Maven ofreció un marco popular para la creación de aplicaciones, cada proyecto solía tener a alguien dedicado exclusivamente a configurar el método de creación.
Además, los desarrolladores tenían que perder tiempo aprendiendo las peculiaridades de cada nuevo proyecto en el que participaban.
**•	Fases de Maven**
Las fases que componen cada ciclo de vida también están predefinidas; Dado que cada fase es responsable de un paso particular del ciclo de vida al que se refiere, la forma en que se llevan a cabo dichas tareas puede diferir según el tipo de proyecto. Para configurar lo que se logra en cada proceso, cada paso está conectado a uno o más objetivos del complemento. Por lo tanto, ejecutar un paso del ciclo de vida equivale a ejecutar los objetivos de los complementos vinculados a ese proceso. Algunas fases ya tienen objetivos de complementos relacionados por diseño. Esta vinculación varía según el tipo de embalaje del proyecto.
Las fases principales de Maven son las siguientes:

1.Validar: Revisar si toda la información necesaria para el constructor esta disponible.
2.Compilar: Compilar el código base.
3.Compilar-test: Compilar los tests del código base.
4.Test: Compilar pruebas de Unidad.
5.Package: Paquete del código compilado en el formato seleccionado (jar, entre otros).
6.Test de Integración: Procesa y despliega el paquete si necesita correr pruebas de integración.
7.Instalación: Instala el paquete en un repositorio local.
8.Despliegue: Copiar el paquete en un repositorio local.

Tomado de [BealDung][3]

**•	Ciclo de vida de la construcción**
El otro principio básico de Maven para manejar el desarrollo de un proyecto es el ciclo de vida. Un ciclo de vida consta de una serie de etapas. En Maven se definen tres ciclos de vida por defecto y normalmente nunca verá la necesidad de definir otros adicionales. Los tres ciclos de vida de Maven son:

* El ciclo de vida default, que gestiona la construcción y despliegue del proyecto.
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Ciclo1.PNG) "CICLO"
* El ciclo de vida clean, que gestiona la limpieza del directorio del proyecto. Es decir, se encarga de eliminar todos los archivos generados en el proceso de construcción y despliegue.
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Ciclo2.PNG) "CICLO"
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Ciclo2-1.PNG) "CICLO"
* El ciclo de vida site, que gestiona la creación de la documentación del proyecto.
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Ciclo3.PNG) "CICLO"

### **•	Para qué sirven los plugins**

Toda la funcionalidad de Maven se realiza mediante complementos. Existen plugins encargados de manejar dependencias, plugins encargados de compilar código Java, plugins encargados de ejecutar pruebas JUnit, plugins encargados de cargar el código en formato JAR, etc. Los plugins entregan su funcionalidad por lo que se conoce como objetivos .

### **•	Qué es y para qué sirve el repositorio central de maven**

Maven tiene un repositorio remoto (Maven central) donde se almacenan la mayoría de las bibliotecas utilizadas en las innovaciones de software y donde se descarga la herramienta en sí cuando es apropiado. 



### **•	Crear un Proyecto con Maven**
```
mvn archetype:generate
```
Es posible crear un proyecto con Parametros definidos

Grupo: edu.eci.cvds
o	Id del Artefacto: Patterns
o	Paquete: edu.eci.cvds.patterns
o	archetypeArtifactId: maven-archetype-quickstart
```
mvn archetype:generate -DgropuId=edu.eci.cvds -DartifactId=Patterns -DarchetypeArtifactId=maven-archetype-quickstart -Dpackage=edu.eci.cvds.patterns -DinteractiveMode=false
```
### **Configuracion de la version Java**

 cambiar la version del compilador de Java a la versión 8, para ello, agregue la sección properties antes de la sección de dependencias
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Configuracion.PNG) "Configuracion"

### **Comandos basicos de Maven**

+mvn clean Borra todos los .class y .jar generados.
+mvn compile Compila el proyecto.
+mvn package Genera el jar.
+mvn install LLeva el jar a nuestro repositorio local de jars. Queda "visible" para otros proyectos maven en nuestro ordenador.
+mvn deploy Lleva el jar a nuestro servidor de jars. Queda "visible" para otros proyectos maven en otros ordenadores. Este comando necesita que a maven se le haya indicado dónde está dicho servidor de jars.
+mvn javadoc:javadoc Genera la documentación javadoc de nuestro proyecto.
+mvn site Genera documentación html del proyecto. Por supuesto, necesitamos haber escrito en determinados ficheros el contenido de esa documentación.

Tomado de [chuwiki][4]
•	Busque cómo ejecutar desde línea de comandos, un proyecto maven y verifique la salida cuando se ejecuta con la clase App.java como parámetro en "mainClass
```
mvn exec:java -Dexec.mainClass="edu.eci.cvds.patterns.App"
```
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Evidencia1.PNG) "Evidencia"
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Evidencia2.PNG) "Evidencia"
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Evidencia3.PNG) "Evidencia"

### Primera ejecucion sin parametros
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Ejecucion1.PNG) "Ejecucion"
### segunda ejecucion "qwerty"
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Ejecucion2.PNG) "Ejecucion"
### Tercera ejecucion "pentagon"
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Ejecucion3.PNG) "Ejecucion"
### Cuarta ejecucion "Hexagon"
![](https://github.com/DonSantiagoS/LAB2CVDS/Imagenes/Ejecucion4.PNG) "Ejecucion"

### **Gitignore**

Git tiene una herramienta importante en casi todos los proyectos, el archivo "gitignore", que se usa para indicar que los archivos o directorios completos de Git deben ignorarse y no agregarse al repositorio de código.

Su implementación es bastante básica, por lo que no hay razón para no usarlo en ningún proyecto y para cualquier nivel de conocimiento de Git que tenga el desarrollador. Solo necesita construir un archivo que defina qué elementos deben pasarse por alto y luego realizar el resto del procedimiento para operar con Git normalmente.

Todas las rutas y archivos que no sean necesarios se enumerarán en gitignore y, por lo tanto, el proceso de control de versiones simplemente ignorará esos archivos.

Tomado de [Gitignore][1]

##### Autores:
 * Santiago Buitrago
 * Andres Cubillos

[1]:https://desarrolloweb.com/articulos/archivo-gitignore.html#:~:text=Qu%C3%A9%20es%20el%20archivo%20gitignore,subir%20al%20repositorio%20de%20c%C3%B3digo.
[2]:https://maven.apache.org/
[3]:https://www.baeldung.com/maven-goals-phases
[4]:http://chuwiki.chuidiang.org/index.php?title=Tareas_b%C3%A1sicas_de_Maven
