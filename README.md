# Funciones 

def multiplicar():
    resultado = 750*2
    print(resultado)

multiplicar()

def saludar_con_nombre(nombre): #(parametro)
    saludando = (f"Hola {nombre}")
    return saludando

devolucion = saludar_con_nombre("Valentin") #(argumento)
print(devolucion)

def test(): # primero va por dentro, y despues pasa por fuera
    variable_test = 5 # variable local, deberia imprimir 10 pero la def test imprime el 5 porque esta mas cerca
    print(variable_test)

variable_test = 10 # variable global
test()
print(variable_test)


def lista():
    return ["a", "b", "c"]

otra_lista = lista() # con corchetes llamo a la funcion
otra_lista.append("d") # como es lista uso append
print(otra_lista)
print(otra_lista[-1]) # hago un slicing y traigo al ultimo elemento

def suma(a, b):
    return a + b 

resultado = suma(7, 7) # argumento por posicion
print(resultado)

def sumar(primer_numero, segundo_numero):
    return primer_numero + segundo_numero

resultado = sumar(primer_numero=10, segundo_numero=5) # argumento por nombre  
print(resultado)

def saludar_ciudad(ciudad):
    mensaje = f"Le damos la bienvenida a {ciudad}"
    return mensaje 

saludo = saludar_ciudad("Buenos Aires")
print(saludo)

def promediar(notas: list[int]) -> float: # HAY ERRORES :/
    cantidad_notas = len(notas) # uso len para ver la cantidad de notas que hay
    promedio = sum(notas) / cantidad_notas
    return promedio

def ingresar_notas():
    notas = []
    while True:
        nota = input("Ingrese sus notas: ")
        if nota == "s":
            print("Saliendo")
            break
        else:
            nota = (nota) # corrobora que la nota sea un entero
            #nota.append(nota) # agrega hasta que se ingresa s por el while True
    return notas
           

def mostrar_datos(datos):
    print("*******")
    print(datos)


def main():
    mis_notas = ingresar_notas()
    mi_promedio = promediar(mis_notas)
    mostrar_datos(mi_promedio)

main()


# realizar una funcion separar() que tome una lista de numeros enteros y que devuelva 2 listas ordenadas
# usar sort() para ordenar las listas 

def separar(numeros: list): # separar recibe como parametro una lista
    numeros.sort() # para ordenarlos 
    pares = []
    impares = []
    for numero in numeros:
        if numero % 2 == 0:
            pares.append(numero)
        else:
            impares.append(numero)
    return pares, impares # siempre devuelve una tupla cuando tenemos varios elementos

lista = [4, 20, 7, 6, 3, 9, 10, 2]
copia_de_lista = lista.copy() # hacemos una copia para que no nos modifique la lista original

resultado = separar(copia_de_lista)
pares, impares = resultado

print(f"Numeros pares {pares}")
print(f"Numeros impares {impares}")
print(lista)




