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

# Ventana Principal
 
<img width="532" height="392" alt="image" src="https://github.com/user-attachments/assets/81712e8b-8687-43fb-8c6a-d0e3888b7921" />

<img width="1155" height="702" alt="image" src="https://github.com/user-attachments/assets/e9cdf941-f7e6-409d-a60e-031306f0ac39" />


# Creacion base de datos

<img width="515" height="457" alt="image" src="https://github.com/user-attachments/assets/3eaa50a4-72c3-4c80-9b6c-f058dd8479b2" />
<img width="1119" height="263" alt="image" src="https://github.com/user-attachments/assets/4830e6dd-cc60-42d0-90d8-c5118dbceb32" />

# Registro de un usuario

<img width="580" height="471" alt="image" src="https://github.com/user-attachments/assets/8019da1c-38fa-4644-8173-3292c33142b4" />
<img width="1121" height="564" alt="image" src="https://github.com/user-attachments/assets/efa31754-cc23-473a-9cb0-70c7dc65dea1" />

# Consulta de Un usuario
<img width="642" height="617" alt="image" src="https://github.com/user-attachments/assets/42cac2b1-f45a-42a2-8cc6-02149197fb17" />
<img width="531" height="606" alt="image" src="https://github.com/user-attachments/assets/d9ec76df-4c50-4926-aa28-f800027a557b" />
<img width="1113" height="110" alt="image" src="https://github.com/user-attachments/assets/7ca6afa7-cd25-4f94-b6c5-2ca2b09d49ae" />

# Actualizacion de informacion
<img width="631" height="561" alt="image" src="https://github.com/user-attachments/assets/b04d5572-23b2-4b9c-813c-a908c99f28be" />

<img width="676" height="484" alt="image" src="https://github.com/user-attachments/assets/65792adc-61af-4719-af0a-5ce1cccc62c6" />

# Eliminacion
<img width="554" height="383" alt="image" src="https://github.com/user-attachments/assets/dc987b9a-fe80-4a1f-bbef-5c1ec2d53b74" />

<img width="597" height="189" alt="image" src="https://github.com/user-attachments/assets/42573ef2-f86b-4378-bbb3-c10073e80420" />


#Validacion 
Validacion con los .get

<img width="185" height="374" alt="image" src="https://github.com/user-attachments/assets/29c6e02d-9ad7-4bd2-ad46-2d362d0a4848" />


#Tabla Treviuw
<img width="919" height="205" alt="image" src="https://github.com/user-attachments/assets/d8ea0528-4145-4e86-9dac-f51bf5804bc9" />

<img width="565" height="255" alt="image" src="https://github.com/user-attachments/assets/e761c186-880b-40df-a0ed-c64e860a7def" />

<img width="520" height="644" alt="image" src="https://github.com/user-attachments/assets/bd9aa68f-8205-4376-a2d1-3ce63b8df948" />
seleccion de un registro


codigo fuente en funcionamiento






# Estrutura del preyecto
       ├── BaseUsuario.db       # Base de datos SQLite (se crea sola al ejecutar la app)

       ├── main.py              # Código principal con la interfaz de Tkinter y lógica CRUD

       ├── README.md            # Guia principal del proyecto

       └── README_Preguntas.md  # Respuestas a la pregunatas del punto 13.
