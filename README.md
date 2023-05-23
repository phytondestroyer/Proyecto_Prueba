import time
import random

tarifa_base = 500
tarifa = 0
costo_kilometro = 100
costoK = 0
costo_minuto_espera = 20
costoM = 0
descuento = 0
total = 0


def es_numero(valor):
        try:
            float(valor)
            return True
        except ValueError:
            return False


# Destinos
aeropuerto = 2000


total_recaudado = 0
cantidad_viajes = 0

while True:
    
        
    
    print("---BIENVENIDO A RÁPIDO Y SEGURO---")
    print()
    print("LA TARIFA BASE ES: $500")
    print("COSTO POR KILÓMETRO: $100")
    print("COSTO POR MINUTO DE ESPERA: $20")
    print()
    print()
    print("1.- INGRESAR NUEVO VIAJE")
    print("2.- IMPRIMIR ESTADÍSTICA BÁSICA")
    print("3.- SALIR DE LA APLICACIÓN")

    try:
        opcion_menu = int(input("INGRESE UNA OPCIÓN: "))
        while opcion_menu not in [1, 2, 3]:
            print("INGRESE UNA OPCIÓN VÁLIDA")
            opcion_menu = int(input("INGRESE UNA OPCIÓN: "))
    except ValueError:
        print("OPCIÓN NO VÁLIDA. INTENTE NUEVAMENTE")
        
    if opcion_menu == 3:
        break
        
    if opcion_menu == 1:
        origen = input("INGRESE ORIGEN: ")
        print("DESEA VIAJAR AL AEROPUERTO?   1.Si   2.No")       
        try:
            opcion_destino = int(input("INGRESE UNA OPCION: "))
            while opcion_destino not in [1, 2]:
                print("INGRESE UNA OPCION VALIDA")
                opcion_destino = int(input("INGRESE LA OPCION NUEVAMENTE: "))
        except ValueError:
            print("OPCIÓN NO VÁLIDA. INTENTE NUEVAMENTE: ")

        if opcion_destino == 1:
            print("TIENES UN 20% DE DESCUENTO POR IR AL AEROPUERTO")
            tiempo_espera = 1 * 2
            print("VIAJE EN CURSO...")
            time.sleep(tiempo_espera)
            print("FIN DE SU VIAJE. MUCHAS GRACIAS")

                

            while True:
                Minutos = input("INGRESE LOS MINUTOS DE ESPERA: ")
                aeropuerto_klm = input("INGRESE LOS KILOMETROS RECORRIDOS: ")

                if es_numero(Minutos) and es_numero(aeropuerto_klm):
                    Minutos = int(Minutos)
                    aeropuerto_klm = int(aeropuerto_klm)
                    break
                else:
                    print("Error: Ingrese solo números.")

            
            print("---TICKET DE VIAJE---")
            print("ORIGEN DE VIAJE: ", origen)
            print("DESTINO DE VIAJE: ", "AEROPUERTO")
            print("TIEMPO DE ESPERA: ", Minutos, " minutos")
            print("DISTANCIA RECORRIDA: ", aeropuerto_klm, " km")
            print("TARIFA BASE: ", tarifa_base)
            costoK = costo_kilometro * aeropuerto_klm
            print("COSTO POR KILOMETRO: ", costoK)
            costoM = costo_minuto_espera * Minutos
            print("COSTO POR MINUTO DE ESPERA: ", costoM)
            
            totalsindescuento= tarifa_base + costo_kilometro * aeropuerto_klm
            descuento= totalsindescuento * 0.20
            print("DESCUENTOS APLICADOS: ", descuento)


            total = totalsindescuento - descuento  
            print("COSTO TOTAL: ", total)

            cantidad_viajes += 1
            total_recaudado += total

            input("INGRESE CUALQUIER TECLA PARA REGRESAR AL MENÚ: ")








        if opcion_destino == 2:
            destino = input("INGRESE DESTINO: ")
            print("ERES CLIENTE FRECUENTE?   1.Si   2.No")

            try:
                opcion_cliente = int(input("INGRESE UNA OPCION: "))
                while opcion_cliente not in [1, 2]:
                    print("INGRESE UNA OPCION VALIDA")
                    opcion_cliente = int(input("INGRESE LA OPCION NUEVAMENTE: "))
            except ValueError:
                print("OPCIÓN NO VÁLIDA. INTENTE NUEVAMENTE")

            if opcion_cliente == 1:
                tiempo_espera = 1 * 5
                print("INICIANDO VIAJE....")
                time.sleep(tiempo_espera)
                print("VIAJE FINALIZADO")

                
                

                while True:
                    Minutos = input("INGRESE LOS MINUTOS DE ESPERA: ")
                    kilometro_cliente = input("INGRESE LOS KILOMETROS RECORRIDOS: ")

                    if es_numero(Minutos) and es_numero(kilometro_cliente):
                        Minutos = int(Minutos)
                        kilometro_cliente = int(kilometro_cliente)
                        break
                    else:
                        print("Error: Ingrese solo números.")


                print("---TICKET DE VIAJE---")
                print("ORIGEN DE VIAJE: ", origen)
                print("DESTINO DE VIAJE: ", destino)
                print("TIEMPO DE ESPERA: ", Minutos, " minutos")
                print("DISTANCIA RECORRIDA: ", kilometro_cliente, " km")
                print("TARIFA BASE: ", tarifa_base)
                costoK = costo_kilometro * kilometro_cliente
                print("COSTO DE VIAJE: ", kilometro_cliente * costo_kilometro)

                costoM = costo_minuto_espera * Minutos
                print("COSTO POR MINUTO DE ESPERA: ", costoM)

                totalsindescuento = tarifa_base + costo_kilometro * kilometro_cliente
                descuento = totalsindescuento * 0.10
                print("DESCUENTOS APLICADOS: ", descuento)

                total = totalsindescuento - descuento 
                print("COSTO TOTAL: ", total)

                cantidad_viajes += 1
                total_recaudado += total

                input("INGRESE CUALQUIER TECLA PARA REGRESAR AL MENÚ: ")








            if opcion_cliente == 2:
                tiempo_espera = 1* 2
                print("INICIANDO VIAJE....")
                time.sleep(tiempo_espera)
                print("VIAJE FINALIZADO")


                while True:
                    Minutos = input("INGRESE LOS MINUTOS DE ESPERA: ")
                    kilometro_cliente = input("INGRESE LOS KILOMETROS RECORRIDOS: ")

                    if es_numero(Minutos) and es_numero(kilometro_cliente):
                        Minutos = int(Minutos)
                        kilometro_cliente = int(kilometro_cliente)
                        break
                    else:
                        print("Error: Ingrese solo números.")

                
                print("---TICKET DE VIAJE---")
                print("ORIGEN DE VIAJE: ", origen)
                print("DESTINO DE VIAJE: ", destino)
                print("TIEMPO DE ESPERA: ", Minutos, " minutos")
                print("DISTANCIA RECORRIDA: ", kilometro_cliente, "km")
                print("TARIFA BASE: ", tarifa_base)
                costoK = costo_kilometro * kilometro_cliente
                print("COSTO POR KILOMETRO: ", costoK)
                costoM = costo_minuto_espera * Minutos
                print("COSTO POR MINUTO DE ESPERA: ", costoM)
                print("DESCUENTOS APLICADOS: ", "0")

                total = tarifa_base + costo_kilometro * kilometro_cliente
                print("COSTO TOTAL: ", total)

                cantidad_viajes += 1
                total_recaudado += total

                input("INGRESE CUALQUIER TECLA PARA REGRESAR AL MENÚ: ")




    if opcion_menu == 2:
        print("CANTIDAD DE VIAJES REALIZADOS: ", cantidad_viajes)
        print("TOTAL RECAUDADO: $", total_recaudado)
        input("INGRESE CUALQUIER TECLA PARA REGRESAR AL MENÚ: ")
