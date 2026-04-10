Implementación de Parking Ticket Dispenser (Entry Machine)

El sistema se divide en tres etapas:

- Escrutar (Sensor)
Se utilizan tres sensores, modelizados mediante pulsadores:
Cámara → detecta presencia del vehículo
Botón → interacción del usuario
Bobina → detecta salida del vehículo

- Procesar (System)
Es la unidad lógica que procesa los eventos generados por los sensores.
Ejemplo:
Cuando la cámara detecta un vehículo → se genera un mensaje de bienvenida en el display
Cuando se presiona el botón → se inicia la emisión del ticket y la apertura de la barrera

-Actuar (Actuator)
Se utilizan cuatro actuadores modelizados con LEDs:
Display
Impresora
Barrera
Servidor

-Proceso completo
El vehículo llega → la cámara lo detecta
Se muestra mensaje de bienvenida en el display
El conductor presiona el botón
Se imprime el ticket y se abre la barrera
El vehículo avanza y deja la bobina
Se cierra la barrera
Se envían los datos al servidor
