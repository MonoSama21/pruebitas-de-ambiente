# Proyecto HTML con CI/CD en Vercel

Este es un proyecto HTML básico configurado con despliegue automático en Vercel usando diferentes ambientes según la rama de Git.

## 🚀 Configuración de Ambientes

- **Rama `main`**: Se despliega automáticamente en el ambiente de **PRODUCCIÓN**
- **Rama `develop`**: Se despliega automáticamente en el ambiente de **DESARROLLO**
- Cada commit genera un preview único

## 📋 Configuración Inicial

### 1. Instalar Vercel CLI (opcional)

```bash
npm i -g vercel
```

### 2. Inicializar repositorio Git

```bash
git init
git add .
git commit -m "Initial commit"
```

### 3. Crear rama develop

```bash
git checkout -b develop
git push origin develop
git checkout main
```

### 4. Conectar con Vercel

#### Opción A: Desde la web de Vercel

1. Ve a [vercel.com](https://vercel.com) e inicia sesión
2. Click en "Add New Project"
3. Importa tu repositorio de GitHub/GitLab/Bitbucket
4. Vercel detectará automáticamente la configuración
5. Click en "Deploy"

#### Opción B: Desde la CLI

```bash
vercel
```

Sigue las instrucciones en pantalla.

## 🔧 Configuración de Ramas en Vercel

Vercel automáticamente detecta las ramas y crea ambientes:

- **Production Branch**: `main` (ambiente de producción)
- **Preview Branches**: `develop` y otras ramas (ambientes de desarrollo/staging)

Para verificar/cambiar la rama de producción:

1. Ve a tu proyecto en Vercel Dashboard
2. Settings → Git
3. En "Production Branch" asegúrate que esté configurado como `main`

## 📦 Estructura del Proyecto

```
pruebitas-de-ambiente/
├── index.html        # Página principal
├── vercel.json       # Configuración de Vercel
├── .gitignore        # Archivos a ignorar
└── README.md         # Este archivo
```

## 🌐 URLs de Despliegue

Después de configurar Vercel, tendrás URLs como:

- **Producción (main)**: `https://tu-proyecto.vercel.app`
- **Desarrollo (develop)**: `https://tu-proyecto-git-develop.vercel.app`
- **Preview por commit**: `https://tu-proyecto-[hash].vercel.app`

## 🔄 Flujo de Trabajo

### Para desarrollo:

```bash
git checkout develop
# Haz tus cambios
git add .
git commit -m "feat: nueva funcionalidad"
git push origin develop
```

→ Se desplegará automáticamente en el ambiente de desarrollo

### Para producción:

```bash
git checkout main
git merge develop
git push origin main
```

→ Se desplegará automáticamente en el ambiente de producción

## 🛠️ Comandos Útiles

```bash
# Ver estado del repositorio
git status

# Cambiar de rama
git checkout develop
git checkout main

# Crear nueva rama
git checkout -b feature/nueva-funcionalidad

# Ver despliegues en Vercel
vercel ls

# Ver logs
vercel logs
```

## 📝 Variables de Ambiente (opcional)

Si necesitas variables de ambiente:

1. En Vercel Dashboard → Settings → Environment Variables
2. Añade variables específicas para cada ambiente:
   - Production (main)
   - Preview (develop)
   - Development (local)

## 🎨 Personalización

Puedes personalizar el proyecto editando:

- **index.html**: Contenido y estilos de la página
- **vercel.json**: Configuración de rutas y builds

## 🔒 Seguridad

- El archivo `.gitignore` está configurado para no subir archivos sensibles
- Usa variables de ambiente en Vercel para datos sensibles
- Nunca subas API keys o secretos al repositorio

## 📚 Recursos

- [Documentación de Vercel](https://vercel.com/docs)
- [Vercel CLI](https://vercel.com/docs/cli)
- [Git Workflows](https://vercel.com/docs/concepts/git)

## 🤝 Contribuir

1. Fork el proyecto
2. Crea una rama feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto es de código abierto y está disponible bajo la licencia MIT.

---

**¡Listo!** 🎉 Ahora tienes un proyecto con CI/CD configurado. Cada vez que hagas push a `develop` o `main`, Vercel desplegará automáticamente en el ambiente correspondiente.