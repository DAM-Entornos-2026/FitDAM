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
		Escribir "3. Alquiler de Taquillas y Venta de Suplementos y  Facturación, Matrícula, IVA y Desglose de Cambio"
		Escribir "4. Control de Acceso por Tornos y Aforo en Tiempo Real"
		Escribir "5. Cierre de Turno, Tasa de Ocupación e Informe"
		Escribir "0. Salir del programa"
		Escribir "--------------------------------------------------"
		Escribir "Seleccione una opción (0-5):"
		Leer opcionMenu
		Escribir ""
		
		Segun opcionMenu Hacer
			1:
				// TODO: [Issue #2] Implementado por Jared
				Escribir "Seleccione su tipo de cuota"
				Escribir "1.Mensual (35?)"
				Escribir "2.Trimestral (90?)"
				Escribir "3.Anual (300?)"
				leer opcionCuota
				mientras opcionCuota>3 o opcionCuota<1 Hacer
					escribir "Cuota invalida, intentelo de nuevo"
					leer opcionCuota
				FinMientras
				Escribir "Introduzca edad"
				leer edadUsuario
				Mientras edadUsuario<=0 hacer
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
						sociosActivos<-sociosActivos+1
						recaudacionCuotas<-recaudacionCuotas+cuota
						escribir "Cuota elegida correctamente, se le ha cobrado ",cuota," euros"
						
					2:
						cuota<-90
						si edadUsuario>65 o edadUsuario<21 Entonces
							cuota<-cuota-(cuota*0.15)
						FinSi
						sociosActivos<-sociosActivos+1
						recaudacionCuotas<-recaudacionCuotas+cuota
						escribir "Cuota elegida correctamente, se le ha cobrado ",cuota," euros"
						
					3:
						cuota<-90
						si edadUsuario>65 o edadUsuario<21 Entonces
							cuota<-cuota-(cuota*0.15)
						FinSi
						sociosActivos<-sociosActivos+1
						recaudacionCuotas<-recaudacionCuotas+cuota
						escribir "Cuota elegida correctamente, se le ha cobrado ",cuota," euros"
						
				FinSegun
			2:
				// TODO: [Issue #3] Implementado por William
				Escribir "--- RESERVA DE CLASE DIRIGIDA ESPECIAL ---"
				// SOLUCIÓN DESARROLLADA PARA LA IMPLEMENRACUION DE RESERVA DE CLASES
				Escribir "Plazas disponibles en la clase: ", plazasClase
				Escribir "Personas en lista de espera: ", listaEspera
				Escribir "------------------------------------------"
				
				Si plazasClase > 0 Entonces
					plazasClase <- plazasClase - 1
					recaudacionClases <- recaudacionClases + 3.0
					Escribir "[EXITO] Plaza reservada correctamente."
					
				Sino
					Si listaEspera < 5 Entonces
						listaEspera <- listaEspera + 1
						Escribir "[PLAZAS AGOTADAS: Añadido a lista de espera en posicion ", listaEspera, "]"
					Sino
						Escribir "[ERROR] Peticion rechazada. La lista de espera esta completamente llena (Max 5)."
					FinSi
				FinSi
			3:
				// TODO: [Issue #6] Implementado por Andrew
				Escribir "[PENDIENTE] Caso 5 no integrado. Esperando revisión en Code Review."
				Definir subtotal, descuento, baseImponible Como Real
				Definir iva, totalPagar, pago, cambio Como Real
				
				// 1. MOSTRAR TIENDA Y SOLICITAR CANTIDADES
				Escribir "=========================================="
				Escribir "       TIENDA NUTRICIONAL FITDAM"
				Escribir "=========================================="
				Escribir "Batidos de Proteina: 4 euros/unidad"
				Escribir "Toallas:             8 euros/unidad"
				Escribir "------------------------------------------"
				
				Repetir
					Escribir "Cantidad de batidos (>= 0):"
					Leer cantidadBatidos
					
					Si cantidadBatidos < 0 Entonces
						Escribir "[ERROR] La cantidad no puede ser negativa."
					FinSi
				Hasta Que cantidadBatidos >= 0
				
				Repetir
					Escribir "Cantidad de toallas (>= 0):"
					Leer cantidadToallas
					
					Si cantidadToallas < 0 Entonces
						Escribir "[ERROR] La cantidad no puede ser negativa."
					FinSi
				Hasta Que cantidadToallas >= 0
				
				// 2. SUBTOTAL Y DESCUENTO POR VOLUMEN
				subtotal <- cantidadBatidos * 4 + cantidadToallas * 8
				descuento <- 0
				
				Si subtotal > 30 Entonces
					descuento <- subtotal * 0.10
				FinSi
				
				baseImponible <- subtotal - descuento
				
				// 3. CALCULAR IVA Y TOTAL
				iva <- baseImponible * 0.21
				totalPagar <- baseImponible + iva
				
				Escribir ""
				Escribir "========== RESUMEN DE COMPRA =========="
				Escribir "Batidos: ", cantidadBatidos
				Escribir "Toallas: ", cantidadToallas
				Escribir "Subtotal: ", subtotal, " euros"
				Escribir "Descuento: ", descuento, " euros"
				Escribir "Base imponible: ", baseImponible, " euros"
				Escribir "IVA (21%): ", iva, " euros"
				Escribir "TOTAL A PAGAR: ", totalPagar, " euros"
				
				// 4. PASARELA DE COBRO: EXIGIR EFECTIVO SUFICIENTE
				Repetir
					Escribir ""
					Escribir "Introduzca el efectivo entregado (euros):"
					Leer pago
					
					Si pago < totalPagar Entonces
						Escribir "[ERROR] Dinero insuficiente. Faltan ",totalPagar - pago, " euros."
						
					FinSi
				Hasta Que pago >= totalPagar
				
				cambio <- pago - totalPagar
				
				Escribir ""
				Escribir "========== RECIBO DE PAGO =========="
				Escribir "Total de la compra: ", totalPagar, " euros"
				Escribir "Efectivo entregado: ", pago, " euros"
				Escribir "Cambio a devolver: ", cambio, " euros"
				
				// Convertir a centimos para evitar errores de decimales
				// en el desglose de billetes y monedas.
				pagoCentimos <- Trunc(pago * 100 + 0.5)
				cambioCentimos <- Trunc(cambio * 100 + 0.5)
				
				// DESGLOSE DEL CAMBIO
				billetes20 <- Trunc(cambioCentimos / 2000)
				restoCambio <- cambioCentimos MOD 2000
				
				billetes10 <- Trunc(restoCambio / 1000)
				restoCambio <- restoCambio MOD 1000
				
				billetes5 <- Trunc(restoCambio / 500)
				restoCambio <- restoCambio MOD 500
				
				monedas2 <- Trunc(restoCambio / 200)
				restoCambio <- restoCambio MOD 200
				
				monedas1 <- Trunc(restoCambio / 100)
				restoCambio <- restoCambio MOD 100
				
				Escribir ""
				Escribir "========== DESGLOSE DEL CAMBIO =========="
				Escribir "Billetes de 20 euros: ", billetes20
				Escribir "Billetes de 10 euros: ", billetes10
				Escribir "Billetes de 5 euros:  ", billetes5
				Escribir "Monedas de 2 euros:   ", monedas2
				Escribir "Monedas de 1 euro:    ", monedas1
				
				Si restoCambio > 0 Entonces
					Escribir "Monedas de centimos restantes: ",restoCambio, " centimos"
					
				FinSi
				
				// 5. ACUMULAR RECAUDACION DE LA TIENDA
				recaudacionTienda <- recaudacionTienda + totalPagar
				
				Escribir ""
				Escribir "Recaudacion de la tienda: ",recaudacionTienda, " euros"
				
				Escribir "Venta completada correctamente."
				
				//FIN
				
			4:
				
			5:
				// TODO: [Issue #5] Implementado por Developer 4
				Escribir "[PENDIENTE] Caso 4 no integrado. Esperando revisión en Code Review."
				Escribir "Elija su opción"
				Escribir "1.Tasa de ocupación"
				escribir "2.Desglose financiero"
				leer opcionFinanciera
				mientras opcionFinanciera>2 o opcionFinanciera<1 Hacer
					escribir "Opción invalida, intentelo de nuevo"
					leer opcionFinanciera
				FinMientras
				Segun opcionFinanciera
					1:
						ocupacion<-(sociosActivos/aforoMaximo)*100
						escribir "La ocupación actual es del ",ocupacion,"%"
						
				    2:
						escribir "Recaudacion de cuotas: ",recaudacionCuotas," euros"
						escribir "Recaudacion de tienda: ",recaudacionSuplementos," euros"
						escribir "Recaudacion de clases: ",recaudacionClases," euros"
						recaudacionGlobal<-recaudacionCuotas+recaudacionSuplementos+recaudacionClases
						escribir "Recaudacion global: ",recaudacionGlobal
						si recaudacionGlobal<500 Entonces
							escribir "Advertencia, la recaudacion no alcanza el minimo necesario para cubrir los costes fijos"
						FinSi
				finsegun
			0:
				Escribir "Cerrando el sistema FitDAM... ¡Hasta pronto!"
				
			De Otro Modo:
				Escribir "[ERROR] Opción no válida. Introduzca un número entre 0 y 5."
		FinSegun
		
	Hasta Que opcionMenu = 0

FinAlgoritmo
