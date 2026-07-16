# restaurante_app

## Datos del estudiante

**Nombre:** Diego Benancio Pluas Arriaga

---

## Descripción del proyecto

`restaurante_app` es un sistema desarrollado en Python utilizando Programación Orientada a Objetos para la gestión básica de un restaurante.

El sistema permite registrar y listar productos, bebidas y clientes mediante un menú interactivo ejecutado desde consola.

El proyecto utiliza una arquitectura modular separando modelos, servicios y la interacción con el usuario. Además, aplica principios SOLID para crear un código organizado, mantenible y fácil de ampliar.

---

## Estructura del proyecto

```
restaurante_app/
│
├── modelos/
│   ├── __init__.py
│   ├── producto.py
│   ├── bebida.py
│   └── cliente.py
│
├── servicios/
│   ├── __init__.py
│   └── restaurante.py
│
└── main.py

README.md
```

---

# Responsabilidad de las clases

## Producto

La clase `Producto` representa un producto general del restaurante.

Sus responsabilidades son:

- Guardar código, nombre, categoría y precio.
- Mostrar la información del producto mediante el método `mostrar_informacion()`.

Esta clase funciona como base para otros tipos de productos del sistema.

---

## Bebida

La clase `Bebida` hereda de la clase `Producto`.

Representa una especialización de un producto del restaurante y agrega información específica:

- Tamaño.
- Tipo de envase.

Sobrescribe el método `mostrar_informacion()` para mostrar sus propios datos adicionales.

La relación entre `Producto` y `Bebida` es válida porque una bebida es un tipo de producto.

---

## Cliente

La clase `Cliente` representa la información de un cliente registrado.

Sus responsabilidades son:

- Guardar identificación, nombre y correo.
- Mostrar la información del cliente mediante el método `mostrar_informacion()`.

No hereda de `Producto` porque un cliente no representa un producto del restaurante.

---

## Restaurante

La clase `Restaurante` funciona como el servicio principal del sistema.

Sus responsabilidades son:

- Administrar la lista de productos.
- Administrar la lista de clientes.
- Registrar productos.
- Registrar clientes.
- Listar productos.
- Listar clientes.
- Validar que no existan códigos de productos repetidos.
- Validar que no existan identificaciones de clientes repetidas.

---

## main.py

El archivo `main.py` es el punto de entrada del programa.

Sus responsabilidades son:

- Mostrar el menú interactivo.
- Solicitar información mediante `input()`.
- Crear objetos Producto, Bebida y Cliente.
- Llamar a los métodos del servicio Restaurante.

No administra directamente las listas internas del sistema.

---

# Principios SOLID aplicados

## SRP - Responsabilidad Única

Cada clase tiene una responsabilidad específica:

- `Producto` representa productos generales.
- `Bebida` representa un tipo específico de producto.
- `Cliente` representa clientes.
- `Restaurante` administra las colecciones y operaciones del sistema.
- `main.py` controla la interacción con el usuario.

Esto permite mantener el código organizado y facilita realizar modificaciones futuras.

---

## OCP - Abierto/Cerrado

El sistema permite ampliar funcionalidades sin modificar el código existente.

La clase `Bebida` se incorpora mediante herencia desde `Producto`, agregando nuevos atributos como tamaño y envase.

La lógica principal de `Restaurante` no necesita modificarse para trabajar con bebidas, porque estas pueden registrarse como productos.

---

## LSP - Sustitución de Liskov

Los objetos de tipo `Bebida` pueden utilizarse como objetos de tipo `Producto`.

Producto y Bebida pueden almacenarse en una misma lista y utilizar el método común:

```python
mostrar_informacion()
```

Cada objeto ejecuta su propia implementación del método sin que el servicio tenga que preguntar qué tipo de objeto está procesando.

Esto permite aplicar polimorfismo correctamente.

---

# Instrucciones de ejecución

1. Abrir una terminal dentro de la carpeta del proyecto:

```
restaurante_app
```

2. Ejecutar el programa con:

```bash
python main.py
```

3. Utilizar el menú interactivo para realizar las siguientes acciones:

- Registrar productos.
- Registrar bebidas.
- Registrar clientes.
- Listar productos.
- Listar clientes.
- Salir del sistema.

---

# Reflexión final

La aplicación de principios SOLID permite desarrollar sistemas más organizados, mantenibles y fáciles de ampliar.

Separar las responsabilidades evita que una clase tenga demasiadas funciones y facilita realizar cambios sin afectar todo el programa.

La herencia y el polimorfismo permiten agregar nuevas funcionalidades de forma ordenada, como la incorporación de la clase `Bebida` dentro del sistema del restaurante.

Un diseño correcto desde el inicio ayuda a crear programas más claros, reutilizables y preparados para futuras mejoras.
