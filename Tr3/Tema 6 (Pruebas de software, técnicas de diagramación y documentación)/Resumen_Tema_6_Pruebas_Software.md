# 📘 Tema 6 – Pruebas de Software, Técnicas de Diagramación y Documentación

## 🧪 Pruebas de Software

Las pruebas de software son una fase crítica en el desarrollo, donde se valida el comportamiento del código y se buscan errores antes de la entrega final. La idea clave es que **encontrar un error es un éxito**, ya que mejora la calidad del producto.

### Tipos de pruebas:

- **Pruebas unitarias**: Validan unidades individuales del código, como funciones o clases. Se ejecutan tras compilar el código y se centran en la lógica. Se utilizan herramientas como JUnit en Java.
- **Pruebas de estrés**: Evalúan la estabilidad de sistemas bajo cargas extremas.
- **Pruebas de integración**: Combinan módulos desarrollados por diferentes personas para verificar su interoperabilidad.
- **Pruebas funcionales**: Comprueban si el sistema cumple con los requerimientos especificados.
- **Pruebas de aceptación**: Realizadas por el cliente final para valorar aspectos funcionales y subjetivos como la usabilidad o estética.
  - **Alfa**: Supervisadas por el desarrollador, realizadas en su entorno.
  - **Beta**: Realizadas en el entorno real del cliente.

## ⚖️ Caja Blanca vs Caja Negra

### Caja Blanca:

Este enfoque prueba el código internamente, siguiendo todas sus ramas y condiciones. Se analiza con técnicas como la complejidad ciclomática. Es útil para software crítico (médico, nuclear, etc.).

### Caja Negra:

Se prueba desde fuera, sin ver el código. Solo se analiza la entrada y la salida. Se construyen **casos de prueba** con:
- **Valores válidos**
- **Valores inválidos**
- **Casos límite (fronteras)**

Ejemplo: Para una función que acepta números entre 1 y 100:
- Incluir: 0, 1, 100, 101, strings, negativos, etc.

## ⚙️ Automatización con JUnit

**JUnit 5** es un framework de pruebas para Java. Permite definir y ejecutar pruebas automatizadas.

### Uso básico:
- Crear clases de prueba dentro del paquete `src/test/java`.
- Decorar funciones con `@Test`.
- Utilizar `assert` para validar resultados:
  - `assertEquals`, `assertTrue`, `assertFalse`
  - `assertThrows` para excepciones

### Ciclo de vida:
- `@BeforeAll` y `@AfterAll`: Ejecutan código antes y después de todos los tests.
- `@BeforeEach` y `@AfterEach`: Ejecutan antes y después de cada test.

### Otros aspectos:
- **@Timeout**: Límite de tiempo por test.
- **@Disabled**: Desactiva temporalmente un test.
- **Mocking**: Se usan objetos falsos para simular partes del sistema aún no implementadas. Herramientas como Mockito pueden facilitar esto.

## 🔄 Diagramas de Flujo

Los diagramas de flujo representan gráficamente los pasos de un algoritmo.

### Símbolos más comunes:
- **Inicio/fin**: Representa el comienzo y final del proceso.
- **Entrada/salida**: Lectura o escritura de datos.
- **Proceso**: Asignaciones, cálculos.
- **Decisión**: Condiciones con ramificación (Sí / No).
- **Indicadores de dirección**: Flechas para secuencia de operaciones.

### Recomendaciones:
- Evitar líneas cruzadas.
- Usar diseño de arriba a abajo y de izquierda a derecha.
- Mantener claridad y simplicidad.

### Cuidado con estructuras no soportadas:
- Bucle `repetir-hasta`: No existe en Java, aunque sí en otros lenguajes.

## 💡 Pseudocódigo

Es una forma de describir algoritmos usando un lenguaje intermedio entre el lenguaje natural y el de programación. Se omite la sintaxis formal.

Ejemplo de estructura:
```
Algoritmo Nombre
Entorno
    variables...
Inicio
    acciones...
Fin
```

Herramientas útiles: **PSeInt**, **Flowgorithm**

## 🧱 Diagramas de Clases UML

Representan clases, atributos y métodos de forma estructurada. Incluyen relaciones como herencia, implementación e interacción entre objetos.

### Estructura:
- Nombre de clase
- Atributos (con modificadores `+` público, `-` privado)
- Métodos

### Relación entre clases:
- **Herencia**: Flecha continua con punta cerrada.
- **Implementación de interfaz**: Flecha discontinua con punta cerrada.
- **Dependencia**: Línea discontinua con punta abierta.

### Otros elementos:
- **Miembros estáticos**: Se subrayan.
- **Abstractos o interfaces**: En cursiva.

## 📝 Documentación con Javadoc

Javadoc permite documentar el código fuente de forma estándar. Usa comentarios especiales `/** */` y etiquetas.

### Etiquetas comunes:
- `@author`
- `@version`
- `@param` (explica parámetros)
- `@return` (describe el valor devuelto)
- `@throws` o `@exception` (para excepciones)
- `@see`, `@since`, `@deprecated`, `{@link}`, `{@inheritDoc}`

### Estilo recomendado:
- Evitar redundancias.
- Usar `<code>` para resaltar nombres de funciones o variables.
- Comenzar métodos con verbos.
- No abusar de los enlaces (`@link`).

Más recursos:
- [Documentación oficial de Oracle](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html)
