# 🕒 Calculadora de Horas de Trabajo

Esta es una herramienta sencilla diseñada para calcular las horas totales trabajadas a partir de un listado de fichajes (Excel, CSV o texto), sin necesidad de instalar programas complejos.

## 🚀 ¿Cómo se usa?

1.  **Abre el archivo** `CalculadoraHoras.html` en tu navegador (Chrome, Edge, Firefox, etc.). No hace falta internet.
2.  **Copia tus datos**: Ve a tu Excel o archivo de fichajes, selecciona todas las columnas con las fechas y horas, y cópialas (`Ctrl + C`).
3.  **Pega los datos**: Ve a la calculadora, pincha en el recuadro blanco grande y pega (`Ctrl + V`).
4.  **Calcula**: Pulsa el botón azul **"Calcular Horas"**.

## 🧠 ¿Cómo funciona la lógica interna?

A diferencia de una fórmula simple de Excel, este programa realiza varios pasos inteligentes para evitar errores comunes en hostelería:

### 1. Ordenación Cronológica (El problema de la madrugada)
Muchos sistemas fallan cuando fichas la salida a las 00:20 (madrugada), porque piensan que es el primer fichaje del día siguiente.
* **Esta herramienta:** Lee todas las fechas, las mezcla y las ordena en una línea de tiempo única.
* **Resultado:** Si entras el día 5 a las 20:00 y sales el día 6 a las 01:00, el programa entiende perfectamente que esa salida pertenece a la entrada anterior.

### 2. Escáner Inteligente
El programa busca línea por línea cualquier cosa que parezca una fecha (`dd/mm/aaaa`) y una hora (`hh:mm`).
* No importa si copias columnas extra (como el nombre o ID).
* No importa si hay espacios raros o tabulaciones.
* El programa ignora el texto basura y se queda solo con los tiempos.

### 3. Detección de Errores
El sistema te avisará automáticamente en dos casos:
* **Fichajes Impares:** Si se te olvidó fichar una entrada o una salida (tienes un número impar de registros), te avisará y descartará el último dato para no romper el cálculo.
* **Turnos Sospechosos:** Si un turno dura más de **16 horas**, lo marcará en **ROJO** en la tabla. Esto suele indicar que alguien olvidó fichar la salida de un día y el sistema lo ha unido con la entrada del día siguiente.

## 📋 Requisitos
* Un navegador web moderno (Chrome, Edge, Safari).
* Los datos deben contener fecha y hora (ejemplo: `25/12/2025 18:30`).

---
*Herramienta creada para uso interno y facilitar el control horario.*
