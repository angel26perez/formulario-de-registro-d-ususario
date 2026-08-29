# Poyecto 1:  Sistema registro de usuarios
Miguel Perez y Marcos Salas

# Problema Solucionado
Reemplaza el registro manual en hojas de cálculo o archivos sueltos por un sistema centralizado, donde es fácil guardar, consultar, cambiar o borrar usuarios sin enredos.

# Tecnologias utilizadas
Python 3

Tkinter

SQLite3

Visual Studio Code

# Funcionamiento
1. Las opciones del menú
Arriba en la esquina tienes el menú BBDD:

Conectar: Prepara la base de datos para empezar a guardar cosas.

Salir: Cierra el programa (te pregunta antes si estás seguro).

2. Los botones de la pantalla
Crear: Llenas las casillas (Nombre, Contraseña, Apellido, Ciudad, Codigo Postal, Dirección y Comentarios) y le das clic a Crear para guardarlo.

Leer: Si quieres buscar a alguien en específico, pones su número de ID y le das a Leer. Los datos de esa persona salen de una en las casillas.

Actualizar: Para cambiarle algo a un usuario, pones su ID, cambias los datos que quieras en las casillas y le das a Actualizar.

Eliminar: Pones el ID, le das a Eliminar y confirmas en la ventana que sale.

Limpiar: Deja todas las casillas vacías de un solo toque para que no tengas que borrar letra por letra.

3. La tabla de abajo
Ahí ves a todos los usuarios registrados.

Atajo fácil: Si le das clic a cualquier persona en la tabla, sus datos se pasan solos a las casillas de arriba. Así no tienes que estar escribiendo el ID a mano para editarlo o borrarlo.

# Evidencias

Ventana Principal
 
<img width="532" height="392" alt="image" src="https://github.com/user-attachments/assets/81712e8b-8687-43fb-8c6a-d0e3888b7921" />

<img width="1155" height="702" alt="image" src="https://github.com/user-attachments/assets/e9cdf941-f7e6-409d-a60e-031306f0ac39" />


Creacion base de datos

<img width="515" height="457" alt="image" src="https://github.com/user-attachments/assets/3eaa50a4-72c3-4c80-9b6c-f058dd8479b2" />
<img width="1119" height="263" alt="image" src="https://github.com/user-attachments/assets/4830e6dd-cc60-42d0-90d8-c5118dbceb32" />

Registro de un usuario








# Estrutura del preyecto
       ├── BaseUsuario.db       # Base de datos SQLite (se crea sola al ejecutar la app)

       ├── main.py              # Código principal con la interfaz de Tkinter y lógica CRUD

       ├── README.md            # Guia principal del proyecto

       └── README_Preguntas.md  # Respuestas a la pregunatas del punto 13.
