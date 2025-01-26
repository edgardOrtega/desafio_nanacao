# Servidor de Cafés: Pruebas con Jest y Supertest

Este proyecto implementa un servidor para manejar operaciones CRUD relacionadas con cafés, desarrollado con Node.js y Express. Las pruebas unitarias y de integración fueron realizadas utilizando **Jest** y **Supertest**.

## Requisitos Previos

Antes de ejecutar las pruebas, asegúrate de tener instalado lo siguiente:

- Node.js (v16 o superior recomendado)
- Jest (`npm install jest --save-dev`)
- Supertest (`npm install supertest --save-dev`)

Además, asegúrate de que el archivo `cafes.json` contenga un arreglo de objetos con información de cafés, como se requiere para la ejecución del servidor.

## Estructura del Proyecto
 proyecto-servidor ├── index.js # Código del servidor ├── server.spec.js # Archivo de pruebas ├── cafes.json # Datos de ejemplo de cafés ├── package.json # Dependencias del proyecto


## Endpoints Implementados

El servidor tiene las siguientes rutas:

1. **GET /cafes**: Obtiene todos los cafés.
2. **GET /cafes/:id**: Obtiene un café por su ID.
3. **POST /cafes**: Agrega un nuevo café.
4. **PUT /cafes/:id**: Actualiza un café existente.
5. **DELETE /cafes/:id**: Elimina un café.

## Pruebas Implementadas

Las pruebas evalúan las rutas del servidor y aseguran el correcto funcionamiento de las operaciones CRUD.

### Archivo de Pruebas: `server.spec.js`

1. **Ruta GET /cafes**
   - Verifica que la respuesta tenga un código de estado `200`.
   - Confirma que el cuerpo de la respuesta es un arreglo que contiene al menos un objeto.

   ```javascript
   expect(response.statusCode).toBe(200);
   expect(Array.isArray(response.body)).toBe(true);
   expect(response.body.length).toBeGreaterThan(0);
   ```
2. Ruta DELETE /cafes/:id

    - Verifica que al intentar eliminar un café con un ID inexistente se devuelve un código de estado 404.
    - Valida que el mensaje de error sea el esperado.

    ```javascript
    expect(response.statusCode).toBe(404);
    expect(response.body.message).toBe(`No se encontró ningún cafe con ese id`);
    ```



