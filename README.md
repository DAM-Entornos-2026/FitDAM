# FitDAM
Software en PSeInt para la gestión integral de FitDAM. Incluye alta de socios con tarifas por edad, control de acceso por torno y aforo, reserva de clases con lista de espera, venta en tienda con IVA/cambio y balance de rentabilidad. Desarrollado con Scrumban en GitHub Projects. (279 caracteres)
```
Algoritmo FitDAM_Master
	
	// =========================================================================
	// DECLARACIÓN E INICIALIZACIÓN DE VARIABLES GLOBALES
	// =========================================================================
	Definir sociosActivos, capacidadGimnasio, taquillasOcupadas, opcionMenu Como Entero
	Definir recaudacionCuotas, recaudacionClases, recaudacionSuplementos Como Real
	Definir alertaAforoGimnasio Como Logico
	
	// Valores iniciales según plantilla maestra
	sociosActivos <- 0
	capacidadGimnasio <- 50
	taquillasOcupadas <- 0
	recaudacionCuotas <- 0.0
	recaudacionClases <- 0.0
	recaudacionSuplementos <- 0.0
	alertaAforoGimnasio <- Falso
	
	// =========================================================================
	// BUCLE PRINCIPAL DE NAVEGACIÓN Y MENÚ
	// =========================================================================
	Repetir
		Escribir ""
		Escribir "=================================================="
		Escribir "     SISTEMA DE GESTIÓN CENTRALIZADA FITDAM      "
		Escribir "=================================================="
		Escribir "1. Alta de Socios, Tipo de Cuota y Descuentos"
		Escribir "2. Reserva de Clases Dirigidas y Aforo"
		Escribir "3. Alquiler de Taquillas y Venta de Suplementos"
		Escribir "4. Facturación, Matrícula, IVA y Desglose de Cambio"
		Escribir "5. Cierre de Turno, Tasa de Ocupación e Informe"
		Escribir "0. Salir del programa"
		Escribir "--------------------------------------------------"
		Escribir "Seleccione una opción (0-5):"
		Leer opcionMenu
		Escribir ""
		
		Segun opcionMenu Hacer
			1:
				// TODO: [Issue #2] Implementado por Developer 1
				Escribir "[PENDIENTE] Caso 1 no integrado. Esperando revisión en Code Review."
				
			2:
				// TODO: [Issue #3] Implementado por Developer 2
				Escribir "[PENDIENTE] Caso 2 no integrado. Esperando revisión en Code Review."
				
			3:
				// TODO: [Issue #4] Implementado por Developer 3
				Escribir "[PENDIENTE] Caso 3 no integrado. Esperando revisión en Code Review."
				
			4:
				// TODO: [Issue #5] Implementado por Developer 4
				Escribir "[PENDIENTE] Caso 4 no integrado. Esperando revisión en Code Review."
				
			5:
				// TODO: [Issue #6] Implementado por Developer 5
				Escribir "[PENDIENTE] Caso 5 no integrado. Esperando revisión en Code Review."
				
			0:
				Escribir "Cerrando el sistema FitDAM... ¡Hasta pronto!"
				
			De Otro Modo:
				Escribir "[ERROR] Opción no válida. Introduzca un número entre 0 y 5."
		FinSegun
		
	Hasta Que opcionMenu = 0

FinAlgoritmo
```
