from tkinter import *
from tkinter import ttk
from tkinter import messagebox
from tkinter import filedialog
import sqlite3
import os

from PIL import Image, ImageTk


# ========================================================
# CONFIGURACIÓN
# ========================================================

raiz = Tk()
raiz.title("Sistema de Gestión de Usuarios")
raiz.geometry("1150x700")
raiz.resizable(False, False)

# Color azul claro
COLOR_FONDO = "#DCEEFF"

raiz.configure(bg=COLOR_FONDO)

try:
    raiz.iconbitmap("Escudo_Junior.ico")
except:
    pass


# ========================================================
# VARIABLES
# ========================================================

id_seleccionado = StringVar()

nombre = StringVar()
apellido = StringVar()
direccion = StringVar()
ciudad = StringVar()
codigo_postal = StringVar()
correo = StringVar()
telefono = StringVar()

genero = StringVar(value="Masculino")
estado = IntVar()
tipo_usuario = StringVar(value="Seleccione")

ruta_imagen = StringVar()
ruta_archivo = StringVar()


# ========================================================
# CONEXIÓN A BASE DE DATOS
# ========================================================

def conexion_bbdd():

    conexion = sqlite3.connect("DB_SanchoPan.db")
    cursor = conexion.cursor()

    cursor.execute("""
        CREATE TABLE IF NOT EXISTS usuarios (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            nombre TEXT NOT NULL,
            apellido TEXT NOT NULL,
            telefono TEXT,
            direccion TEXT,
            ciudad TEXT,
            codigo_postal TEXT,
            correo TEXT,
            genero TEXT,
            estado INTEGER,
            tipo_usuario TEXT,
            comentarios TEXT,
            imagen TEXT,
            archivo TEXT
        )
    """)

    cursor.execute("PRAGMA table_info(usuarios)")

    columnas_bbdd = [
        columna[1]
        for columna in cursor.fetchall()
    ]

    if "comentarios" not in columnas_bbdd:

        cursor.execute(
            "ALTER TABLE usuarios ADD COLUMN comentarios TEXT"
        )

    conexion.commit()
    conexion.close()


conexion_bbdd()


# ========================================================
# FRAME PRINCIPAL
# ========================================================

miFrame = Frame(
    raiz,
    bg=COLOR_FONDO,
    bd=2,
    relief="groove",
    padx=10,
    pady=10
)

miFrame.pack(
    padx=10,
    pady=10,
    fill="x"
)


# ========================================================
# FRAME DEL FORMULARIO
# ========================================================

frame_formulario = Frame(
    miFrame,
    bg=COLOR_FONDO
)

frame_formulario.pack(
    side=LEFT,
    padx=10,
    pady=10
)


# ========================================================
# FRAME DE LA IMAGEN - DERECHA
# ========================================================

frame_imagen = Frame(
    miFrame,
    bg=COLOR_FONDO,
    width=180,
    height=180,
    bd=2,
    relief="groove"
)

frame_imagen.pack(
    side=RIGHT,
    padx=25,
    pady=10
)

frame_imagen.pack_propagate(False)


# ========================================================
# ESCUDO JUNIOR
# ========================================================

try:

    imagen_escudo = Image.open(
        "Escudo_Junior.png"
    )

    imagen_escudo.thumbnail(
        (150, 150)
    )

    imagen_escudo_tk = ImageTk.PhotoImage(
        imagen_escudo
    )

    etiqueta_escudo = Label(
        frame_imagen,
        image=imagen_escudo_tk,
        bg=COLOR_FONDO
    )

    etiqueta_escudo.pack(
        expand=True
    )

except Exception as error:

    etiqueta_escudo = Label(
        frame_imagen,
        text="Escudo\nno encontrado",
        bg=COLOR_FONDO,
        font=("Arial", 12, "bold")
    )

    etiqueta_escudo.pack(
        expand=True
    )


# ========================================================
# TÍTULO
# ========================================================

Label(
    frame_formulario,
    text="FORMULARIO DE REGISTRO DE USUARIOS",
    font=("Arial", 16, "bold"),
    bg=COLOR_FONDO
).grid(
    row=0,
    column=0,
    columnspan=6,
    pady=10
)


# ========================================================
# NOMBRE
# ========================================================

Label(
    frame_formulario,
    text="Nombre:",
    bg=COLOR_FONDO
).grid(
    row=1,
    column=0,
    padx=5,
    pady=5,
    sticky="e"
)

Entry(
    frame_formulario,
    textvariable=nombre,
    width=25
).grid(
    row=1,
    column=1,
    padx=5,
    pady=5
)


# ========================================================
# APELLIDO
# ========================================================

Label(
    frame_formulario,
    text="Apellido:",
    bg=COLOR_FONDO
).grid(
    row=1,
    column=2,
    padx=5,
    pady=5,
    sticky="e"
)

Entry(
    frame_formulario,
    textvariable=apellido,
    width=25
).grid(
    row=1,
    column=3,
    padx=5,
    pady=5
)


# ========================================================
# TELÉFONO
# ========================================================

Label(
    frame_formulario,
    text="Teléfono:",
    bg=COLOR_FONDO
).grid(
    row=1,
    column=4,
    padx=5,
    pady=5,
    sticky="e"
)

Entry(
    frame_formulario,
    textvariable=telefono,
    width=25
).grid(
    row=1,
    column=5,
    padx=5,
    pady=5
)


# ========================================================
# DIRECCIÓN
# ========================================================

Label(
    frame_formulario,
    text="Dirección:",
    bg=COLOR_FONDO
).grid(
    row=2,
    column=0,
    padx=5,
    pady=5,
    sticky="e"
)

Entry(
    frame_formulario,
    textvariable=direccion,
    width=25
).grid(
    row=2,
    column=1,
    padx=5,
    pady=5
)


# ========================================================
# CIUDAD
# ========================================================

Label(
    frame_formulario,
    text="Ciudad:",
    bg=COLOR_FONDO
).grid(
    row=2,
    column=2,
    padx=5,
    pady=5,
    sticky="e"
)

Entry(
    frame_formulario,
    textvariable=ciudad,
    width=25
).grid(
    row=2,
    column=3,
    padx=5,
    pady=5
)


# ========================================================
# CORREO
# ========================================================

Label(
    frame_formulario,
    text="Correo:",
    bg=COLOR_FONDO
).grid(
    row=2,
    column=4,
    padx=5,
    pady=5,
    sticky="e"
)

Entry(
    frame_formulario,
    textvariable=correo,
    width=25
).grid(
    row=2,
    column=5,
    padx=5,
    pady=5
)


# ========================================================
# CÓDIGO POSTAL
# ========================================================

Label(
    frame_formulario,
    text="Código Postal:",
    bg=COLOR_FONDO
).grid(
    row=3,
    column=0,
    padx=5,
    pady=5,
    sticky="e"
)

Entry(
    frame_formulario,
    textvariable=codigo_postal,
    width=25
).grid(
    row=3,
    column=1,
    padx=5,
    pady=5
)


# ========================================================
# GÉNERO
# ========================================================

Label(
    frame_formulario,
    text="Género:",
    bg=COLOR_FONDO
).grid(
    row=3,
    column=2,
    padx=5,
    pady=5
)


Radiobutton(
    frame_formulario,
    text="Masculino",
    variable=genero,
    value="Masculino",
    bg=COLOR_FONDO
).grid(
    row=3,
    column=3,
    sticky="w"
)


Radiobutton(
    frame_formulario,
    text="Femenino",
    variable=genero,
    value="Femenino",
    bg=COLOR_FONDO
).grid(
    row=4,
    column=3,
    sticky="w"
)


# ========================================================
# COMENTARIOS
# ========================================================

Label(
    frame_formulario,
    text="Comentarios:",
    bg=COLOR_FONDO
).grid(
    row=3,
    column=4,
    padx=5,
    pady=5,
    sticky="ne"
)


entrada_comentarios = Text(
    frame_formulario,
    width=25,
    height=4
)

entrada_comentarios.grid(
    row=3,
    column=5,
    rowspan=3,
    padx=5,
    pady=5
)


# ========================================================
# ESTADO
# ========================================================

Checkbutton(
    frame_formulario,
    text="Usuario activo",
    variable=estado,
    bg=COLOR_FONDO
).grid(
    row=5,
    column=1,
    pady=5
)


# ========================================================
# TIPO DE USUARIO
# ========================================================

Label(
    frame_formulario,
    text="Tipo de usuario:",
    bg=COLOR_FONDO
).grid(
    row=5,
    column=2,
    padx=5,
    pady=5
)


combo_tipo = ttk.Combobox(
    frame_formulario,
    textvariable=tipo_usuario,
    values=[
        "Administrador",
        "Docente",
        "Estudiante",
        "Invitado"
    ],
    state="readonly",
    width=22
)

combo_tipo.grid(
    row=5,
    column=3,
    padx=5,
    pady=5
)


# ========================================================
# FUNCIÓN LIMPIAR
# ========================================================

def limpiar():

    id_seleccionado.set("")

    nombre.set("")
    apellido.set("")
    telefono.set("")
    direccion.set("")
    ciudad.set("")
    codigo_postal.set("")
    correo.set("")

    genero.set("Masculino")
    estado.set(0)
    tipo_usuario.set("Seleccione")

    # CORREGIDO
    entrada_comentarios.delete(
        "1.0",
        END
    )

    ruta_imagen.set("")
    ruta_archivo.set("")

    etiqueta_imagen.config(
        image=""
    )

    etiqueta_imagen.image = None

    etiqueta_archivo.config(
        text="Archivo: No adjunto"
    )


# ========================================================
# IMAGEN DEL USUARIO
# ========================================================

def seleccionar_imagen():

    archivo = filedialog.askopenfilename(
        title="Seleccionar imagen",
        filetypes=[
            (
                "Imágenes",
                "*.png *.jpg *.jpeg *.gif"
            ),
            (
                "Todos los archivos",
                "*.*"
            )
        ]
    )

    if archivo:

        ruta_imagen.set(
            archivo
        )

        try:

            imagen = Image.open(
                archivo
            )

            imagen.thumbnail(
                (150, 150)
            )

            imagen_tk = ImageTk.PhotoImage(
                imagen
            )

            etiqueta_imagen.config(
                image=imagen_tk
            )

            etiqueta_imagen.image = imagen_tk

        except Exception as error:

            messagebox.showerror(
                "Error",
                f"No se pudo cargar la imagen:\n{error}"
            )


# ========================================================
# ARCHIVO
# ========================================================

def seleccionar_archivo():

    archivo = filedialog.askopenfilename(
        title="Seleccionar archivo",
        filetypes=[
            (
                "Documentos",
                "*.pdf *.docx *.xlsx *.txt"
            ),
            (
                "Todos los archivos",
                "*.*"
            )
        ]
    )

    if archivo:

        ruta_archivo.set(
            archivo
        )

        nombre_archivo = os.path.basename(
            archivo
        )

        etiqueta_archivo.config(
            text=f"Archivo: {nombre_archivo}"
        )


# ========================================================
# INSERTAR
# ========================================================

def insertar():

    if nombre.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Debe ingresar el nombre."
        )

        return

    if apellido.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Debe ingresar el apellido."
        )

        return

    if telefono.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Debe ingresar el teléfono."
        )

        return

    if direccion.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Debe ingresar la dirección."
        )

        return

    if ciudad.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Debe ingresar la ciudad."
        )

        return

    if codigo_postal.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Debe ingresar el código postal."
        )

        return

    if correo.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Debe ingresar el correo."
        )

        return

    if tipo_usuario.get() == "Seleccione":

        messagebox.showwarning(
            "Advertencia",
            "Debe seleccionar el tipo de usuario."
        )

        return


    # ====================================================
    # COMENTARIOS
    # ====================================================

    texto_comentarios = entrada_comentarios.get(
        "1.0",
        END
    ).strip()


    conexion = sqlite3.connect(
        "DB_SanchoPan.db"
    )

    cursor = conexion.cursor()


    cursor.execute("""
        INSERT INTO usuarios
        (
            nombre,
            apellido,
            telefono,
            direccion,
            ciudad,
            codigo_postal,
            correo,
            genero,
            estado,
            tipo_usuario,
            comentarios,
            imagen,
            archivo
        )
        VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?)
    """, (

        nombre.get(),
        apellido.get(),
        telefono.get(),
        direccion.get(),
        ciudad.get(),
        codigo_postal.get(),
        correo.get(),
        genero.get(),
        estado.get(),
        tipo_usuario.get(),

        texto_comentarios,

        ruta_imagen.get(),
        ruta_archivo.get()
    ))


    conexion.commit()
    conexion.close()


    messagebox.showinfo(
        "Registro",
        "Usuario registrado correctamente."
    )


    mostrar_datos()
    limpiar()


# ========================================================
# MOSTRAR DATOS
# ========================================================

def mostrar_datos():

    for elemento in tabla.get_children():

        tabla.delete(
            elemento
        )


    conexion = sqlite3.connect(
        "DB_SanchoPan.db"
    )

    cursor = conexion.cursor()


    cursor.execute("""
        SELECT
            id,
            nombre,
            apellido,
            telefono,
            direccion,
            ciudad,
            codigo_postal,
            correo,
            genero,
            estado,
            tipo_usuario,
            comentarios,
            imagen,
            archivo
        FROM usuarios
        ORDER BY id DESC
    """)


    registros = cursor.fetchall()

    conexion.close()


    for registro in registros:

        estado_texto = (
            "Activo"
            if registro[9] == 1
            else "Inactivo"
        )


        tabla.insert(
            "",
            END,
            values=(
                registro[0],
                registro[1],
                registro[2],
                registro[3],
                registro[4],
                registro[5],
                registro[6],
                registro[7],
                registro[8],
                estado_texto,
                registro[10],
                registro[11]
            )
        )


# ========================================================
# SELECCIONAR REGISTRO
# ========================================================

def seleccionar_registro(event):

    seleccionado = tabla.focus()

    if not seleccionado:
        return


    datos = tabla.item(
        seleccionado,
        "values"
    )


    if not datos:
        return


    id_seleccionado.set(
        datos[0]
    )

    nombre.set(
        datos[1]
    )

    apellido.set(
        datos[2]
    )

    telefono.set(
        datos[3]
    )

    direccion.set(
        datos[4]
    )

    ciudad.set(
        datos[5]
    )

    codigo_postal.set(
        datos[6]
    )

    correo.set(
        datos[7]
    )

    genero.set(
        datos[8]
    )


    # ====================================================
    # CARGAR COMENTARIOS
    # ====================================================

    entrada_comentarios.delete(
        "1.0",
        END
    )

    entrada_comentarios.insert(
        "1.0",
        datos[11]
    )


    if datos[9] == "Activo":

        estado.set(1)

    else:

        estado.set(0)


    tipo_usuario.set(
        datos[10]
    )


    cargar_archivos_registro(
        datos[0]
    )


# ========================================================
# CARGAR IMAGEN Y ARCHIVO
# ========================================================

def cargar_archivos_registro(
    id_usuario
):

    conexion = sqlite3.connect(
        "DB_SanchoPan.db"
    )

    cursor = conexion.cursor()


    cursor.execute(
        """
        SELECT imagen, archivo
        FROM usuarios
        WHERE id = ?
        """,
        (id_usuario,)
    )


    registro = cursor.fetchone()

    conexion.close()


    if not registro:
        return


    imagen = registro[0]
    archivo = registro[1]


    ruta_imagen.set(
        imagen if imagen else ""
    )

    ruta_archivo.set(
        archivo if archivo else ""
    )


    if archivo:

        etiqueta_archivo.config(
            text=f"Archivo: {os.path.basename(archivo)}"
        )

    else:

        etiqueta_archivo.config(
            text="Archivo: No adjunto"
        )


    if imagen and os.path.exists(imagen):

        try:

            img = Image.open(
                imagen
            )

            img.thumbnail(
                (150, 150)
            )

            img_tk = ImageTk.PhotoImage(
                img
            )

            etiqueta_imagen.config(
                image=img_tk
            )

            etiqueta_imagen.image = img_tk

        except:

            etiqueta_imagen.config(
                image=""
            )

            etiqueta_imagen.image = None

    else:

        etiqueta_imagen.config(
            image=""
        )

        etiqueta_imagen.image = None


# ========================================================
# ACTUALIZAR
# ========================================================

def actualizar():

    if id_seleccionado.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Seleccione primero un registro."
        )

        return


    texto_comentarios = entrada_comentarios.get(
        "1.0",
        END
    ).strip()


    conexion = sqlite3.connect(
        "DB_SanchoPan.db"
    )

    cursor = conexion.cursor()


    cursor.execute("""
        UPDATE usuarios
        SET
            nombre = ?,
            apellido = ?,
            telefono = ?,
            direccion = ?,
            ciudad = ?,
            codigo_postal = ?,
            correo = ?,
            genero = ?,
            estado = ?,
            tipo_usuario = ?,
            comentarios = ?,
            imagen = ?,
            archivo = ?
        WHERE id = ?
    """, (

        nombre.get(),
        apellido.get(),
        telefono.get(),
        direccion.get(),
        ciudad.get(),
        codigo_postal.get(),
        correo.get(),
        genero.get(),
        estado.get(),
        tipo_usuario.get(),

        texto_comentarios,

        ruta_imagen.get(),
        ruta_archivo.get(),

        id_seleccionado.get()
    ))


    conexion.commit()
    conexion.close()


    messagebox.showinfo(
        "Actualizar",
        "Registro actualizado correctamente."
    )


    mostrar_datos()
    limpiar()


# ========================================================
# ELIMINAR
# ========================================================

def eliminar():

    if id_seleccionado.get() == "":

        messagebox.showwarning(
            "Advertencia",
            "Seleccione un registro."
        )

        return


    respuesta = messagebox.askyesno(
        "Eliminar",
        "¿Está seguro de eliminar este registro?"
    )


    if respuesta:

        conexion = sqlite3.connect(
            "DB_SanchoPan.db"
        )

        cursor = conexion.cursor()


        cursor.execute(
            "DELETE FROM usuarios WHERE id = ?",
            (id_seleccionado.get(),)
        )


        conexion.commit()
        conexion.close()


        messagebox.showinfo(
            "Eliminar",
            "Registro eliminado correctamente."
        )


        mostrar_datos()
        limpiar()


# ========================================================
# BUSCAR
# ========================================================

def buscar():

    texto = entrada_buscar.get()


    for elemento in tabla.get_children():

        tabla.delete(
            elemento
        )


    conexion = sqlite3.connect(
        "DB_SanchoPan.db"
    )

    cursor = conexion.cursor()


    cursor.execute("""
        SELECT
            id,
            nombre,
            apellido,
            telefono,
            direccion,
            ciudad,
            codigo_postal,
            correo,
            genero,
            estado,
            tipo_usuario,
            comentarios,
            imagen,
            archivo
        FROM usuarios
        WHERE nombre LIKE ?
           OR apellido LIKE ?
           OR ciudad LIKE ?
        ORDER BY id DESC
    """, (

        "%" + texto + "%",
        "%" + texto + "%",
        "%" + texto + "%"
    ))


    registros = cursor.fetchall()

    conexion.close()


    for registro in registros:

        estado_texto = (
            "Activo"
            if registro[9] == 1
            else "Inactivo"
        )


        tabla.insert(
            "",
            END,
            values=(
                registro[0],
                registro[1],
                registro[2],
                registro[3],
                registro[4],
                registro[5],
                registro[6],
                registro[7],
                registro[8],
                estado_texto,
                registro[10],
                registro[11]
            )
        )


# ========================================================
# SALIR
# ========================================================

def salir_programa():

    respuesta = messagebox.askyesno(
        "Salir",
        "¿Está seguro de que desea salir del programa?"
    )


    if respuesta:

        raiz.destroy()


# ========================================================
# FRAME BOTONES
# ========================================================

frame_botones = Frame(
    raiz,
    bg=COLOR_FONDO,
    bd=2,
    relief="groove",
    padx=10,
    pady=10
)

frame_botones.pack(
    padx=10,
    pady=5,
    fill="x"
)


Button(
    frame_botones,
    text="➕ INSERTAR",
    command=insertar,
    bg="#27AE60",
    fg="white",
    font=("Arial", 10, "bold"),
    width=15
).pack(
    side=LEFT,
    padx=5
)


Button(
    frame_botones,
    text="🔄 ACTUALIZAR",
    command=actualizar,
    bg="#F39C12",
    fg="white",
    font=("Arial", 10, "bold"),
    width=15
).pack(
    side=LEFT,
    padx=5
)


Button(
    frame_botones,
    text="ELIMINAR",
    command=eliminar,
    bg="#F31212",
    fg="white",
    font=("Arial", 10, "bold"),
    width=15
).pack(
    side=LEFT,
    padx=5
)


Button(
    frame_botones,
    text="🧹 LIMPIAR",
    command=limpiar,
    bg="#34495E",
    fg="white",
    font=("Arial", 10, "bold"),
    width=15
).pack(
    side=LEFT,
    padx=5
)


Button(
    frame_botones,
    text="🚪 SALIR",
    command=salir_programa,
    bg="#7F8C8D",
    fg="white",
    font=("Arial", 10, "bold"),
    width=15
).pack(
    side=LEFT,
    padx=5
)


# ========================================================
# BUSCADOR
# ========================================================

frame_buscar = Frame(
    raiz,
    bg=COLOR_FONDO
)

frame_buscar.pack(
    padx=10,
    pady=5,
    fill="x"
)


Label(
    frame_buscar,
    text="Buscar:",
    bg=COLOR_FONDO
).pack(
    side=LEFT,
    padx=5
)


entrada_buscar = Entry(
    frame_buscar,
    width=40
)

entrada_buscar.pack(
    side=LEFT,
    padx=5
)


Button(
    frame_buscar,
    text="🔍 BUSCAR",
    command=buscar,
    bg="#2980B9",
    fg="white",
    width=15
).pack(
    side=LEFT,
    padx=5
)


Button(
    frame_buscar,
    text="MOSTRAR TODOS",
    command=mostrar_datos,
    bg="#16A085",
    fg="white",
    width=15
).pack(
    side=LEFT,
    padx=5
)


# ========================================================
# FRAME TREEVIEW
# ========================================================

frame_tabla = Frame(
    raiz,
    bg=COLOR_FONDO,
    bd=2,
    relief="groove"
)

frame_tabla.pack(
    padx=10,
    pady=5,
    fill="both",
    expand=True
)


scroll_vertical = Scrollbar(
    frame_tabla,
    orient=VERTICAL
)

scroll_vertical.pack(
    side=RIGHT,
    fill=Y
)


scroll_horizontal = Scrollbar(
    frame_tabla,
    orient=HORIZONTAL
)

scroll_horizontal.pack(
    side=BOTTOM,
    fill=X
)


# ========================================================
# TREEVIEW
# ========================================================

columnas = (
    "ID",
    "Nombre",
    "Apellido",
    "Teléfono",
    "Dirección",
    "Ciudad",
    "Código Postal",
    "Correo",
    "Género",
    "Estado",
    "Tipo Usuario",
    "Comentarios"
)


tabla = ttk.Treeview(
    frame_tabla,
    columns=columnas,
    show="headings",
    yscrollcommand=scroll_vertical.set,
    xscrollcommand=scroll_horizontal.set,
    height=10
)


for columna in columnas:

    tabla.heading(
        columna,
        text=columna
    )

    tabla.column(
        columna,
        width=120,
        anchor="center"
    )


tabla.column(
    "ID",
    width=40
)

tabla.column(
    "Nombre",
    width=90
)

tabla.column(
    "Apellido",
    width=90
)

tabla.column(
    "Teléfono",
    width=90
)

tabla.column(
    "Dirección",
    width=100
)

tabla.column(
    "Ciudad",
    width=90
)

tabla.column(
    "Código Postal",
    width=90
)

tabla.column(
    "Correo",
    width=130
)

tabla.column(
    "Género",
    width=80
)

tabla.column(
    "Estado",
    width=80
)

tabla.column(
    "Tipo Usuario",
    width=110
)

tabla.column(
    "Comentarios",
    width=180
)


tabla.pack(
    side=LEFT,
    fill=BOTH,
    expand=True
)


scroll_vertical.config(
    command=tabla.yview
)

scroll_horizontal.config(
    command=tabla.xview
)


tabla.bind(
    "<ButtonRelease-1>",
    seleccionar_registro
)


# ========================================================
# ETIQUETA PARA IMAGEN DEL USUARIO
# ========================================================

etiqueta_imagen = Label(
    frame_formulario,
    bg=COLOR_FONDO,
    width=20,
    height=8,
    relief="sunken"
)

# Esta es la imagen que se selecciona para cada usuario.
# Está en una posición independiente del escudo.


# ========================================================
# ETIQUETA ARCHIVO
# ========================================================

etiqueta_archivo = Label(
    frame_formulario,
    text="Archivo: No adjunto",
    bg=COLOR_FONDO,
    width=30,
    anchor="w"
)


# ========================================================
# BOTONES DE IMAGEN Y ARCHIVO
# ========================================================

Button(
    frame_formulario,
    text="Seleccionar Imagen",
    command=seleccionar_imagen,
    bg="#3498DB",
    fg="white",
    width=20
).grid(
    row=6,
    column=1,
    padx=5,
    pady=5
)


Button(
    frame_formulario,
    text="📎 Adjuntar Archivo",
    command=seleccionar_archivo,
    bg="#9B59B6",
    fg="white",
    width=20
).grid(
    row=7,
    column=1,
    padx=5,
    pady=5
)


etiqueta_archivo.grid(
    row=8,
    column=0,
    columnspan=2,
    padx=5,
    pady=5
)


# ========================================================
# MENÚ
# ========================================================

barra_menu = Menu(
    raiz
)


menu_principal = Menu(
    barra_menu,
    tearoff=0
)


menu_principal.add_command(
    label="Limpiar formulario",
    command=limpiar
)


menu_principal.add_command(
    label="Mostrar todos",
    command=mostrar_datos
)


menu_principal.add_separator()


menu_principal.add_command(
    label="Salir",
    command=salir_programa
)


barra_menu.add_cascade(
    label="Menú",
    menu=menu_principal
)


# ========================================================
# AYUDA
# ========================================================

menu_ayuda = Menu(
    barra_menu,
    tearoff=0
)


menu_ayuda.add_command(
    label="Acerca del sistema",
    command=lambda: messagebox.showinfo(
        "Ayuda",
        "SISTEMA DE GESTIÓN DE USUARIOS\n\n"
        "Este sistema permite:\n\n"
        "• Registrar usuarios\n"
        "• Actualizar usuarios\n"
        "• Eliminar usuarios\n"
        "• Buscar usuarios\n"
        "• Adjuntar imágenes\n"
        "• Adjuntar archivos\n"
        "• Agregar comentarios\n\n"
        "Versión 1.0"
    )
)


barra_menu.add_cascade(
    label="Ayuda",
    menu=menu_ayuda
)


barra_menu.add_command(
    label="Salir",
    command=salir_programa
)


raiz.config(
    menu=barra_menu
)


# ========================================================
# MOSTRAR DATOS INICIALES
# ========================================================

mostrar_datos()


# ========================================================
# EJECUTAR
# ========================================================

raiz.mainloop()
