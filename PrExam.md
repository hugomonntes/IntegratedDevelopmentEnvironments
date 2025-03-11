# Resumen de los Temas 4 y 5

## Tema 4: Packages e introducción a Maven

### **1. ¿Qué son los Packages en Java?**
- Son un sistema de organización de código.
- Permiten reutilizar código sin copiar/pegar.
- Facilitan la modularización y evitan conflictos entre clases.
- Se definen con la sentencia `package nombre_del_paquete;` al inicio del archivo.
- Se importan con `import nombre_del_paquete.Clase;` o `import nombre_del_paquete.*;`.

### **2. Creación y uso de Packages en Java**
1. **Estructura del proyecto**
   - Crear una carpeta con el nombre del proyecto (`ProyectoAreas`).
   - Dentro de esta, crear dos carpetas: `milibreria` y `app`.
   - `milibreria` contendrá las clases de utilidad.
   - `app` contendrá la clase principal.

2. **Ejemplo de código**
   - `Areas.java` dentro de `milibreria`:
     ```java
     package milibreria;
     public class Areas {
         public static double circulo(double radio) {
             return Math.PI * radio * radio;
         }
     }
     ```
   - `Principal.java` dentro de `app`:
     ```java
     package app;
     import milibreria.Areas;
     public class Principal {
         public static void main(String[] args) {
             System.out.println("Área de un círculo de radio 5: " + Areas.circulo(5));
         }
     }
     ```

3. **Compilación y ejecución desde la terminal**
   ```sh
   cd ProyectoAreas
   javac app/Principal.java
   java app.Principal
   ```

---

### **3. Introducción a Maven**
- Herramienta para la gestión de proyectos en Java.
- Automatiza la compilación, prueba y distribución del código.
- Usa el archivo `pom.xml` para la configuración del proyecto.
- Instalación en Linux:
  ```sh
  sudo apt update
  sudo apt install maven
  mvn -v  # Para comprobar la instalación
  ```

### **4. Creación de un proyecto Maven**
1. **En VSCode:**
   - Paleta de comandos → `Java: Create Java Project → Maven Create from archetype`.
   - Elegir un arquetipo (ejemplo: `maven-archetype-quickstart`).
   - Definir `groupId`, `artifactId` y `version`.

2. **Estructura del proyecto Maven**
   - `src/main/java/` → Código fuente.
   - `src/test/java/` → Pruebas unitarias.
   - `target/` → Código compilado.
   - `pom.xml` → Archivo de configuración de Maven.

3. **Comandos básicos de Maven**
   ```sh
   mvn clean        # Borra archivos compilados
   mvn compile      # Compila el código fuente
   mvn package      # Genera el archivo JAR
   ```

---

## Tema 5: Otros aspectos de la ingeniería del software

### **5. Ingeniería de la Usabilidad**
- El usuario es el centro del desarrollo de software.
- Se debe optimizar la experiencia del usuario (UX) y la interfaz de usuario (UI).
- Factores clave:
  - **Fácil de aprender** → Intuitivo para nuevos usuarios.
  - **Flexible** → Se adapta a diferentes usuarios y configuraciones.
  - **Sólido** → Libre de errores y con feedback claro.

### **6. Lenguajes de programación**
- **Lenguaje de máquina**: Código binario que entiende la CPU.
- **Ensamblador**: Lenguaje de bajo nivel con mnemónicos (ejemplo: `ADD AX, BX`).
- **Alto nivel**: Más cercano al lenguaje humano (ejemplo: Java, Python, C++).
- **Lenguajes compilados vs. interpretados**:
  - **Compilados**: Se traducen a código máquina antes de ejecutarse (C, C++).
  - **Interpretados**: Se traducen línea por línea en tiempo de ejecución (Python, JavaScript).
  - **Máquina virtual**: Intermedio, compila a un bytecode ejecutable en una máquina virtual (Java, C#).

### **7. Tipos de programación**
- **Convencional**: Código desordenado, difícil de mantener.
- **Modular**: Divide el código en módulos independientes.
- **Estructurada**: Usa estructuras de control (secuencia, selección, repetición).
- **Imperativa**: Basada en instrucciones y algoritmos.
- **Orientada a Objetos (POO)**: Organiza el código en clases y objetos.

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
   
