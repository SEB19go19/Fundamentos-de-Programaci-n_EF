
#variables qeu usare
codigos = []
descripciones = []
cantidades = []
precios = []

try:
    archivo = open("catalogo_productos.txt", "r")
    for linea in archivo:
        linea = linea.strip()
        if linea != "":
            partes = linea.split(",")
            codigos.append(partes[0])
            descripciones.append(partes[1])
            cantidades.append(int(partes[2]))
            precios.append(float(partes[3]))
    archivo.close()
except:
    print("no hay un archivo anterior")

opcion = ""

#bucle general
while opcion != "5":
    print("\n Productos")
    print("1 mostrar catalogo")
    print("2 registrar nuevo producto")
    print("3 buscar producto por codigo")
    print("4 actualizar cantidad o precio")
    print("5 salir")
    
    opcion = input("elige una opcion 1 a 5: ")
    
    if opcion == "1":
        print("\nlista de productos")
        if len(codigos) == 0:
            print("el catalogo esta vacio")
        else:
            for i in range(len(codigos)):
                print("-------------------------")
                print("codigo:", codigos[i])
                print("descripcion:", descripciones[i])
                print("cantidad:", cantidades[i])
                print("precio s/:", precios[i])
                print("-------------------------")
                
    elif opcion == "2":
        print("\nregistrar producto")
        codigo = input("ingrese el codigo ")
        
        existe = False
        for i in range(len(codigos)):
            if codigos[i] == codigo:
                existe = True
                
        if existe:
            print("error ya existe un producto con ese codigo")
        else:
            descripcion = input("ingrese la descripcion ")
            cantidad = int(input("ingrese la cantidad "))
            precio = float(input("ingrese el precio "))
            
            codigos.append(codigo)
            descripciones.append(descripcion)
            cantidades.append(cantidad)
            precios.append(precio)
            
            archivo = open("catalogo_productos.txt", "w")
            for i in range(len(codigos)):
                linea = codigos[i] + "," + descripciones[i] + "," + str(cantidades[i]) + "," + str(precios[i]) + "\n"
                archivo.write(linea)
            archivo.close()
            
            print("se agrrego bien")
            
    elif opcion == "3":
        print("\nbuscar producto")
        buscado = input("ingrese el codigo a buscar: ")
        encontrado = False
        
        for i in range(len(codigos)):
            if codigos[i] == buscado:
                print("\nproducto encontrado")
                print("-------------------------")
                print("codigo:", codigos[i])
                print("descripcion:", descripciones[i])
                print("cantidad:", cantidades[i])
                print("precio s/:", precios[i])
                encontrado = True
                break
                
        if not encontrado:
            print("no se encontro ningun producto con ese codigo")
            
    elif opcion == "4":
        print("\nactualizar producto")
        buscado = input("ingrese el codigo del producto a modificar ")
        encontrado = False
        
        for i in range(len(codigos)):
            if codigos[i] == buscado:
                encontrado = True
                print("1 modificar cantidad")
                print("2 modificar precio")
                sub_opcion = input("seleccione una opcion 1 o 2 ")
                
                if sub_opcion == "1":
                    cantidades[i] = int(input("ingrese la nueva cantidad "))
                    print("cantidad actualizada")
                elif sub_opcion == "2":
                    precios[i] = float(input("ingrese el nuevo precio "))
                    print("precio actualizado")
                else:
                    print("opcion no valida")
                
                archivo = open("catalogo_productos.txt", "w")
                for j in range(len(codigos)):
                    linea = codigos[j] + "," + descripciones[j] + "," + str(cantidades[j]) + "," + str(precios[j]) + "\n"
                    archivo.write(linea)
                archivo.close()
                break
                
        if not encontrado:
            print("no se encontro el producto")
            
    elif opcion == "5":
        print("saliendo")
    else:
        print("ingrese un numero del 1 al 5")
