# API REST - Autenticación con Express y MongoDB

## Descripción
Esta API REST proporciona un sistema de autenticación de usuarios utilizando **Express.js**, **MongoDB**, y **JSON Web Tokens (JWT)**. Implementa la ruta `api/auth/login` para la autenticación de usuarios.

## Tecnologías Utilizadas
- Node.js
- Express.js
- MongoDB + Mongoose
- JWT (JSON Web Tokens)
- Bcrypt.js (para el hash de contraseñas)
- CORS
- Dotenv

## Instalación
### 1. Clonar el Repositorio
```sh
git clone https://github.com/tu-usuario/tu-repositorio.git
cd tu-repositorio
```

### 2. Instalar Dependencias
```sh
npm install
```

### 3. Configurar Variables de Entorno
Crea un archivo `.env` en la raíz del proyecto con el siguiente contenido:
```env
MONGO_URI=mongodb+srv://usuario:contraseña@cluster.mongodb.net/miBaseDeDatos
JWT_SECRET=miClaveSecretaParaJWT
PORT=3000
```

### 4. Iniciar el Servidor
```sh
npm run dev   # Si usas nodemon
# o
npm start     # Si usas node directamente
```

El servidor estará corriendo en `http://localhost:3000`.

## Endpoints

### **1. Login de Usuario**
**Ruta:** `POST /api/auth/login`

**Cuerpo de la petición (JSON):**
```json
{
  "email": "test@example.com",
  "password": "123456"
}
```

**Respuesta exitosa (200 OK):**
```json
{
  "token": "eyJhbGciOiJIUzI...",
  "user": {
    "id": "61234abcd567",
    "email": "test@example.com"
  }
}
```

**Errores posibles:**
- `400`: Usuario no encontrado o contraseña incorrecta.
- `500`: Error interno del servidor.

## Estructura del Proyecto
```
/backend
 ├── /config
 │    ├── db.js
 ├── /models
 │    ├── User.js
 ├── /controllers
 │    ├── authController.js
 ├── /routes
 │    ├── authRoutes.js
 ├── /middlewares
 │    ├── authMiddleware.js (opcional)
 ├── server.js
 ├── .env
 ├── package.json
```



