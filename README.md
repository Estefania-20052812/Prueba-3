import os
os.system("cls")

#registro
#costo
#listar vehículos

menu = """
1. Registrar vehículo
2. Listado de vehiculo(s)
3. Orden de reparación
4. Salir
"""
marcas = ["ford", "chevrolet", "toyota"]
vehiculos = []

def registro():
    while True:
        os.system("cls")
        try:
            marca = input("Marca: ").lower()
            año = int(input("Año de fabricación: "))
            km = int(input("Kilometraje: "))
            costoestimado = int(input("Costo estimado: "))
            if marca in marcas and año>0 and costoestimado>0 and km>0:
               impuesto = round(costoestimado*0.08)
               total = round(costoestimado+impuesto)
               vehiculos.append([marca, año, km, costoestimado, impuesto, total])
            else:
                input("Error, reingrese")
        except:
            input("Excepción")

def listado():
    os.system("cls")
    try:
        lis = int(input("1. Listar todos \n2. Listar por marca"))
        if lis == 1:
            for v in vehiculos:
                vaa += f"{v[0]:15s}" #marca
                vaa += f"{v[1]:6d}" #año
                vaa += f"{v[2]:8s}" #km
                vaa += f"{v[3]:15d}" #costo estimado
                vaa += f"{v[4]:12d}" #impuesto
                vaa += f"{v[5]:18d}" #total a pagar
        elif lis == 2:
            eleccion = input(" Búsqueda por marca \n Marca elegida: ").lower
            if eleccion in marcas:
                vaa += f"{eleccion[0]:15s}" #marca 
                vaa += f"{eleccion[1]:6d}" #año
                vaa += f"{eleccion[2]:8d}" #km
                vaa += f"{eleccion[3]:15d}" #costo estimado
                vaa += f"{eleccion[4]:12d}" #impuesto
                vaa += f"{eleccion[5]:18d}" #total a pagar
            else:
                input("Error")
    except Exception as e:
                input(f"Excepción: {e}")

def imprimirorden():
    os.system("cls")
    pass

while True:
    os.system("cls")
    opc = input(f"{menu} \n")
    if opc == "4":
        break
    elif opc == "1":
        registro()
    elif opc == "2":
        listado()
    elif opc == "3":
        imprimirorden()
