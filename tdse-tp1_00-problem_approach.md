Implementacion de Parking Ticket Dispenser (Machine)
Es un sistema que consta de tres etapas: escrutar, procesar y actuar.
Escrutar: Consta de tres sensores: la camara, el boton y la bobina, que seran modelizados por tres pulsadores.
Procesamiento: es la placa que se encarga de procesar los estados de la etapa anterior. Por ejemplo cuando un auto llega lo detecta la camara (se cierra el pulsador) y esa accion activa un mensaje de bienvenida en el display.
Actuador: Consta de cuatro actuadores: el display, impresora, barrera y el servidor, que seran modelizados por cuatro leds.

Proceso: Cuando el auto llega a la entrada, la maquina lo procesa mediante la camara y envia un mensaje de bienvenida por el display. Luego el conductor apreta el boton, el cual causa la impresion del ticket y la apertura de la barrera. Por ultimo el auto sale, y es detectado por la bobina que ya no se encuentra ahi para poder cerrar la barrera. Simultaneamente de cerrar la barrera la informacion de ingreso y los datos del auto son enviados al servidor.
