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
				Segun opcionMenu Hacer
				1:
					Escribir "Seleccione su tipo de cuota"
					Escribir "1.Mensual (35€)"
					Escribir "2.Trimestral (90€)"
					Escribir "3.Anual (300€)"
					leer opcionCuota
					Escribir "Introduzca edad"
					leer edadUsuario
					Mientras edadUsuario<=0 hacer
						escribir "La edad no puede ser 0 o menor"
						leer edadUsuario
					FinMientras
					
					Segun opcionCuota
						1:
							escribir "Se le ha sumado 15€ por cuota de inscripción fija por matrícula" 
							cuota<-50
							si edadUsuario>65 o edadUsuario<21 Entonces
								cuota<-cuota-(cuota*0.15)
							FinSi
							sociosActivos<-sociosActivos+1
							recaudacionCuotas<-recaudacionCuotas+cuota
							
						2:
							cuota<-90
							si edadUsuario>65 o edadUsuario<21 Entonces
								cuota<-cuota-(cuota*0.15)
							FinSi
							sociosActivos<-sociosActivos+1
							recaudacionCuotas<-recaudacionCuotas+cuota
							
						3:
							cuota<-300
							si edadUsuario>65 o edadUsuario<21 Entonces
								cuota<-cuota-(cuota*0.15)
							FinSi
							sociosActivos<-sociosActivos+1
							recaudacionCuotas<-recaudacionCuotas+cuota
					FinSegun
				
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
