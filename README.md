# Login con autenticación JWT (Node.js + React)

Ejemplo de inicio de sesión con **JSON Web Tokens**: un backend en Node.js y Express emite y valida los tokens, y un frontend en React envía las credenciales con Axios.

## Tecnologías

- **Backend:** Node.js, Express, jsonwebtoken, cors
- **Frontend:** React, Vite, Axios

## Estructura

```
jwt/    → API en Express (puerto 3001)
react/  → Cliente en React + Vite
```

## Endpoints

| Método | Ruta | Descripción |
|---|---|---|
| GET | `/api` | Comprueba que el servidor responde |
| POST | `/usuario/login` | Valida usuario y clave; devuelve un token JWT (expira en 100 s) y lo guarda en una cookie `httpOnly` |
| POST | `/api/login` | Genera un token de ejemplo |
| POST | `/api/protected` | Ruta protegida; requiere el encabezado `Authorization: Bearer <token>` |

## Cómo ejecutarlo

**Backend**

```bash
cd jwt
npm install
npm run dev
```

**Frontend**

```bash
cd react
npm install
npm run dev
```

Credenciales de prueba: usuario `pedro`, clave `123`.

## Notas

Proyecto de aprendizaje. El usuario y la clave secreta del token están definidos en el código; en un entorno real se guardarían en una base de datos y en variables de entorno.
