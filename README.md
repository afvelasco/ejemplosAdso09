# ejemplosAdso09
Repositorio para ejemplos de ADSO-09

"""
Se trata de escribir un programa con un CRUD para clientes
Cada producto debe tener los siguientes datos:
Identificación (string), Nombre (string), saldo (float), 
cupo_crédito (float)
"""

import json
from clientes import Clientes

def crud_clientes(listado, mis_clientes):
    while True:
        print("GESTIÓN DE CLIENTES")
        print("1. Agregar")
        print("2. Buscar")
        print("3. Modificar")
        print("4. Borrar")
        print("5. Listar\n")
        print("0. Salir")
        opcion = input("Digite su opción: ")
        if opcion=="1":
            id = input("Id cliente: ")
            nom = input("Nombre: ")
            cup = float(input("Cupo de crédito: "))
            sal = int(input("Saldo: "))
            nuevo_cliente = {"id": id,
                            "nombre": nom,
                            "cupo": cup,
                            "saldo": sal}
            resultado = mis_clientes.agregar(nuevo_cliente)
            if resultado==0:
                print("Cliente agregado satisfactoriamente!")
            else:
                print("Id de cliente ya existe!")
        elif opcion=="2":
            id = input("Digite id a buscar: ")
            resultado = mis_clientes.buscar(id)
            if resultado==-1:
                print("Cliente no existe!")
            else:
                print(listado[resultado])
        elif opcion=="3":
            id = input("Digite id a modificar")
            resultado = mis_clientes.buscar(id)
            if resultado>-1:
                nom = input("Nuevo nombre: ")
                cup = float(input("Nuevo cupo de crédito: "))
                sal = int(input("Nuevo saldo: "))
                nuevo_producto = {"id": id,
                                "nombre": nom,
                                "cupo": cup,
                                "saldo": sal}
                mis_clientes.modificar(nuevo_producto)
            else:
                print("Cliente no existe!")
        elif opcion=="4":
            id = input("Digite id a borrar")
            resultado = mis_clientes.buscar(id)
            if resultado>-1:
                mis_clientes.borrar(id)
            else:
                print("Cliente no existe!")
        elif opcion=="5":
            mis_clientes.listar()
        elif opcion=="0":
            break
        else:
            print("Opción inválida")
