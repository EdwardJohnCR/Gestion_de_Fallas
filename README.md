# Sistema de Gestión de Fallas y Mantenimiento Industrial

## 📝 Descripción del Proyecto
Aplicación web diseñada para la digitalización, reporte y seguimiento de fallas de maquinaria en el piso de planta. El sistema reemplaza las listas estáticas por una plataforma dinámica, multiusuario y orientada a la movilidad, permitiendo a los técnicos reportar incidencias en tiempo real y a los administradores gestionar los activos y auditar los turnos.

## ✨ Características Principales
* **Diseño Mobile-First:** Interfaz optimizada mediante Tailwind CSS para ser operada fluidamente en smartphones y tablets industriales.
* **Autenticación Rápida (PIN):** Sistema de inicio de sesión mediante teclado numérico en pantalla para agilizar el acceso del personal en movimiento.
* **Gestión de Turnos:** Registro automatizado de la jornada del usuario (Mañana, Tarde, Noche) para agrupar las tareas diarias.
* **Catálogo Dinámico de Activos:** Lógica de base de datos adaptada para líneas de producción con secuencias de máquinas no contiguas (ej. permitiendo saltos de G05 a G13).
* **Control de Acceso Basado en Roles (RBAC):** Permisos segmentados para Administradores, Supervisores, Técnicos y usuarios de solo Vista.
* **Carga Asíncrona (AJAX):** Interfaz fluida sin recargas completas de página para operar en zonas de la planta con fluctuaciones de señal Wi-Fi.

## 🛠️ Stack Tecnológico
* **Frontend:** HTML5, Vanilla JavaScript, Tailwind CSS (vía CDN para prototipado rápido).
* **Backend:** PHP 8.x.
* **Base de Datos:** MySQL (Estructura relacional).
* **Entorno de Despliegue (Local):** Servidor Apache en Linux Mint 21.3.

## 📂 Estructura de Directorios
```text
/
├── index.php                 # Punto de entrada / Redireccionamiento
├── login.php                 # Interfaz de acceso mediante PIN
├── dashboard.php             # Panel principal de tareas diarias
├── admin.php                 # Panel de configuración general
├── config/
│   └── database.php          # Credenciales de conexión PDO/MySQLi
├── includes/                 # Componentes de interfaz reutilizables
│   ├── header.php            # Cabecera, meta tags y carga de Tailwind
│   └── footer.php            # Cierre de HTML y scripts globales
├── api/                      # Endpoints asíncronos para peticiones AJAX
│   ├── get_maquinas.php      # Filtro dinámico del catálogo de máquinas
│   └── procesar_falla.php    # Lógica de inserción de tareas
└── assets/                   # Archivos estáticos
    ├── css/                  # Hojas de estilo complementarias
    ├── js/                   # Scripts de la aplicación
    └── img/                  # Recursos gráficos y logotipos

⚙️ Instalación y Despliegue Local
Clonar este repositorio en el directorio del servidor web:

Bash
cd /var/www/html/
git clone [URL_DEL_REPOSITORIO] lista_fallas
Crear la base de datos mantenimiento_fallas en MySQL.

Importar el script SQL inicial (disponible en la documentación del proyecto o en el directorio database/ cuando se genere).

Configurar las credenciales de acceso a MySQL en config/database.php.

Acceder a través del navegador web local o mediante la IP del servidor en la red de la planta (ej. http://localhost/lista_fallas).

🚀 Estado del Proyecto
Fase Actual: Fase 1 - Inicialización del repositorio, configuración del esqueleto del proyecto y modelado de la base de datos relacional.
