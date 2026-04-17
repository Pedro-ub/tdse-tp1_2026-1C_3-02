## System Statechart - Eventos y Estados

---

### Eventos de entrada (desde sensores)

- EV_ACT_DISPLAY_ON
- EV_ACT_DISPLAY_OFF
- EV_ACT_TICKET_PRINT
- EV_ACT_BARRIER_UP
- EV_ACT_BARRIER_DOWN
- EV_ACT_SERVER_SEND
---

### Eventos de salida (hacia actuadores)

- EV_ACT_SERVER_SEND

---

### Estados

- ST_SYS_IDLE: sistema en espera
- ST_ACT_DISPLAY_ON
- ST_ACT_DISPLAY_OFF
- ST_ACT_TICKET_PRINT
- ST_ACT_BARRIER_OPEN
- ST_ACT_BARRIER_DOWN
  ## Tabla de Estados - System


| Current State       | Event                        | Guard           | Next State            | Actions                      |
|----------------     |----------------------------- |-----------------|-----------------      |------------------------------|  
| ST_ACT_IDLE         | EV_ACT_DISPLAY_ON            | -               | ST_ACT_DISPLAY_ON     |                              |
| ST_ACT_DISPLAY_ON   | EV_ACT_TICKET_PRINT          | -               | ST_ACT_TICKET_PRINT   |                              |
| ST_ACT_TICKET_PRINT | EV_ACT_BARRIER_UP            | -               | ST_ACT_BARRIER_OPEN   |                              |
| ST_ACT_OPEN_BARRIER | EV_ACT_BARRIER_DOWN          | -               | ST_ACT_BARRIER_DOWN   |                              |
| ST_ACT_BARRIER_DOWN | EV_ACT_DISPLAY_OFF           | -               | ST_ACT_IDLE           |  raise EV_ACT_SERVER_SEND    |






