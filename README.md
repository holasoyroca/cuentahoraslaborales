# 🕒 Control de Horas y Fichajes

Herramienta web sencilla y **autocontenida** (un solo archivo) diseñada para calcular horas trabajadas en entornos de hostelería o turnos rotativos. Soluciona automáticamente los problemas comunes de fichajes duplicados, turnos de madrugada y olvidos de entrada/salida.

> **Versión actual:** v12.0
> **Tecnología:** HTML5 + JavaScript (Funciona offline en el navegador).

## 🚀 Características Principales

Esta herramienta no es una simple calculadora. Incluye lógica específica para corregir errores humanos habituales:

* **👤 Detección de Empleado:** Lee automáticamente el nombre de la persona en la segunda columna del archivo pegado.
* **🧹 Filtro "Anti-Pánico" (Limpieza de Duplicados):** Si un empleado ficha dos veces seguidas por error (en un intervalo menor a 30 minutos), el sistema elimina el segundo fichaje automáticamente.
* **🌙 Soporte para Turnos de Noche:** Calcula correctamente las horas aunque el turno empiece un día y termine al siguiente (ej: 20:00 a 02:00).
* **🧠 Detección de Olvidos:** Si un turno dura demasiadas horas (>16h) o se junta con la mañana siguiente, el sistema detecta que falta un fichaje, corta el turno y te avisa.
* **✍️ Edición Manual Interactiva:** Las horas que faltan aparecen en **rojo**. Puedes escribir la hora correcta directamente en la casilla y el total se recalcula en tiempo real.

## 📖 Instrucciones de Uso

1.  **Descarga** el archivo `ControlHorario.html`.
2.  Ábrelo con cualquier navegador web (Chrome, Edge, Firefox). No necesitas internet.
3.  Ve a tu Excel o programa de fichajes.
4.  **Selecciona todo** (Ctrl + A) y **copia** (Ctrl + C).
5.  Pega los datos en el cuadro blanco de la herramienta.
6.  Pulsa el botón azul **"Procesar Datos"**.

## 🛠️ Solución de Errores (Cajas Rojas)

Si el programa detecta un error (por ejemplo, alguien olvidó fichar la salida), verás una fila en rojo con el mensaje **ERROR**.

1.  Haz clic en la casilla de la hora que falta (o la que está mal).
2.  Escribe la hora correcta (ej: `01:30`) o selecciónala con el reloj.
3.  Haz clic fuera.
4.  La fila se pondrá en verde (**MANUAL**) y el total de horas se actualizará solo.

## ⚙️ Lógica Interna (Algoritmo)

El script sigue estas reglas de prioridad para evitar "efectos dominó" en los cálculos:

1.  **Limpieza:** Se eliminan `rawTimestamps` duplicados (<30min).
2.  **Madrugada (00:00 - 06:00):** Se asume siempre como hora de **SALIDA** obligatoria.
3.  **Reset de Mañana:** Si hay una entrada abierta y el siguiente fichaje es al día siguiente pasadas las 06:00 AM, se considera una **NUEVA ENTRADA** (asumiendo que se olvidó fichar la salida anterior).

## 📄 Licencia

Este proyecto es de código abierto. Puedes usarlo y modificarlo libremente.
Repositorio: [https://github.com/holasoyroca/cuentahoraslaborales](https://github.com/holasoyroca/cuentahoraslaborales)
