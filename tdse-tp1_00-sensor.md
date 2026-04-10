Accion real|Accion en el modelo|Proximo estado|
camara detecta auto | pulsador down | bool=1
boton apretado | pulsador down | bool=1
auto presente | pulsador down| bool=1

- Eventos:
  
EV_BTN_UP: boton no accionado

EV_BTN_DOWN: boton accionado

- Estados:
  
ST_BTN_UP: estado final

ST_BTN_RAISING: estado intermedio (down>up)

ST_BTN_FALLING: estado intermedio (up>down)

ST_BTN_DOWN: estado final

- Signals:

EV_SYS_BTNDOWN=1 if pulsador apretado

EV_SYS_BTNUP=1 if pulsador no apretado

- Acciones
  
Inicialización del temporizador:

tick = DEL_BTN_MAX

Decremento:

tick--

Generación de eventos al sistema:

raise EV_SYS_BTN_DOWN

raise EV_SYS_BTN_UP


