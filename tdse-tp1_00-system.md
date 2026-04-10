## System Statechart - Eventos y Estados

---

### Eventos de entrada (desde sensores)

- EV_SYS_CAM_ON
- EV_SYS_TICKET
- EV_SYS_COIL_OFF

---

### Eventos de salida (hacia actuadores)

- EV_ACT_DISPLAY_ON
- EV_ACT_TICKET_PRINT
- EV_ACT_BARRIER_UP
- EV_ACT_BARRIER_DOWN
- EV_ACT_SERVER_SEND

---

### Estados

- ST_SYS_IDLE: sistema en espera (sin vehículo)
- ST_SYS_WELCOME: vehículo detectado (mensaje en display)
- ST_SYS_PROCESS: usuario interactúa (impresión de ticket)
- ST_SYS_BARRIER: control de barrera

  ## Tabla de Estados - System

| Current State   | Event            | Guard | Next State      | Actions                          |
|----------------|------------------|-------|-----------------|----------------------------------|
| ST_SYS_IDLE    | EV_SYS_CAM_ON    | -     | ST_SYS_WELCOME  | raise EV_ACT_DISPLAY_ON          |
| ST_SYS_WELCOME | EV_SYS_BTN_DOWN  | -     | ST_SYS_PROCESS  | raise EV_ACT_TICKET_PRINT        |
| ST_SYS_PROCESS | EV_SYS_BTN_UP    | -     | ST_SYS_BARRIER  | raise EV_ACT_BARRIER_UP          |
| ST_SYS_BARRIER | EV_SYS_COIL_OFF  | -     | ST_SYS_IDLE     | raise EV_ACT_BARRIER_DOWN; raise EV_ACT_SERVER_SEND |




