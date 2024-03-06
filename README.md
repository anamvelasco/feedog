# FEEDOG

Feedog es un comedero automático y es el proyecto final de la materia de electrónica digital III de la Universidad de Antioquia

Este proyecto consta de un sistema automático de alimentación para perros controlado por temporizador y/o sensor de movimiento. El propósito de este proyecto es el control automático y monitoreo remoto de un sistema capaz de dosificar alimento a un perro ya sea por periodos de tiempo programados, por detección de la presencia de la mascota o de manera remota por el usuario. Así mismo, se busca proporcionar métricas al dueño de manera remota que indiquen cuando se ha suministrado alimento, cuanto de este queda en el tanque y en qué horarios ha comido el perro para llevar un registro de sus hábitos alimenticios . El sistema soltará el alimento sobre el plato mediante la apertura de una compuerta accionada mediante un motor. El sistema permitirá ser iniciado y configurado inicialmente mediante una simple interfaz compuesta por botones y una pantalla LCD. El sistema también permitirá, en paralelo, un suministro igualmente controlado de agua sobre el que también se proporcionará información al dueño.



SENSORES A UTILIZAR:

-  Sensor de movimiento PIR 
- Reloj de tiempo real RTC DS1302
- Sensor de obstáculos infrarrojo IR
- Sensor de peso HX711 y celda de carga
- Sensor de nivel de agua OKY3446

ACTUADORES A UTILIZAR:

- Servomotor estándar de alto torque MG996R
- Bomba de agua

ELEMENTOS DE INTERFAZ HUMANO-MAQUINA:
- LCD display con módulo I2C
- Pulsadores

Nota: La Raspberry Pi Pico W será utilizada para este proyecto, en tanto cuenta con un módulo de comunicación Wi - Fi integrado.



REQUISITOS FUNCIONALES:

- El sistema debe ser capaz de dispensar alimento y el agua a horas programadas definidas por el usuario.
- Se debe detectar la presencia de la mascota mediante un sensor de movimiento PIR y dispensar alimento en respuesta a esta detección y a un tiempo previamente estipulado, esto con la intención de reducir errores por el sensor de movimiento.
- El usuario debe poder iniciar la alimentación manualmente a través de una interfaz remota.
- El sistema debe proporcionar actualizaciones en tiempo real sobre el estado de alimentación, la cantidad de alimento y agua restante en el tanque a través de una conexión Wi-Fi.
- Se debe incluir una pantalla LCD para navegar entre las opciones de configuración.
- El sistema debe controlar un servomotor para abrir y cerrar una compuerta, permitiendo así la dispensación del alimento.
- La cantidad de alimento dispensada debe ser ajustable basada en la configuración establecida por el usuario.
- Se debe integrar un sensor de movimiento PIR para detectar la presencia del perro.
- Se debe emplear un sensor de peso (HX711 y celda de carga) para monitorear la cantidad de alimento restante en el tanque y confirmar la cantidad de alimento dispensado.
- Se debe emplear un sensor de nivel para controlar el agua en el tanque.
- Se debe utilizar un servomotor para la operación de la compuerta de alimentación.
- El sistema debe operar de manera segura para el usuario y la mascota, sin causar lesiones.
- Se debe asegurar una conexión segura entre el usuario y el dispensador


REQUISITOS NO FUNCIONALES:

* Disponibilidad: El sistema deberá ser capaz de operar las 24 horas en tanto está concebido con el fin de mantener alimentada a la mascota en el peor de los escenarios, donde el dueño no pueda estar durante todo el día con esta por motivos inesperados (NO busca ser un reemplazo de la responsabilidad humana, sin embargo debe servir como un salvavidas ante el imprevisto de no poder asistir a la mascota)
* Fiabilidad: Se espera que el sistema pueda permanecer sin mantenimiento en un periodo entre 2 semanas y 4 semanas. Sería indispensable entonces, hacer mantenimiento llegado a estos periodos de tiempo para evitar atascamiento en el sistema o limpieza para evitar deterioro de la calidad del alimento. 
* Usabilidad: El sistema deberá proporcionar una configuración mediante una interfaz humano-máquina sencilla. La interfaz embebida físicamente en la estructura del sistema no deberá tener muchos pulsadores. La cantidad de pulsadores sería tal que permita una navegación similar a la que permiten algunos monitores de computadora antiguos, de a lo sumo 5 o 6 pulsadores. Así mismo, no requerirá ninguna capacitación especial al usuario, salvo un pequeño instructivo sobre las funciones de cada pulsador.
* Seguridad: El sistema no requerirá una protección especial de datos en tanto estos no son particularmente sensibles, sin embargo si deberá tener una construcción robusta e impermeable que impida que la electrónica se vea afectada por el alimento y el agua
* Escalabilidad: El tanque donde se almacena el alimenta no será restringido a un único tamaño, pero si deberá limitarse a los pesos máximo y mínimo del sensor de peso utilizado.
* Tolerancia a fallos: El sistema debe avisar al usuario cuando exista desabastecimiento en el sistema, ya sea de agua o de alimento.
*  Mantenibilidad: Su mantenimiento sea lo más sencillo posible. Por ejemplo, desmontar fácilmente las partes que entran en contacto con el alimento para su limpieza, así como un acceso simplificado a los componentes electrónicos para su revisión o reemplazo, sin necesidad de herramientas especiales.
* Consumo de energía: Durante los periodos de inactividad, deberá entrar en un estado de suspensión, asegurando así una operación eficiente y sostenible, reduciendo el alto consumo de energía innecesaria en estado de reposo.
* Interoperabilidad: Debe ser capaz de conectarse y comunicarse con la aplicación  mediante Wi-Fi, para permitir el control remoto y la monitorización del estado del dispositivo.
* Cumplimiento normativo: Cumplimiento con la ley de protección al consumidor. El sistema debe diseñarse, fabricarse y comercializarse de acuerdo con las leyes de protección al consumidor vigentes en los territorios en los que se ofrece, en este caso Colombia.


ESCENARIO DE PRUEBAS:

* Espacio de ejecución: un entorno doméstico, que incluya variaciones de luz, temperatura y suelo.
* Un prototipo completo del alimentador automático.
* Perros para evaluar cómo diferentes perros interactúan con el alimentador.
* Usuarios humanos para probar la facilidad de uso de la interfaz.
* Prueba de dispensación, por ejemplo, configurar varias alimentaciones programadas para diferentes momentos del día y verificar si el dispositivo dispensa correctamente.
* Prueba de sensor de movimiento, por ejemplo, observar si el alimentador dispensa alimento cuando un perro se acerca, identificando tanto la sensibilidad como la eficacia del sensor.
* Verificar la precisión del sensor de peso, tanto en la detección de la cantidad de alimento restante como en la cantidad dispensada.
* Solicitar a usuarios que configuren horarios de alimentación, ajusten cantidades de alimento y utilicen funciones de alimentación manual, observando dificultades y facilidad de uso.

LISTADO DE COMPONENTES Y COTIZACIÓN DE PROYECTO:

1. Sensor de movimiento HC-SR501  --> $10,000 (COP)
2. Módulo de reloj de tiempo real DS1302 --> $ 5,593 (COP)
3. Sensor de Obstáculos Infrarrojo IR --> $ 3,500 (COP)
4. Kit De Báscula Con Celda De Carga 1Kg HX711 --> 26.000 (COP)
5. LCD (con I2C) --> $ 26000 (COP)
6. Sensor Nivel de Agua --> $ 5000 (COP)
7. Bomba de agua --> $16000 (COP)
8. Tarjeta Raspberry Pi Pico W --> $ 43723 (COP)
9. Fuente 5V 2A --> $ 17000 (COP) (pendiente de revisión, puede requerirse una de mayores prestaciones - precio tentativo máximo: 40000 COP)
10. Protoboard transparente, 830 puntos de inserción -> $13600 (COP)
11. Cable UTP CAT 6 por metro --> $ 725,90 (COP)
12. Multímetro digital --> $ 24000 (COP)
13. Pinzas punta curva tipo Americano 11.5 cms --> $ 13000 (COP)
14. Cable duplex con clavija 1.5mt--> $ 4500 (COP)
15. Chunky Perro Cachorro Pollo 4kg $40000
16. MDF 5.5mm 1.83x2.44 Metros --> $ 6000 (COP)
17. Plato agua --> $ 15000 (COP)
18. Plato alimento --> $ 15000 (COP)
19. Flux 8g  --> $ 3000 (COP)
20. Cautín ---> $ 32000 (COP)
21. Super pega ---> $ 1200 (COP)
22. Tornillos ---> $300 (COP)
23. Tuercas ---> $200 (COP)
24. Destornillador ---> $8000 (COP)
Total: 329.342 (COP)
Software: Inventor (u Onshape), RdWorks, Cura.

*Nota 1: Los valores cotizados están sujetos a cambios en la moneda. Así mismo, están sujetos a cambios en las decisiones de diseño con lo que, una cotización más realista del proyecto podría resultar a partir de un primer prototipo.
*Nota 2: Los software descritos son gratuitos. En el caso de Inventor, el acceso es proporcionado por la Universidad. Como alternativa al anterior, se tiene Onshape.
*Nota 3: Herramientas: Impresora 3D Artillery Sidewinder X2 ($200 el gramo) y cortadora láser (gratis/proporcionados por la Universidad exceptuando el material)


