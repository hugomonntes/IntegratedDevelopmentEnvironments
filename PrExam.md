# Resumen de los Temas 4 y 5 IDE DAM

## Tema 4: Packages e introducción a Maven

### **1. ¿Qué son los Packages en Java?**
- Un **package** es una agrupación lógica de clases relacionadas dentro de un mismo directorio.
- Permiten organizar mejor los proyectos, evitar conflictos entre clases con el mismo nombre y reutilizar código sin necesidad de copiarlo manualmente.
- Java ya viene con paquetes estándar como `java.util`, `java.io`, etc.
- Se definen con la sentencia `package nombre_del_paquete;` al inicio del archivo.
- Para usar clases de otros paquetes, se debe importar con `import nombre_del_paquete.Clase;` o `import nombre_del_paquete.*;` para importar todas las clases del paquete.

### **2. Creación y uso de Packages en Java**

1. **Estructura del proyecto con Packages**
   - Supongamos que queremos hacer un programa que calcule áreas de figuras.
   - Creamos una carpeta llamada `ProyectoAreas` y dentro de ella dos subcarpetas:
     - `milibreria`: Contendrá clases con funciones de cálculo.
     - `app`: Contendrá la clase principal que usará esas funciones.

2. **Ejemplo de código**
   - `Areas.java` dentro de `milibreria`:
     ```java
     package milibreria;
     public class Areas {
         public static double circulo(double radio) {
             return Math.PI * radio * radio;
         }
         public static double rectangulo(double base, double altura) {
             return base * altura;
         }
     }
     ```
   - `Principal.java` dentro de `app`:
     ```java
     package app;
     import milibreria.Areas;
     public class Principal {
         public static void main(String[] args) {
             double areaCirculo = Areas.circulo(5);
             System.out.println("Área de un círculo de radio 5: " + areaCirculo);
         }
     }
     ```

3. **Compilación y ejecución desde la terminal**
   ```sh
   cd ProyectoAreas
   javac app/Principal.java
   java app.Principal
   ```
   - Es importante compilar desde la raíz del proyecto para que Java pueda encontrar los paquetes correctamente.

---

### **3. Introducción a Maven**
- Maven es una herramienta para la gestión y automatización de proyectos en Java.
- Se encarga de compilar, ejecutar pruebas y empaquetar el código.
- Usa un archivo de configuración (`pom.xml`) para definir dependencias, configuración del proyecto y plugins.
- **Ventajas de Maven:**
  - Organización automática del proyecto.
  - Gestión eficiente de dependencias.
  - Integración con IDEs y herramientas de CI/CD.

### **4. Instalación y uso básico de Maven**

1. **Instalación en Linux:**
   ```sh
   sudo apt update
   sudo apt install maven
   mvn -v  # Para comprobar la instalación
   ```

2. **Creación de un proyecto Maven en VSCode:**
   - Ir a la **Paleta de Comandos** → `Java: Create Java Project → Maven Create from archetype`.
   - Elegir un arquetipo (`java11-classic`).
   - Configurar:
     - `groupId`: Identificador único del grupo o empresa.
     - `artifactId`: Nombre del proyecto.
     - `version`: Número de versión del proyecto.

3. **Estructura del proyecto Maven:**
   - `src/main/java/` → Código fuente.
   - `src/test/java/` → Pruebas unitarias.
   - `target/` → Código compilado.
   - `pom.xml` → Configuración del proyecto.

4. **Comandos básicos de Maven:**
   ```sh
   mvn clean        # Borra archivos compilados
   mvn compile      # Compila el código fuente
   mvn package      # Genera el archivo JAR
   ```

---

## Tema 5: Otros aspectos de la ingeniería del software

### **5. Ingeniería de la Usabilidad**
- La **usabilidad** es la facilidad con la que un usuario puede interactuar con un software.
- **Objetivo:** Hacer sistemas intuitivos, eficientes y accesibles.
- Factores clave:
  - **Facilidad de aprendizaje**: Debe ser comprensible sin necesidad de formación extensa.
  - **Eficiencia**: Permitir que el usuario realice tareas con rapidez.
  - **Satisfacción**: Que el usuario disfrute la experiencia de uso.

### **6. Lenguajes de programación**
- **Lenguaje de máquina**: Código binario que entiende la CPU.
- **Lenguaje ensamblador**: Representación mnemónica del lenguaje de máquina.
- **Lenguajes de alto nivel**:
  - **Compilados**: Traducidos a código máquina antes de ejecutarse (C, C++).
  - **Interpretados**: Se traducen en tiempo de ejecución (Python, JavaScript).
  - **Máquina virtual**: Compilan a bytecode ejecutado por una máquina virtual (Java, C#).

### **7. Tipos de programación**
- **Modular**: Divide el código en módulos independientes.
- **Estructurada**: Se basa en secuencia, selección y repetición.
- **Orientada a Objetos (POO)**: Usa clases y objetos para estructurar el código.

### **8. Creación de un JAR con Maven**
1. **Configurar `pom.xml` para definir la clase principal:**
   ```xml
   <build>
       <plugins>
           <plugin>
               <artifactId>maven-jar-plugin</artifactId>
               <configuration>
                   <archive>
                       <manifest>
                           <mainClass>app.Principal</mainClass>
                       </manifest>
                   </archive>
               </configuration>
           </plugin>
       </plugins>
   </build>
   ```
2. **Generar el JAR:**
   ```sh
   mvn package
   ```
3. **Ejecutar el JAR:**
   ```sh
   java -jar target/proyecto_areas-1.0-SNAPSHOT.jar
