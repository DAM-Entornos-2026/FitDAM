Algoritmo FitDAM_Master
	
	// =========================================================================
	// DECLARACIÓN E INICIALIZACIÓN DE VARIABLES GLOBALES
	// =========================================================================
	Definir sociosActivos, capacidadGimnasio, taquillasOcupadas, opcionMenu Como Entero
	Definir recaudacionCuotas, recaudacionClases, recaudacionSuplementos Como Real
	Definir alertaAforoGimnasio Como Logico
	
	// Valores iniciales según plantilla maestra
	sociosActivos <- 0
	sociosRegistrados <- 0
	capacidadGimnasio <- 50
	aforoMaximo <- 30
	taquillasOcupadas <- 0
	recaudacionCuotas <- 0.0
	recaudacionClases <- 0.0
	recaudacionSuplementos <- 0.0
	alertaAforoGimnasio <- Falso
	plazasClase <- 10
	listaEspera <- 0
	
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
				Escribir "Seleccione su tipo de cuota"
				Escribir "1.Mensual (35 euros)"
				Escribir "2.Trimestral (90 euros)"
				Escribir "3.Anual (300 euros)"
				leer opcionCuota
				mientras opcionCuota>3 o opcionCuota<1 Hacer
					escribir "Cuota invalida, intentelo de nuevo"
					leer opcionCuota
				FinMientras
				Escribir "Introduzca edad"
				leer edadUsuario
				Mientras edadUsuario<1 hacer
					escribir "La edad no puede ser 0 o menor"
					leer edadUsuario
				FinMientras
				
				Segun opcionCuota
					1:
						escribir "Se le ha sumado 15 euros por cuota de inscripción fija por matrícula" 
						cuota<-50
						si edadUsuario>65 o edadUsuario<21 Entonces
							cuota<-cuota-(cuota*0.15)
						FinSi
						si esEstudiante=1 Entonces
								cuota<-cuota-(cuota*0.15)
								Escribir "Descuento por estudiante del 15% aplicado"
						FinSi
						sociosActivos<-sociosActivos+1
						recaudacionCuotas<-recaudacionCuotas+cuota
						escribir "Cuota elegida correctamente, se le ha cobrado ",cuota," euros"
						
					2:
						cuota<-90
						si edadUsuario>65 o edadUsuario<21 Entonces
							cuota<-cuota-(cuota*0.15)
						FinSi
						si esEstudiante=1 Entonces
								cuota<-cuota-(cuota*0.15)
								Escribir "Descuento por estudiante del 15% aplicado"
						FinSi
						sociosActivos<-sociosActivos+1
						recaudacionCuotas<-recaudacionCuotas+cuota
						escribir "Cuota elegida correctamente, se le ha cobrado ",cuota," euros"
						
					3:
						cuota<-90
						si edadUsuario>65 o edadUsuario<21 Entonces
							cuota<-cuota-(cuota*0.15)
						FinSi
						si esEstudiante=1 Entonces
								cuota<-cuota-(cuota*0.15)
								Escribir "Descuento por estudiante del 15% aplicado"
						FinSi
						sociosActivos<-sociosActivos+1
						recaudacionCuotas<-recaudacionCuotas+cuota
						escribir "Cuota elegida correctamente, se le ha cobrado ",cuota," euros"
						
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
