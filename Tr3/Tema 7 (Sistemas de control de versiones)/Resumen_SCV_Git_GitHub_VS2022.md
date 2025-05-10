
# 🛠️ Sistemas de Control de Versiones con Git, GitHub y Visual Studio 2022

## 📌 Introducción

Un sistema de control de versiones (SCV) permite registrar los cambios realizados en archivos y proyectos. Esto ayuda a gestionar versiones, colaborar en equipo, revertir errores y realizar pruebas sin afectar el código principal.

### ¿Por qué es útil?

- Recuperar versiones previas.
- Hacer pruebas sin afectar la versión estable.
- Colaborar en equipo sin sobrescribir el trabajo ajeno.
- Fusionar desarrollos paralelos.
- Detectar errores introducidos entre versiones.

## 🔁 Tipos de Sistemas de Control de Versiones

### 1. Local:
- Control en el equipo personal.
- Guarda diferencias (parches) entre versiones.

### 2. Centralizado:
- Un servidor almacena las versiones.
- Todos los usuarios trabajan desde este servidor.
- Riesgo: si el servidor falla, se pierde todo.

### 3. Distribuido (como Git):
- Cada usuario tiene una copia completa.
- Permite trabajo offline.
- Sincronización voluntaria con el servidor remoto.

## 🧰 Git

Git es un SCV distribuido creado por Linus Torvalds. Se basa en instantáneas de todo el proyecto, no solo parches. Es rápido, robusto y multiplataforma.

### 🔧 Instalación

- **Windows**: Instalar desde [git-scm.com](https://git-scm.com). Usar Git Bash.
- **Linux**:
  ```bash
  sudo apt update
  sudo apt install git-all
  ```
- **macOS**: Solo ejecutar `git` en consola, se instalarán herramientas necesarias.

## ⚙️ Configuración inicial

```bash
git config --global user.name "TuNombre"
git config --global user.email "tuemail@example.com"
```

Ver configuración:

```bash
git config --list
```

Cambiar editor predeterminado:

```bash
git config --global core.editor nano
```

## 📁 Iniciar repositorio

```bash
git init
```

Esto crea el directorio `.git/`, donde se almacena el historial.

## ✅ Ciclo básico de trabajo

1. **Crear archivos**
2. **git add** – Añadir al "staging area".
3. **git commit -m "mensaje"** – Confirmar cambios.
4. **git status** – Ver el estado actual.
5. **git log** – Ver historial de cambios.

Atajo:

```bash
git commit -a -m "mensaje"
```

## 🔍 Diferencias

```bash
git diff
```

Muestra los cambios entre el archivo actual y el último commit.

## 🚫 Ignorar archivos

Crear `.gitignore` con patrones:

```txt
*.class
*~
!important~
```

## 🏷️ Etiquetas (Tags)

Permiten nombrar versiones específicas:

```bash
git tag v1.0
git show v1.0
git checkout v1.0
```

## 🌱 Ramas

Permiten desarrollar características en paralelo:

```bash
git branch nuevaRama
git switch nuevaRama
git merge nuevaRama
```

## ❌ Eliminar archivos

```bash
git rm archivo
```

Quitar seguimiento sin borrar:

```bash
git reset HEAD archivo
```

## 🌐 Repositorios remotos con GitHub

- **Clonar**: 
  ```bash
  git clone https://github.com/usuario/repositorio.git
  ```

- **Vincular remoto a repositorio local**:
  ```bash
  git remote add origin https://github.com/usuario/repositorio.git
  ```

- **Enviar cambios**:
  ```bash
  git push -u origin master
  ```

- **Descargar cambios remotos**:
  ```bash
  git pull origin master --allow-unrelated-histories
  ```

## 🖼️ Front-ends gráficos

- **Git GUI**, **GitKraken**, **GitHub Desktop**.
- Visual Studio Code y Visual Studio tienen soporte Git integrado.
- Sitios visuales: [Visualizing Git](https://git-school.github.io/visualizing-git/)

## 🎮 Git y Visual Studio 2022

1. Crear un proyecto.
2. Usar la opción "Crear repositorio Git".
3. Confirmar cambios desde la barra de estado.
4. Configurar `.gitignore` desde el menú.
5. Enviar cambios con "Push a un servicio Git".

## 📚 Recursos útiles

- [Libro oficial Git](https://git-scm.com/book/es/v2)
- [GitHub para estudiantes](https://education.github.com/pack)
- [Guía visual](https://git-school.github.io/visualizing-git/)
- [Curso Git en Pluralsight](https://app.pluralsight.com/library/courses/how-git-works/table-of-contents)

---

