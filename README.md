# ejemplosAdso09
Repositorio para ejemplos de ADSO-09

import tkinter as tk

def validar():
    usuario = e_login.get()
    contra = e_pass.get()
    if usuario=="usuario" and contra=="1234":
        l_mensaje.configure(text="Bienvenido al programa")
    else:
        l_mensaje.configure(text="Credenciales incorrectas")

ventana = tk.Tk()
ventana.geometry("300x400")
ventana.title("Mi primer ventana")
titulo = tk.Label(ventana, text="Programa de gestión comercial")
titulo.place(x=80,y=50)
l_login = tk.Label(ventana,text="Usuario: ")
l_login.place(x=50,y=100)
e_login = tk.Entry(width=15)
e_login.place(x=120,y=100)
l_pass = tk.Label(ventana,text="Contraseña: ")
l_pass.place(x=50,y=130)
e_pass = tk.Entry(show="*", width=15)
e_pass.place(x=120,y=130)
b_ingresar = tk.Button(ventana,text="Ingresar",command=validar)
b_ingresar.place(x=90, y=180)
l_mensaje = tk.Label(ventana,text="")
l_mensaje.place(x=50,y=210)


ventana.mainloop()
