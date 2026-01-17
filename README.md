# Backend API - Sistema de Productos y Categorías

API REST desarrollada con Laravel para la gestión de productos y categorías.

## 📋 Requisitos Previos

- PHP >= 8.2
- Composer
- MySQL >= 8.0
- Node.js >= 18.x
- NPM o Yarn

## 🚀 Instalación

1. **Clonar el repositorio**
```bash
git clone <url-del-repositorio>
cd backend-prueba
```

2. **Instalar dependencias de PHP**
```bash
composer install
```

3. **Instalar dependencias de Node.js**
```bash
npm install
```

4. **Configurar variables de entorno**
```bash
cp .env.example .env
```

5. **Generar clave de aplicación**
```bash
php artisan key:generate
```

6. **Configurar base de datos**

Edita el archivo `.env` con tus credenciales de MySQL:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=prueba_tecnica
DB_USERNAME=root
DB_PASSWORD=tu_contraseña
```

7. **Ejecutar migraciones**
```bash
php artisan migrate
```

## ▶️ Ejecutar el Proyecto

### Servidor de desarrollo
```bash
# Opción 1: Servidor artisan
php artisan serve

# Opción 2: Con ruta específica de PHP (XAMPP)
D:\xampp\php\php.exe artisan serve
```

El servidor estará disponible en: `http://localhost:8000`

### Compilar assets (opcional)
```bash
npm run dev
```

## 📚 Endpoints de la API

### Categorías

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/api/categorias` | Listar todas las categorías |
| GET | `/api/categorias/{id}` | Obtener una categoría específica |
| POST | `/api/categorias` | Crear nueva categoría |
| PUT/PATCH | `/api/categorias/{id}` | Actualizar categoría |
| DELETE | `/api/categorias/{id}` | Eliminar categoría |

**Ejemplo de request (POST):**
```json
{
  "nombre": "Electrónica"
}
```

### Productos

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/api/productos` | Listar todos los productos |
| GET | `/api/productos/{id}` | Obtener un producto específico |
| POST | `/api/productos` | Crear nuevo producto |
| PUT/PATCH | `/api/productos/{id}` | Actualizar producto |
| DELETE | `/api/productos/{id}` | Eliminar producto |

**Ejemplo de request (POST):**
```json
{
  "nombre": "Laptop HP",
  "descripcion": "Laptop de alto rendimiento",
  "precio": 15000.50,
  "stock": 10,
  "categoria_id": 1
}
```

## 🗄️ Estructura de la Base de Datos

### Tabla: categorias
- `id` - Identificador único
- `nombre` - Nombre de la categoría
- `created_at` - Fecha de creación
- `updated_at` - Fecha de actualización

### Tabla: productos
- `id` - Identificador único
- `nombre` - Nombre del producto
- `descripcion` - Descripción del producto (opcional)
- `precio` - Precio (decimal 8,2)
- `stock` - Cantidad en inventario
- `categoria_id` - Relación con categorías
- `created_at` - Fecha de creación
- `updated_at` - Fecha de actualización

## 🛠️ Tecnologías Utilizadas

- **Framework:** Laravel 11.x
- **Base de datos:** MySQL
- **Frontend Assets:** Vite + Tailwind CSS
- **API:** RESTful

## 📝 Notas Adicionales

- El proyecto utiliza rutas API con el prefijo `/api`
- Las relaciones están configuradas: Una categoría tiene muchos productos
- Se implementa eliminación en cascada (al borrar una categoría se eliminan sus productos)
- Validaciones implementadas en los controllers

## 🧪 Testing

```bash
php artisan test
```

## 📄 Licencia

Este proyecto es de uso privado. 
