# ⚙️ Sistema de Gestión de Usuarios con Supabase

Una solución completa para la gestión de usuarios que implementa autenticación basada en número de identificación y control de acceso basado en roles, todo impulsado por la potencia de Supabase.

## ✨ Características Principales

* **🔑 Autenticación Segura por ID:** Permite a los usuarios iniciar sesión utilizando su número de identificación, eliminando la necesidad de correos electrónicos.
* **<0xF0><0x9F><0x91><0xA6> Operaciones CRUD de Usuarios:** Funcionalidades completas para Crear, Leer, Actualizar y Eliminar usuarios dentro del sistema.
* **🛡️ Control de Acceso Basado en Roles:** Implementa tres roles de usuario distintos: Normal, Administrador y Super Administrador, cada uno con sus propios permisos.
* **📱 Diseño Responsivo:** La interfaz de usuario se adapta perfectamente a diferentes tamaños de pantalla, ofreciendo una experiencia consistente en dispositivos móviles y de escritorio.
* **🔄 Persistencia de Sesión:** Mantiene las sesiones de usuario activas utilizando `localStorage` para una experiencia fluida.
* **⚡ Integración Directa con la API REST de Supabase:** Aprovecha la velocidad y eficiencia de la API REST de Supabase para todas las operaciones de la base de datos.

## 🚀 Inicio Rápido

Sigue estos sencillos pasos para poner en marcha el sistema:

1.  **Clona el repositorio:**
    ```bash
    git clone [https://github.com/yourusername/user-management-system.git](https://github.com/yourusername/user-management-system.git)
    cd user-management-system
    ```
2.  **Abre `index.html` en tu navegador:** Simplemente haz doble clic en el archivo o utiliza un servidor local como Live Server para visualizar la aplicación.

### 🛠️ Configuración de Supabase

Asegúrate de configurar tu proyecto de Supabase correctamente siguiendo estos pasos:

#### 💾 Creación de la Tabla de Usuarios

Ejecuta la siguiente consulta SQL en el editor de SQL de tu proyecto de Supabase para crear la tabla `usuarios`:

```sql
CREATE TABLE usuarios (
  id_usuario SERIAL PRIMARY KEY,
  identificacion BIGINT UNIQUE NOT NULL,
  nombre_usuario TEXT NOT NULL,
  email TEXT NOT NULL,
  clave_encriptada TEXT NOT NULL,
  usuario_normal BOOLEAN DEFAULT FALSE,
  usuario_administrador BOOLEAN DEFAULT FALSE,
  usuario_superadministrador BOOLEAN DEFAULT FALSE
);
🔒 Políticas de Seguridad a Nivel de Fila (RLS)
Habilita y configura las políticas de RLS para proteger tus datos. Un buen punto de partida es permitir el acceso a todos los usuarios autenticados:

SQL

ALTER TABLE usuarios ENABLE ROW LEVEL SECURITY;

CREATE POLICY "Enable access for authenticated users"
ON usuarios FOR ALL
TO authenticated
USING (true);
Nota: Es posible que necesites políticas más granular para controlar quién puede crear, leer, actualizar y eliminar usuarios, dependiendo de los roles implementados.

⚙️ Configuración del Proyecto
Reemplaza los siguientes valores en el archivo index.html con las credenciales de tu proyecto de Supabase:

JavaScript

const SUPABASE_URL = 'your-supabase-url';
const SUPABASE_KEY = 'your-supabase-key';
Puedes encontrar la URL y la clave de tu proyecto en la configuración de tu proyecto de Supabase.

📂 Estructura del Proyecto
user-management-system/
├── index.html         # Archivo principal de la aplicación
├── README.md          # Documentación del proyecto
└── styles.css         # Archivos de estilos CSS
🎨 Componentes de la Interfaz de Usuario
Componente	Descripción
Pantalla de Autenticación	Formularios de inicio de sesión y registro.
Panel de Usuario	Interfaz para la gestión de usuarios (CRUD).
Modales	Ventanas emergentes para agregar y editar usuarios.
📜 Licencia
Este proyecto está bajo la Licencia MIT - consulta el archivo LICENSE para obtener más detalles.


Espero que esto sea lo que necesitabas. ¡Avísame si tienes alguna otra pregunta!