# 🚀 Guía Completa de Comandos Git

*Una guía exhaustiva y práctica que reúne los comandos más esenciales de Git, organizados por categorías y explicados con ejemplos reales. Desde comandos básicos para principiantes hasta técnicas avanzadas para profesionales, esta documentación te ayudará a dominar Git paso a paso. Incluye comandos para configuración inicial, manejo de repositorios, branches, commits, merging, resolución de conflictos, trabajo colaborativo y mucho más. Perfecta para desarrolladores, estudiantes y cualquier persona que quiera convertirse en un experto en control de versiones.*

## 📋 Tabla de Contenidos

- [Configuración Inicial](#️-configuración-inicial)
- [Comandos Básicos de Repositorio](#-comandos-básicos-de-repositorio)
- [Comandos de Staging y Commits](#-comandos-de-staging-y-commits)
- [Comandos de Branches](#-comandos-de-branches)
- [Comandos de Historial y Logs](#-comandos-de-historial-y-logs)
- [Comandos de Trabajo Remoto](#-comandos-de-trabajo-remoto)
- [Comandos de Merge y Rebase](#-comandos-de-merge-y-rebase)
- [Comandos de Deshacer Cambios](#-comandos-de-deshacer-cambios)
- [Comandos de Stash](#-comandos-de-stash)
- [Comandos Avanzados](#-comandos-avanzados)
- [Comandos Más Utilizados](#-comandos-más-utilizados-en-el-día-a-día)
- [Pro Tips](#-pro-tips)

## ⚙️ Configuración Inicial

### `git config`
Configura tu identidad y preferencias globales

```bash
# Configurar nombre y email (obligatorio)
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@ejemplo.com"

# Configurar editor por defecto
git config --global core.editor "code --wait"

# Ver toda la configuración
git config --list
```

### `git init`
Inicializa un nuevo repositorio Git

```bash
git init
git init mi-proyecto  # Crea carpeta y inicializa
```

## 📁 Comandos Básicos de Repositorio

### `git clone`
Clona un repositorio remoto

```bash
git clone https://github.com/usuario/repositorio.git
git clone https://github.com/usuario/repositorio.git mi-carpeta
```

### `git status`
Muestra el estado actual del repositorio (el más usado)

```bash
git status
git status -s  # Versión corta
```

### `git add`
Añade archivos al área de staging

```bash
git add archivo.txt        # Añade un archivo específico
git add .                  # Añade todos los archivos
git add *.js              # Añade todos los archivos .js
git add -A                # Añade todos los archivos (incluyendo eliminados)
```

## 💾 Comandos de Staging y Commits

### `git commit`
Guarda los cambios en el repositorio

```bash
git commit -m "Mensaje descriptivo del commit"
git commit -am "Añade y commitea archivos modificados"
git commit --amend -m "Modifica el último commit"
```

### `git diff`
Muestra las diferencias entre archivos

```bash
git diff                   # Cambios no staged
git diff --staged         # Cambios staged
git diff HEAD~1           # Comparar con commit anterior
```

### `git reset`
Deshace cambios en el staging area

```bash
git reset archivo.txt      # Quita archivo del staging
git reset                 # Quita todos los archivos del staging
```

## 🌿 Comandos de Branches

### `git branch`
Maneja las ramas del repositorio

```bash
git branch                 # Lista todas las ramas
git branch nueva-rama      # Crea una nueva rama
git branch -d rama         # Elimina una rama
git branch -D rama         # Fuerza eliminación de rama
```

### `git checkout`
Cambia entre ramas o commits

```bash
git checkout main          # Cambia a la rama main
git checkout -b nueva-rama # Crea y cambia a nueva rama
git checkout archivo.txt   # Restaura archivo desde último commit
```

### `git switch` (Moderno)
Alternativa moderna a checkout para cambiar ramas

```bash
git switch main            # Cambia a rama main
git switch -c nueva-rama   # Crea y cambia a nueva rama
```

## 📜 Comandos de Historial y Logs

### `git log`
Muestra el historial de commits

```bash
git log                    # Historial completo
git log --oneline         # Una línea por commit
git log --graph           # Muestra gráfico de ramas
git log -n 5              # Últimos 5 commits
git log --author="Nombre" # Commits de un autor específico
```

### `git show`
Muestra información detallada de un commit

```bash
git show                   # Último commit
git show HEAD~1           # Commit anterior
git show abc123           # Commit específico por hash
```

## 🌐 Comandos de Trabajo Remoto

### `git remote`
Maneja repositorios remotos

```bash
git remote -v              # Lista remotos configurados
git remote add origin https://github.com/usuario/repo.git
git remote remove origin   # Elimina remoto
```

### `git fetch`
Descarga cambios sin fusionar

```bash
git fetch                  # Descarga desde origin
git fetch origin main     # Descarga rama específica
```

### `git pull`
Descarga y fusiona cambios

```bash
git pull                   # Pull desde rama actual
git pull origin main      # Pull desde rama específica
git pull --rebase         # Pull con rebase en lugar de merge
```

### `git push`
Sube cambios al repositorio remoto

```bash
git push                   # Push a rama actual
git push origin main      # Push a rama específica
git push -u origin main   # Push y establece upstream
git push --force          # Push forzado (¡cuidado!)
```

## 🔀 Comandos de Merge y Rebase

### `git merge`
Fusiona ramas

```bash
git merge feature-branch   # Fusiona feature-branch en rama actual
git merge --no-ff branch   # Merge sin fast-forward
git merge --abort         # Cancela merge en progreso
```

### `git rebase`
Reaplica commits sobre otra rama

```bash
git rebase main           # Rebase rama actual sobre main
git rebase -i HEAD~3     # Rebase interactivo últimos 3 commits
git rebase --continue    # Continúa rebase después de resolver conflictos
git rebase --abort       # Cancela rebase en progreso
```

## ↩️ Comandos de Deshacer Cambios

### `git restore` (Moderno)
Restaura archivos a estados anteriores

```bash
git restore archivo.txt    # Restaura archivo desde último commit
git restore --staged archivo.txt  # Quita archivo del staging
git restore --source=HEAD~1 archivo.txt  # Restaura desde commit específico
```

### `git reset` (Avanzado)
Deshace commits y cambios

```bash
git reset --soft HEAD~1   # Deshace último commit, mantiene cambios staged
git reset --mixed HEAD~1  # Deshace commit y staging (por defecto)
git reset --hard HEAD~1   # Deshace todo (¡cuidado!)
```

### `git revert`
Crea commit que deshace cambios anteriores

```bash
git revert HEAD           # Revierte último commit
git revert abc123         # Revierte commit específico
```

## 📦 Comandos de Stash

### `git stash`
Guarda temporalmente cambios sin commitear

```bash
git stash                 # Guarda cambios actuales
git stash push -m "Mensaje descriptivo"
git stash list           # Lista todos los stashes
git stash pop            # Aplica y elimina último stash
git stash apply          # Aplica stash sin eliminarlo
git stash drop           # Elimina stash sin aplicar
```

## 💡 Comandos Avanzados

### `git cherry-pick`
Aplica commits específicos a la rama actual

```bash
git cherry-pick abc123    # Aplica commit específico
git cherry-pick abc123..def456  # Aplica rango de commits
```

### `git tag`
Crea etiquetas para versiones

```bash
git tag v1.0.0            # Crea tag ligero
git tag -a v1.0.0 -m "Versión 1.0.0"  # Tag anotado
git push origin --tags    # Sube todos los tags
```

### `git blame`
Muestra quién modificó cada línea

```bash
git blame archivo.txt     # Muestra autor de cada línea
```

### `git bisect`
Encuentra commit que introdujo un bug

```bash
git bisect start
git bisect bad           # Marca commit actual como malo
git bisect good abc123   # Marca commit como bueno
git bisect reset         # Termina bisect
```

## 🎯 Comandos Más Utilizados en el Día a Día

1. **`git status`** - Para ver qué archivos han cambiado
2. **`git add .`** - Para añadir todos los cambios al staging
3. **`git commit -m "mensaje"`** - Para guardar cambios
4. **`git push`** - Para subir cambios al repositorio remoto
5. **`git pull`** - Para descargar últimos cambios
6. **`git checkout -b nueva-rama`** - Para crear y cambiar a nueva rama
7. **`git merge rama`** - Para fusionar ramas
8. **`git log --oneline`** - Para ver historial resumido

## 🔥 Pro Tips

- Usa `git commit -am "mensaje"` para añadir y commitear archivos modificados en un solo comando
- Configura aliases: `git config --global alias.st status` para usar `git st`
- Usa `git log --graph --oneline --all` para ver un gráfico bonito del historial
- Siempre haz `git pull` antes de `git push` para evitar conflictos
- Usa mensajes de commit descriptivos: "Fix: corrige bug en login" en lugar de "fix"
- Crea un `.gitignore` para excluir archivos innecesarios

## 📚 Ejemplos Prácticos

### Flujo básico de trabajo
```bash
# Clonar repositorio
git clone https://github.com/usuario/proyecto.git
cd proyecto

# Crear nueva rama para feature
git checkout -b nueva-funcionalidad

# Hacer cambios y commitear
git add .
git commit -m "Add: nueva funcionalidad de login"

# Subir rama al remoto
git push -u origin nueva-funcionalidad

# Cambiar a main y actualizar
git checkout main
git pull origin main

# Fusionar feature
git merge nueva-funcionalidad
git push origin main

# Limpiar rama local
git branch -d nueva-funcionalidad
```

### Resolver conflictos de merge
```bash
# Intentar merge
git merge feature-branch

# Si hay conflictos, editarlos manualmente
# Luego añadir archivos resueltos
git add archivo-con-conflicto.txt

# Completar merge
git commit -m "Resolve merge conflicts"
```

### Deshacer último commit (manteniendo cambios)
```bash
git reset --soft HEAD~1
# Editar archivos si es necesario
git add .
git commit -m "Nuevo mensaje de commit corregido"
```

## 🆘 Comandos de Emergencia

### Deshacer todos los cambios locales
```bash
git reset --hard HEAD
git clean -fd  # Elimina archivos no trackeados
```

### Recuperar commit "perdido"
```bash
git reflog              # Encuentra el hash del commit
git checkout abc123     # Recupera el commit
git checkout -b recuperar-commit  # Crea rama desde ese punto
```

### Cambiar URL del repositorio remoto
```bash
git remote set-url origin https://github.com/nuevo-usuario/nuevo-repo.git
```

### Limpiar historial de un archivo
```bash
git filter-branch --force --index-filter \
'git rm --cached --ignore-unmatch archivo-sensible.txt' \
--prune-empty --tag-name-filter cat -- --all
```

---

## 📝 Notas Importantes

- **Siempre** haz backup antes de usar comandos destructivos como `reset --hard`
- **Nunca** hagas `git push --force` en ramas compartidas
- **Revisa** siempre `git status` antes de hacer commits
- **Usa** ramas para nuevas funcionalidades, nunca trabajes directamente en main
- **Escribe** mensajes de commit claros y descriptivos
- **Haz** commits pequeños y frecuentes en lugar de commits grandes

---

*¿Necesitas ayuda con algún comando específico o situación particular? ¡No dudes en consultar!*

## 🤝 Contribuciones

Si encuentras algún error o quieres agregar más comandos útiles, ¡las contribuciones son bienvenidas!

---

## 🌐 Conecta Conmigo

<div align="center">

### 📌 **Mis Redes Sociales**

[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/gdcodev)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gastondanielsen/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gastondanielsen)

---

</div>
