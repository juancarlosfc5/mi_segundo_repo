# Clase 1

1. 

```pseudocode
Algoritmo subsidio_transporte
	Definir distancia, salario, salario_minimo Como Entero
	Definir aplica_subsidio Como Logico
	
	Escribir "Bienvenido al programa para determinar beneficiarios de subsidio de transporte"
	Escribir "Ingrese su salario: "
	Leer salario
	Escribir "Ingrese su distancia en Km hasta el trabajo: "
	Leer distancia
	
	salario_minimo <- 1750000
	
	Si salario <= (salario_minimo * 2) Y distancia > 50 Entonces
		aplica_subsidio <- Verdadero
		Escribir "Aplica subsidio"
	SiNo
		Escribir "No aplica subsidio"
	Fin Si
	
FinAlgoritmo
```

2. 

```pseudocode
Algoritmo nota_estudiante
	Definir nota Como Real
	Escribir "Bienvenido al sistema de registro de notas"
	Escribir "Ingrese la nota del estudiante: "
	Leer nota
	
	Mientras (nota < 0 o nota > 5) Hacer
		Escribir "Ingrese una nota valida para el estudiante: "
		Leer nota
	Fin Mientras
	Escribir "La nota ingresada es valida"
	
FinAlgoritmo
```

3. 

```pseudocode
Algoritmo conteo_especial_rango
    Definir n, i, contador Como Entero

    Escribir "Ingrese un numero entero positivo:"
    Leer n

    contador <- 0

    Para i <- 1 Hasta n Con Paso 1 Hacer
        Si i MOD 2 = 0 Y i MOD 3 = 0 Entonces
            Escribir i
            contador <- contador + 1
        FinSi
    FinPara

    Escribir "Cantidad que cumplen la condicion: ", contador
FinAlgoritmo
```

4. 

```pseudocode
Algoritmo encuestas
	Definir clientes, i, calificacion, baja, media, alta Como Entero
	Escribir "Bienvenido al programa para registrar las encuentas de los clientes"
	Escribir "Ingrese el numero de clientes que van a responder la encuesta: "
	Leer clientes
	baja <- 0
	media <- 0
	alta <- 0
	Para i <- 1 Hasta clientes Con Paso 1 Hacer
		Repetir
			Escribir "Ingrese la calificación del cliente ", i, " (1 a 5): "
			Leer calificacion
		Hasta Que calificacion >= 1 Y calificacion <= 5
		Si calificacion <= 2 Entonces
			baja <- baja + 1
		SiNo
			Si calificacion = 3 Entonces
				media <- media + 1
			SiNo
				alta <- alta + 1
			Fin Si
		Fin Si
	Fin Para
	
	Escribir "La cantidad de respuestas bajas es: ", baja
	Escribir "La cantidad de respuestas medias es: ", media
	Escribir "La cantidad de respuestas altas es: ", alta
	
FinAlgoritmo
```

5. 

```pseudocode
Algoritmo revision_paquetes
	Definir paquetes, i Como Entero
	Definir peso, mayor_peso Como Real
	
	Escribir "Bienvenido al programa para revisar paquetes"
	Escribir "Ingrese el numero de parquetes que se van a registrar: "
	Leer paquetes
	
	mayor_peso <- 0
	
	Para i <- 1 Hasta paquetes Con Paso 1 Hacer
		Repetir
			Escribir "Ingrese el peso del paquete No. ", i, " (Kg): "
			Leer peso
		Hasta Que peso > 0
		
		Si peso > 50 Entonces
			Escribir "El paquete requiere revisión especial"
		Fin Si
		
		Si peso > mayor_peso Entonces
			mayor_peso <- peso
		Fin Si
		
	Fin Para
	
	Escribir "El paquete con mayor peso es de ", mayor_peso, " Kg"
	
FinAlgoritmo
```

# Clase 2

1. 

```pseudocode
Funcion bisiesto <- EsBisiesto(anio)
	Si ((anio MOD 4 = 0) Y (anio MOD 100 <> 0)) O (anio MOD 400 = 0) Entonces
		bisiesto <- Verdadero
	SiNo
		bisiesto <- Falso
	Fin Si
Fin Funcion

Algoritmo es_bisiesto
	Definir anios, i Como Entero
	
	Escribir "Bienvenido al programa para determinar si un año es bisiesto"
	
	Para i<-1 Hasta 5 Con Paso 1 Hacer
		Repetir
			Escribir "Ingrese el año No.", i, " :"
			Leer anios
		Hasta Que anios > 0
		
		Si EsBisiesto(anios) = Verdadero
			Escribir "El año es bisiesto"
		SiNo
			Escribir "El año NO es bisiesto"
		FinSi

	Fin Para

FinAlgoritmo
```

2. 

```pseudocode
Funcion tarifa <- TarifaPeaje(tipoVehiculo)
	Segun tipoVehiculo Hacer
		1:
			tarifa <- 1500
		2:
			tarifa <- 4500
		3:
			tarifa <- 10000
		4:
			tarifa <- 20000
		De Otro Modo:
			tarifa <- 0
	Fin Segun
Fin Funcion

Algoritmo peaje
	Definir vehiculos, tipo, i, total_recaudado Como Entero
	
	Escribir "Bienvenido al programa para calcular el total recaudado por el peaje"
	Escribir "Ingrese la cantidad de vehiculos que pasaron por el peaje: "
	Leer vehiculos
	
	total_recaudado <- 0
	
	Para i <- 1 Hasta vehiculos Con Paso 1 Hacer
		Escribir "Ingrese el tipo de vehiculo (1 moto, 2 carro, 3 camion, 4 mula):"
		Leer tipo
		Escribir "El valor de la tarifa es: ", TarifaPeaje(tipo)
		total_recaudado <- total_recaudado + TarifaPeaje(tipo)
		
	Fin Para
	
	Escribir "El total recaudado es: ", total_recaudado
	
FinAlgoritmo
```

3. 

```pseudocode
Funcion nivel <- NivelRiesgo(temperatura, presion)
	Si temperatura > 80 O presion > 120 Entonces
		nivel <- "ALTO"
	SiNo
		Si (temperatura > 60 Y temperatura < 80) O (presion > 90 Y presion < 120) Entonces
			nivel <- "MEDIO"
		SiNo
			nivel <- "BAJO"
		Fin Si
	Fin Si
Fin Funcion

Algoritmo maquinas
	Definir t, p Como Real
	Definir i, total_alto Como Entero
	Definir nivel Como Caracter
	
	total_alto <- 0
	
	Escribir "Bienvenido al programa para calcular el nivel de riesgo de las maquinas"

	Para i <- 1 Hasta 7 Con Paso 1 Hacer
		Escribir "Ingrese la temperatura: "
		Leer t
		Escribir "Ingrese la presion: "
		Leer p
		
		nivel <- NivelRiesgo(t, p)
		Escribir "El nivel de riesgo de la maquina es: ", nivel
		
		Si nivel = "ALTO" Entonces
			total_alto = total_alto + 1
		Fin Si
		
	Fin Para
	
	Escribir ""
	Escribir "El total de maquina con nivel alto es: ", total_alto
	
FinAlgoritmo
```

4. 

```pseudocode
ALGORITMO
```

5. 

```pseudocode

```



# Clase 3

1. 

```pseudocode

```

2. 

```pseudocode

```

3. 

```pseudocode

```

4. 

```pseudocode

```

5. 

```pseudocode

```

