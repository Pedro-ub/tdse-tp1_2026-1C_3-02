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

EV_SYS_CAM_ON

EV_SYS_CAM_OFF

EV_SYS_TICKET_REQUESTED

EV_SYS_TICKET_NOT_REQUESTED

EV_SYS_COIL_DETECT

EV_SYS_COIL_NOT_DETECT


- Acciones
  
Inicialización del temporizador:

tick = DEL_BTN_MAX

Decremento:

tick--

Generación de eventos al sistema:

raise EV_SYS_BTN_DOWN

raise EV_SYS_BTN_UP

## Tabla de Estados - Sensor (Botón)

| Current State     | Event         | Guard     | Next State      | Actions              |
|------------------|--------------|----------|-----------------|----------------------|
| ST_BTN_UP        | EV_BTN_UP    | -        | ST_BTN_UP       | -                    |
| ST_BTN_UP        | EV_BTN_DOWN  | -        | ST_BTN_FALLING  | tick = DEL_BTN_MAX   |
| ST_BTN_DOWN      | EV_BTN_UP    | -        | ST_BTN_RISING   | tick = DEL_BTN_MAX   |
| ST_BTN_DOWN      | EV_BTN_DOWN  | -        | ST_BTN_DOWN     | -                    |
| ST_BTN_RISING    | EV_BTN_UP    | tick==0  | ST_BTN_UP       | raise EV_SYS_BTN_UP  |
| ST_BTN_RISING    | EV_BTN_UP    | tick>0   | ST_BTN_RISING   | tick--               |
| ST_BTN_RISING    | EV_BTN_DOWN  | tick==0  | ST_BTN_DOWN     | -                    |
| ST_BTN_RISING    | EV_BTN_DOWN  | tick>0   | ST_BTN_RISING   | tick--               |
| ST_BTN_FALLING   | EV_BTN_UP    | tick==0  | ST_BTN_UP       | -                    |
| ST_BTN_FALLING   | EV_BTN_UP    | tick>0   | ST_BTN_FALLING  | tick--               |
| ST_BTN_FALLING   | EV_BTN_DOWN  | tick==0  | ST_BTN_DOWN     | raise EV_SYS_BTNDOWN |
| ST_BTN_FALLING   | EV_BTN_DOWN  | tick>0   | ST_BTN_FALLING  | tick--               |

