"""
Crear un programa que pida al usuario su nombre, 
apellido paterno, apellido materno, edad, peso y estatura, 
desplegarlos en pantalla junto con su Índice de Masa Corporal (IMC).

El programa no puede permitir que ningún dato quede vacío, 
además de asegurarse de que en los campos de edad, peso y 
estatura el usuario introduzca una cifra. Todo esto antes 
de proceder con el cálculo del IMC siguiendo la fórmula:

Peso / estatura2   -> Peso sobre estatura al cuadrado

"""
print('='*50)
print('\t\u2730\tCALCULADORA DE I.M.C\t\u2730')
print('='*50)

print('\n***INGRESA LOS DATOS SOLICITADOS***\n')

#Nombre
while True:
    nombre = str(input('1-Ingresa nombre: ')).strip()
    if nombre:
        break
    else:
        print('\u26A0\uFE0F\tNo puedes dejar espacios vacíos, intenta de nuevo\t\u26A0\uFE0F')

#Apellido paterno
while True:
    apellidop = str(input('2-Ingresa apellido paterno: ')).strip()
    if apellidop:
        break
    else:
        print('\u26A0\uFE0F\tNo puedes dejar espacios vacíos, intenta de nuevo\t\u26A0\uFE0F')

#Apellido materno
while True:
    apellidom = str(input('3-Ingresa apellido materno: ')).strip()
    if apellidom:
        break
    else:
        print('\u26A0\uFE0F\tNo puedes dejar espacios vacíos, intenta de nuevo\t\u26A0\uFE0F')

# Edad
while True:
    edad_str = input('4-Ingresa edad: ').strip()
    if edad_str.isdigit():  # Verifica que solo haya números
        edad = int(edad_str)
        if edad > 0:  # Asegura que la edad sea positiva
            break
        else:
            print('⚠️ La edad debe ser mayor a 0. Intenta de nuevo. ⚠️')
    else:
        print('⚠️ Ingresa una edad válida (solo números enteros). ⚠️')

# Peso
while True:
    peso_str = input('5-Ingresa peso en KG: ').strip()
    try:
        peso = float(peso_str)
        if peso > 0:  # Evita valores negativos
            break
        else:
            print('⚠️ El peso debe ser mayor a 0. Intenta de nuevo. ⚠️')
    except ValueError:
        print('⚠️ Ingresa un número válido para el peso. ⚠️')

# Estatura
while True:
    estatura_str = input('6-Ingresa estatura en METROS: ').strip()
    try:
        estatura = float(estatura_str)
        if estatura > 0:  # Evita valores negativos
            break
        else:
            print('⚠️ La estatura debe ser mayor a 0. Intenta de nuevo. ⚠️')
    except ValueError:
        print('⚠️ Ingresa un número válido para la estatura. ⚠️')

#Fórmula del IMC
imc = peso/(estatura ** 2)

print('\n***RESULTADOS***\n')
print('Nombre:', nombre)
print('Apellido paterno: ', apellidop)
print('Apellido materno: ', apellidom)
print('Edad: ', edad)
print('Peso: ', peso)
print('Estatura: ', estatura)
print('I.M.C = ', imc)
