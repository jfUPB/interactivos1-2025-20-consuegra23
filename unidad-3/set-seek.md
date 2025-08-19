# Unidad 3

## 🔎 Fase: Set + Seek


### Actividad 5
<img width="1901" height="1090" alt="Diagrama sin título drawio" src="https://github.com/user-attachments/assets/49ef5005-a8c3-4113-94a6-9e8e5f64ca4a" />


Vector de prueba 1
Estado inicial: STATE_CONFIG, count = 20
Entrada: A
Salida esperada: count = 21, display = 21
Estado final: STATE_CONFIG

Vector de prueba 2
Estado inicial: STATE_CONFIG, count = 20
Entrada: B
Salida esperada: count = 19, display = 19
Estado final: STATE_CONFIG

Vector de prueba 3
Estado inicial: STATE_CONFIG, count = 25
Entrada: S
Salida esperada: startTime actualizado, state = ARMED
Estado final: STATE_ARMED

Vector de prueba 4
Estado inicial: STATE_ARMED, count = 10
Entrada: pasa 1 segundo
Salida esperada: count = 9, display = 9
Estado final: STATE_ARMED

Vector de prueba 5
Estado inicial: STATE_ARMED, count = 1
Entrada: pasa 1 segundo
Salida esperada: count = 0, display = SKULL, state = EXPLODED
Nueva entrada: T
Salida esperada: count = 20, display = 20, state = CONFIG
Estado final: STATE_CONFIG
