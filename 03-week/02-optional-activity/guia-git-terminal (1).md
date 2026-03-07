# Guía Git desde la Terminal

## 1. ¿Por qué usar Git en la terminal?

Git es un sistema de control de versiones distribuido que registra cambios en archivos
y coordina el trabajo entre varios desarrolladores.

Razones para usarlo desde la terminal:

- Más rápida y directa que las interfaces gráficas
- Control total sobre las operaciones
- Funciona igual en Linux, macOS y Windows
- Estándar en entornos profesionales y servidores

Con Git desde la terminal puedes:

- Registrar cambios en tu código
- Volver a versiones anteriores
- Colaborar con otros desarrolladores
- Sincronizar proyectos con GitHub o GitLab

---

## 2. Inicialización de un Repositorio

Ir a la carpeta del proyecto:

```bash
cd ruta/de/tu/proyecto
```

Inicializar Git:

```bash
git init
```

Esto crea una carpeta oculta `.git` con toda la información del repositorio.

Ver el estado de los archivos (modificados, sin seguimiento, listos para commit):

```bash
git status
```

---

### Configuración obligatoria antes del primer commit

Git necesita saber quién realiza los cambios. Configura tu nombre y email:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tuemail@example.com"
```

Verificar la configuración:

```bash
git config --list
```

---

## 3. Flujo de Trabajo de Commit

El flujo básico tiene **3 etapas**: modificar archivos → preparar (stage) → guardar (commit).

Agregar todos los archivos modificados al staging area:

```bash
git add .
```

Agregar un archivo específico:

```bash
git add archivo.js
```

Crear un commit con un mensaje descriptivo:

```bash
git commit -m "mensaje del commit"
```

---

### Buenas prácticas para mensajes de commit

Un buen mensaje debe ser claro, corto y descriptivo.

✔ Correcto:

```
Corrige error en validación de contraseña
```

```
Agrega módulo de autenticación
```

✘ Incorrecto:

```
arreglos
```

```
cambios
```

Un commit debe describir **qué se cambió y por qué**.

---

## 4. Subir al Servidor Remoto (Push)

Para subir a GitHub o GitLab, primero conecta el repositorio local con el remoto.

Conectar repositorio local con remoto:

```bash
git remote add origin https://github.com/usuario/repositorio.git
```

Verificar conexión:

```bash
git remote -v
```

Subir por primera vez (`-u` guarda la configuración para futuros push):

```bash
git push -u origin main
```

Subidas siguientes:

```bash
git push
```

---

## 5. Descargar y Actualizar Repositorios

Clonar un repositorio existente desde internet:

```bash
git clone https://github.com/usuario/repositorio.git
```

Traer cambios nuevos al repositorio local (descarga y mezcla con tu versión):

```bash
git pull
```

---

## 6. Cheat Sheet de Comandos Esenciales

| Acción                       | Comando                                             |
| ---------------------------- | --------------------------------------------------- |
| Inicializar repositorio      | `git init`                                          |
| Ver estado                   | `git status`                                        |
| Agregar todos los archivos   | `git add .`                                         |
| Agregar archivo específico   | `git add archivo.txt`                               |
| Crear commit                 | `git commit -m "mensaje"`                           |
| Configurar nombre            | `git config --global user.name "Nombre"`            |
| Configurar email             | `git config --global user.email "correo@email.com"` |
| Conectar remoto              | `git remote add origin URL`                         |
| Ver remotos                  | `git remote -v`                                     |
| Subir cambios                | `git push`                                          |
| Subir por primera vez        | `git push -u origin main`                           |
| Clonar repositorio           | `git clone URL`                                     |
| Descargar cambios            | `git pull`                                          |

---

## Conclusión

Flujo básico:

```
editar archivos → git add → git commit → git push
```

Para proyectos existentes:

```
git clone → git pull → editar → commit → push
```

Dominar estos comandos es suficiente para manejar la mayoría de proyectos
de desarrollo de software profesional.


