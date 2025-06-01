# 🖥️ AcroWare - Sistema de Gestión de Inventarios 📊

[![Estado](https://img.shields.io/badge/Estado-En%20Desarrollo-yellow)](https://github.com/username/GestionInventarios)
[![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)](https://developer.mozilla.org/es/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![Licencia](https://img.shields.io/badge/Licencia-MIT-blue.svg)](LICENSE)

## 📋 Descripción del Proyecto

**AcroWare** es un sistema integral de gestión de inventarios diseñado específicamente para instituciones educativas y empresas que necesitan llevar un control detallado de sus activos tecnológicos, mobiliario y software. La plataforma permite realizar un seguimiento completo del ciclo de vida de los bienes, desde su adquisición hasta su baja, incluyendo ubicaciones, responsables, mantenimientos y actualizaciones.

El sistema está construido con una arquitectura modular que facilita la escalabilidad y el mantenimiento, implementando patrones de diseño que aseguran la calidad del código. AcroWare ofrece diferentes niveles de acceso según el rol del usuario, generación de reportes en PDF, códigos QR para la identificación rápida de activos y notificaciones por correo electrónico para alertas importantes.

## 🚀 Objetivos del Proyecto

- **Gestión Centralizada**: Proporcionar una plataforma única para administrar todos los activos de la organización, eliminando la necesidad de utilizar múltiples sistemas o registros manuales.

- **Trazabilidad Completa**: Permitir el seguimiento histórico de cada activo, incluyendo asignaciones, traslados, mantenimientos y actualizaciones realizadas a lo largo del tiempo.

- **Optimización de Recursos**: Facilitar la toma de decisiones basada en datos sobre adquisiciones, reemplazos y asignaciones de activos, maximizando la vida útil y el retorno de inversión.

- **Cumplimiento Normativo**: Ayudar a las instituciones a cumplir con regulaciones contables y auditorías mediante el registro detallado y la documentación adecuada de todos los activos.

- **Interfaz Intuitiva**: Ofrecer una experiencia de usuario amigable que minimice la curva de aprendizaje y maximice la productividad del personal encargado del inventario.

## 📁 Estructura del Proyecto

```
GestionInventarios/
│
├── Acciones/                  # Controladores y lógica de negocio
│   ├── fpdf/                  # Biblioteca para generación de PDFs
│   ├── PHPMailer/             # Biblioteca para envío de correos
│   ├── phpqrcode/             # Generación de códigos QR
│   ├── recordatorios/         # Sistema de notificaciones
│   ├── crud*.php              # Operaciones CRUD para cada entidad
│   ├── Rest*.php              # Endpoints de API REST
│   └── Reporte*.php           # Generación de reportes
│
├── pages/                     # Páginas de la aplicación
│   ├── assets/                # Recursos específicos de páginas
│   ├── errors/                # Páginas de error
│   ├── login/                 # Autenticación y recuperación de contraseña
│   ├── management/            # Gestión de entidades principales
│   │   ├── marca.php          # Gestión de marcas
│   │   ├── software.php       # Gestión de software
│   │   └── users.php          # Gestión de usuarios
│   ├── others/                # Páginas secundarias
│   └── places/                # Gestión de ubicaciones
│
├── patrones/                  # Implementación de patrones de diseño
│   ├── Singleton/             # Patrón Singleton (conexión BD)
│   └── Strategy/              # Patrón Strategy (autenticación)
│
├── resources/                 # Recursos estáticos
│   ├── css/                   # Hojas de estilo
│   ├── fonts/                 # Fuentes personalizadas
│   ├── images/                # Imágenes y logos
│   ├── js/                    # Scripts JavaScript
│   └── vendors/               # Bibliotecas de terceros
│
├── .gitignore                 # Archivos ignorados por Git
├── cerrar.php                 # Cierre de sesión
├── index.php                  # Punto de entrada principal (admin)
└── README.md                  # Documentación del proyecto
```

## 💻 Tecnologías Utilizadas

- **Backend**:
  - PHP 7.4+
  - MySQL 5.7+
  - Patrones de diseño (Singleton, Strategy)

- **Frontend**:
  - HTML5
  - CSS3
  - JavaScript
  - Bootstrap 4
  - jQuery
  - AJAX

- **Bibliotecas y Herramientas**:
  - FPDF (generación de PDFs)
  - PHPMailer (envío de correos)
  - PHP QR Code (generación de códigos QR)
  - DataTables (tablas interactivas)
  - Chart.js (gráficos estadísticos)

## ⚙️ Instalación

1. Clona este repositorio en tu servidor web:
   ```bash
   git clone https://github.com/Dallex-MT/GestionInventarios.git
   ```

2. Navega al directorio del proyecto:
   ```bash
   cd GestionInventarios
   ```

3. Importa la base de datos:
   ```bash
   mysql -u usuario -p nombre_base < ruta/al/archivo.sql
   ```

4. Configura la conexión a la base de datos en `patrones/Singleton/Conexion.php`:
   ```php
   // Ejemplo de configuración
   private $host = 'localhost';
   private $db = 'nombre_base_datos';
   private $user = 'usuario_mysql';
   private $pass = 'contraseña_mysql';
   ```

5. Configura los parámetros para el envío de correos en `Acciones/enviarEmail.php`:
   ```php
   // Ejemplo de configuración
   $mail->Host = 'smtp.ejemplo.com';
   $mail->Username = 'correo@ejemplo.com';
   $mail->Password = 'contraseña_correo';
   ```

6. Asegúrate de que el servidor web tenga permisos de escritura en las carpetas donde se generarán los códigos QR y reportes.

## 🔍 Uso

Para utilizar el sistema:

1. Accede a la aplicación a través de tu navegador:
   ```
   http://tu-servidor/GestionInventarios/
   ```

2. Inicia sesión con las credenciales según tu rol:
   - **Administrador**: acceso completo a todas las funcionalidades
   - **Laboratorista**: gestión de activos y ubicaciones
   - **Reportero**: visualización y generación de reportes

3. Desde el panel principal podrás:
   - Gestionar bienes informáticos (computadoras, impresoras, etc.)
   - Administrar bienes mobiliarios (mesas, sillas, etc.)
   - Registrar y asignar software
   - Definir ubicaciones y responsables
   - Generar códigos QR para identificación de activos
   - Crear reportes en PDF para inventarios y auditorías
   - Recibir notificaciones sobre mantenimientos y garantías

## 🤝 Cómo Contribuir

Si deseas contribuir a este proyecto, sigue estos pasos:

1. Haz un Fork del repositorio
   
2. Crea una rama para tu funcionalidad:
   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```

3. Desarrolla tu funcionalidad siguiendo estas pautas:
   - Respeta la arquitectura y patrones existentes
   - Sigue las convenciones de nomenclatura del proyecto
   - Documenta adecuadamente tu código
   - Añade validaciones y manejo de errores

4. Haz commit de tus cambios:
   ```bash
   git commit -m "Añade: funcionalidad para gestión de garantías"
   ```

5. Sube los cambios a tu repositorio:
   ```bash
   git push origin feature/nueva-funcionalidad
   ```

6. Crea un Pull Request describiendo detalladamente:
   - La funcionalidad implementada
   - Cómo se integra con el sistema actual
   - Posibles impactos en otras áreas del sistema
   - Pruebas realizadas

## 📝 Historial de Cambios

- **v1.2.0** (15/05/2025):
  - Implementación del sistema de códigos QR para identificación rápida
  - Módulo de notificaciones por correo para mantenimientos programados
  - Mejora en los reportes con gráficos estadísticos
  - Optimización en las consultas a la base de datos

- **v1.1.0** (20/03/2025):
  - Añadido módulo de gestión de software y licencias
  - Implementación del rol "Reportero" con permisos específicos
  - Mejoras en la interfaz responsiva para dispositivos móviles
  - Corrección de errores en el módulo de ubicaciones

- **v1.0.0** (10/01/2025):
  - Lanzamiento inicial
  - Funcionalidades básicas de gestión de activos informáticos y mobiliarios
  - Sistema de autenticación con roles (Administrador y Laboratorista)
  - Generación de reportes básicos en PDF

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - consulta el archivo [LICENSE](LICENSE) para más detalles.

## 👨‍💻 Créditos

Desarrollado con ❤️ por **DXM**

---

⭐️ **Nota**: Este proyecto ha sido desarrollado con fines educativos y como solución para la gestión eficiente de inventarios en instituciones educativas. Su implementación puede adaptarse a diferentes contextos organizacionales que requieran un control detallado de activos. ⭐️

#Acroware
