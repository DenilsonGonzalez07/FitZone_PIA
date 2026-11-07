# Business Requirements Document (BRD) - FitZone

## 1. Preguntas para el stakeholder

1. ¿Qué evento exacto marca el inicio de la vigencia de una membresía y a qué hora precisa vence el último día? 
2. ¿Existe un periodo de gracia para el acceso si la membresía del socio acaba de vencer? 
3. ¿Cómo se determina exactamente qué clases especiales están incluidas o excluidas en el plan contratado por cada socio? 
4. ¿Con cuánto tiempo de anticipación máxima y mínima puede un socio reservar un lugar en una clase? 
5. ¿Cuál es el límite de tiempo permitido para que un socio cancele su reserva sin recibir una penalización? 
6. ¿Qué penalización o restricción se aplica cuando un socio reserva y no asiste (no-show)? 
7. Cuando se libera un lugar y pasa a la lista de espera, ¿cuánto tiempo tiene el primer socio notificado para confirmar antes de ceder el turno al siguiente? 
8. ¿En qué condiciones específicas un administrador o recepción puede autorizar el ingreso manual ignorando una restricción del sistema? 
9. ¿Qué información exacta requiere ver el instructor sobre los alumnos en su lista de asistencia? 
10. ¿Cuál es el protocolo y tiempo límite para que un instructor cancele una clase? 
11. Si el instructor cancela, ¿cómo se compensa a los socios (reprogramación, devolución, etc.)? 
12. ¿Cómo se procesa y registra el pago cuando un socio desea entrar a una clase que no está incluida en su plan? 
13. ¿Qué reportes o indicadores (KPIs) específicos revisa el administrador diaria y mensualmente para medir la demanda? 
14. ¿Cuáles son los motivos de negocio por los que una membresía cambia a estado "suspendida" y quién lo autoriza? 
15. ¿Qué información queda fuera del alcance de este sistema (ej. nómina de instructores, mantenimiento de equipo)? 

---

## 2. Contexto del Negocio 

FitZone opera vendiendo membresías con periodos mensuales, trimestrales y anuales, así como servicios adicionales de entrenamiento personal y entrenamientos especiales. Los servicios y accesos permitidos dependen estrictamente del plan que el socio haya contratado. Actualmente, los procesos clave como el control de acceso, la gestión de reservaciones y el manejo de listas de espera operan con controles manuales y reglas inconsistentes. 

---

## 3. Definición del Problema / Oportunidad 

### Problemas 
* **Lugares vacíos:** Alta incidencia de inasistencias (no-shows) de socios que reservan y no se presentan, quitando el lugar a otros. 
* **Ineficiencia operativa:** El control de las listas de espera se hace de forma manual, lo que retrasa la reasignación de espacios. 
* **Inconsistencia en accesos:** Se otorgan accesos erróneos debido a la falta de validación automatizada del tipo de membresía. 
* **Falta de métricas:** Existe una gran dificultad para medir con precisión la demanda real de las clases y horarios. 

### Oportunidades 
Implementar un sistema centralizado que automatice las reglas de membresía, el control de accesos y el flujo de reservaciones. Esto permitirá asignar lugares de listas de espera en tiempo real, reducir la capacidad ociosa penalizando o controlando los no-shows, y generar reportes precisos sobre la ocupación para optimizar los horarios de los instructores. 

---

## 4. Stakeholders 

| Rol / Stakeholder | Descripción y Responsabilidad en el Proceso |
| :--- | :--- |
| **Socio** | Inicia el proceso contratando planes; reserva, asiste o cancela el entrenamiento y se identifica en recepción para ingresar. |
| **Recepción** | Valida la identidad del socio, revisa vigencias y cobra cuotas adicionales si el entrenamiento no está en el plan. |
| **Instructor** | Gestiona la impartición del entrenamiento, revisa sus horarios, la capacidad asignada y notifica cancelaciones de sus sesiones. |
| **Administrador** | Mide la demanda, supervisa la asignación de lugares, evalúa el impacto de los no-shows y define políticas de acceso. |

---

## 5. Alcance 

### Dentro del Alcance (In Scope) 
* **Gestión de membresías:** Fechas de inicio, vencimiento y estatus (activa, vencida, suspendida). 
* **Control de accesos:** Validación en recepción mediante identificación del socio. 
* **Reservación de entrenamiento:** Descuento de cupo, cancelación y automatización de la lista de espera. 
* **Gestión de excepciones:** Registro de no-shows, clases no incluidas y cancelaciones por parte del instructor. 

### Fuera de Alcance (Out of Scope)  
* Procesamiento de nómina o pago de comisiones a los instructores. 
* Mantenimiento preventivo o correctivo del equipo de gimnasio. 
* Campañas de marketing o atracción de nuevos prospectos. 

---

## 6. Necesidades del Negocio y Funcionales 

1. **Gestión de membresías:** El sistema debe registrar la fecha de inicio y calcular automáticamente el vencimiento según el plan (mensual, trimestral, anual). 
2. **Políticas de acceso:** El sistema debe identificar estatus vencidos o suspendidos, negando el acceso físico o la reserva de clases. 
3. **Control de aforo:** Los entrenamientos deben tener un límite de capacidad máxima; al llenarse, el sistema debe habilitar una lista de espera. 
4. **Liberación de espacios:** Las cancelaciones de socios deben detonar la asignación inmediata al primer usuario en la lista de espera. 
5. **Manejo de excepciones:** Si un entrenamiento no está incluido en el plan del socio, el sistema debe alertar para realizar el cobro. Si el instructor cancela, el sistema debe notificar a los inscritos. 

---

## 7. Restricciones y Supuestos  

* **Restricciones:** Recepción no debe poder saltarse las validaciones de acceso de forma manual sin autorización. El cupo del entrenamiento no puede excederse por motivos de seguridad y espacio físico. 
* **Supuestos:** Los socios cuentan con un medio de identificación (tarjeta, app, huella) vinculable a su perfil en el sistema. Los instructores tienen acceso a una interfaz para gestionar sus horarios. 

---

## 8. Criterios de Éxito e Indicadores (KPIs) 

| Indicador de Éxito | Estado Actual | Meta Comprometida |
| :--- | :--- | :--- |
| **Tiempo de asignación de lista de espera** | Manual (Lento y propenso a errores) | Automático (Inmediato al cancelar un socio) |
| **Inconsistencias en acceso por membresía** | Frecuentes por revisión manual | 0% (Bloqueo automático del sistema) |
| **Porcentaje de lugares vacíos por No-Shows** | Alto, sin medición exacta | Reducción medible a menos del 5% |
| **Reporte de demanda de clases** | Difícil de generar, laborioso | Disponible en línea en tiempo real |