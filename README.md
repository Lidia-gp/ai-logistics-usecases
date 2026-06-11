# AI Use Case Map — Operaciones Logísticas
 
8 casos de uso de inteligencia artificial en operaciones logísticas (transporte terrestre, marítimo y aéreo), priorizados por madurez de implementación.
 
> Elaborado por **Lidia García** — Directora de Operaciones Logísticas · 10+ años de experiencia internacional en supply chain multimodal.
 
---
 
## Resumen
 
| # | Caso de uso | Tipo de IA | Categoría |
|---|-------------|-----------|-----------|
| 1 | Reporting operativo con GenAI | Generación (LLM) | Quick win |
| 2 | Procesamiento de documentos con OCR + LLM | NLP / Extracción | Quick win |
| 3 | Clasificación automática de incidencias | NLP / Clasificación | Quick win |
| 4 | Anomalías en facturación de transportistas | Detección de anomalías | Impacto medio |
| 5 | Asistente interno sobre procedimientos | GenAI / RAG | Impacto medio |
| 6 | Previsión de demanda y capacidad de transporte | Predicción | Estratégico |
| 7 | Estimación predictiva de ETAs | Predicción + tiempo real | Estratégico |
| 8 | Optimización de modalidad de carga | Optimización | Estratégico |
 
---
 
## Quick wins
 
### 1. Reporting operativo con GenAI
 
| | |
|---|---|
| **Problema** | El equipo dedica horas diarias a agregar incidencias (roturas de stock, quiebras de temperatura, retrasos), redactar correos a comercial y clientes, calcular costes de mercancía dañada y llamar a transportistas, navieras o agentes aéreos para actualizar ETAs. El equipo hace de intermediario de información en lugar de resolver problemas. |
| **Tipo de IA** | LLM para redacción automatizada + integración con TMS/WMS/ERP para alimentar el contexto. |
| **Datos** | Registro de incidencias, ETAs de transportistas/navieras/aerolíneas (frecuentemente obtenidas por teléfono), costes por referencia, pedidos activos por cliente. Los datos existen pero en sistemas separados y se consolidan a mano. |
| **ROI** | Reducción del 60-70% del tiempo en redacción y distribución. Información al cliente en minutos en lugar de horas. Libera 1-2h/día por persona en equipos de 4-6. |
| **Riesgos** | Requiere incidencias digitalizadas. El LLM necesita revisión humana al principio. La integración con tracking depende de cada proveedor — muchos operadores pequeños no tienen API. |
 
**Perspectiva profesional** — He gestionado equipos donde gente con años de experiencia dedicaba media mañana a redactar correos actualizando información a diferentes personas, o llamando a los transportistas para conocer el estado de las cargas o si se mantiene la ETA. Ese tiempo no vuelve y evita avanzar en mejoras operativas reales. Este caso no es el de mayor ROI en una hoja de cálculo, pero es el primero que comenzaría a trabajar: es rápido de implementar y el riesgo es bajo. Cuando los reportes llegan a tiempo y completos, se aumenta la eficiencia de todos los implicados.
 
---
 
### 2. Procesamiento de documentos con OCR + LLM
 
| | |
|---|---|
| **Problema** | Facturas de transportistas, navieras y aerolíneas, documentos de transporte (CMR, BL, AWB) y documentación aduanera se revisan manualmente comparando datos con el sistema. En facturación: abrir factura, abrir Excel de tarifas, comprobar, y si hay discrepancia contactar al proveedor y volver a revisar cuando contesta. En documentación aduanera se revisan los mismos campos una y otra vez en un volumen enorme de documentos, y un solo error puede bloquear una carga en frontera. |
| **Tipo de IA** | OCR para extracción + LLM para interpretación, cruce con el sistema y alertas por discrepancia. |
| **Datos** | Facturas digitales, tarifas contratadas con sus variables, datos de pedidos (TMS/ERP), documentos de transporte (CMR, BL, AWB), documentación aduanera (DUA, packing lists, certificados de origen). |
| **ROI** | El sistema valida automáticamente el 80-90% de documentos sin errores y solo escala las discrepancias. Asociación automática de facturas a pedidos. Reducción del riesgo de errores en aduanas. |
| **Riesgos** | La calidad del OCR depende del formato. Cada proveedor tiene un formato de factura distinto. En documentación aduanera la IA no elimina la revisión humana, la reduce a los casos dudosos. |
 
**Perspectiva profesional** — He tenido a personas cualificadas dedicando jornadas enteras a abrir un documento, abrir un Excel, comparar línea por línea y volver a empezar con el siguiente. En documentación aduanera es peor: el volumen es alto, los campos a revisar son siempre los mismos, pero un solo error puede bloquear una carga en frontera. Y esto se multiplica cuando operas en varios modos de transporte porque cada uno tiene su propia documentación — CMR, BL, AWB — pero los datos que revisas son esencialmente los mismos. Lo que necesitas no es que la IA haga el trabajo, sino que revise lo que ya está bien y te avise solo cuando algo no cuadra. Eso cambia por completo el rol de la persona: pasa de revisar todo a gestionar solo las excepciones.
 
---
 
### 3. Clasificación automática de incidencias
 
| | |
|---|---|
| **Problema** | Las incidencias llegan por todos los canales (llamada, WhatsApp, correo) sin estructura. El equipo las registra en Excel para identificar patrones y negociar con proveedores, pero el volumen hace que haya incidencias sin registrar, duplicados (la recibe uno por WhatsApp y otro por correo) y clasificaciones inconsistentes. El resultado: un histórico que no sirve como base fiable. |
| **Tipo de IA** | NLP para extracción y clasificación desde múltiples canales + deduplicación automática + categorización por tipo, responsable y causa raíz. |
| **Datos** | Mensajes de incidencias en cualquier formato. Catálogo de tipos: rotura de mercancía, palet dañado, rotura de temperatura, falta de mercancía, pérdida de palets, error de entrega cruzada, daños en contenedor, incidencias en carga aérea. Base de proveedores, transportistas, navieras y aerolíneas. |
| **ROI** | Eliminación de duplicados. Clasificación automática por tipo y responsable. Histórico fiable para negociación con proveedores y operadores de transporte. El equipo deja de transcribir y se centra en resolver. |
| **Riesgos** | Mensajes sin contexto son difíciles de procesar. Unificar canales tiene coste. La deduplicación de la misma incidencia contada por personas distintas no es trivial. |
 
**Perspectiva profesional** — He dedicado reuniones enteras a discutir con un transportista sobre roturas de mercancía y no tener datos limpios para demostrar que el patrón era suyo y no del proveedor. Cuando tu histórico de incidencias tiene huecos, duplicados y clasificaciones inconsistentes, pierdes capacidad de negociación y pierdes visibilidad sobre dónde están los problemas reales. Lo que necesitas no es un sistema más sofisticado de registro — es que el registro ocurra solo. Que la incidencia llegue por donde llegue, se clasifique, se deduplique y se asocie al transportista, naviera o proveedor correcto sin que nadie tenga que abrir un Excel.
 
---
 
## Impacto medio
 
### 4. Detección de anomalías en facturación de transportistas
 
| | |
|---|---|
| **Problema** | Las facturas de transportistas, navieras y aerolíneas contienen discrepancias constantes: kilos incorrectos, tarifas mal aplicadas, conceptos que no corresponden, recargos que no deberían aplicar. Son errores de proceso — tarifas complejas, datos manuales, actualizaciones que no se reflejan a tiempo. En marítimo la complejidad es mayor por la cantidad de recargos (BAF, CAF, THC, demoras) y en aéreo por la variabilidad de tarifas. El equipo no tiene tiempo de revisar cada factura al detalle, así que hace un cálculo aproximado. Las discrepancias pasan una a una y nadie las suma a final de año. |
| **Tipo de IA** | Comparación automática de cada línea de factura contra tarifas contratadas, datos reales del envío y patrones históricos por proveedor. |
| **Datos** | Facturas (via OCR del caso 2 o del sistema), tarifas con todas sus variables incluyendo suplementos marítimos y aéreos, datos reales del envío (TMS/ERP), histórico de facturas por proveedor. |
| **ROI** | Detección del 100% de discrepancias, no solo las que alguien tiene tiempo de revisar. Cuantificación real de la desviación por proveedor — dato que hoy no existe. En facturación marítima, con más conceptos y recargos, el impacto acumulado puede ser especialmente alto. |
| **Riesgos** | Las tarifas deben estar digitalizadas y actualizadas. Si marca demasiadas facturas se genera desconfianza. La aparición de discrepancias antes invisibles debe gestionarse como mejora de proceso que beneficia a ambas partes. |
 
**Perspectiva profesional** — Todo responsable de logística sabe que hay facturas que se aprueban sin revisar a fondo porque el coste de revisarlas es mayor que la desviación individual. No es un problema de mala fe, es un problema de volumen, de tarifas complejas y de datos que se introducen a mano en ambos lados. Pero nadie suma esas desviaciones a final de año y cuando lo haces, el número asusta. Lo que necesitas no es más gente revisando facturas, es un sistema que compare automáticamente y te diga solo dónde hay una discrepancia. Con esos datos puedes trabajar con el transportista en limpiar el proceso, no en buscar culpables.
 
---
 
### 5. Asistente interno con IA generativa sobre procedimientos
 
| | |
|---|---|
| **Problema** | Manuales de operaciones, contratos de transporte, tarifas, procedimientos de aduanas, regulación por modo de transporte (IATA, ADR), instrucciones del TMS, particularidades por ruta y proveedor, políticas de empresa — cada documento en una ruta diferente de las carpetas compartidas. A veces no lo encuentras, otras lo encuentras en cuatro carpetas con versiones distintas. Al final nadie busca el documento: pregunta al compañero que más sabe. Y nadie te avisa de que un contrato de transporte está a punto de vencer. |
| **Tipo de IA** | LLM con RAG: indexa toda la documentación interna y responde preguntas en lenguaje natural citando la fuente y versión del documento. |
| **Datos** | Toda la documentación interna digital: manuales, contratos terrestres/marítimos/aéreos, tarifas, procedimientos, regulación por modo de transporte, guías de herramientas. El reto es organizativo: decidir la versión válida de cada documento y quién la mantiene. |
| **ROI** | Reducción drástica del tiempo buscando documentación. Eliminación del problema de versiones. Onboarding más rápido. Alertas de vencimiento de contratos y renovaciones de tarifas. |
| **Riesgos** | Si la documentación no está actualizada, el asistente da respuestas incorrectas con mucha seguridad. Requiere limpieza documental inicial. En documentación sensible (contratos, condiciones comerciales, regulación IATA) hay que definir permisos de acceso. |
 
**Perspectiva profesional** — En ocasiones he dedicado media hora a buscar un procedimiento que estaba en una carpeta compartida con un nombre que nadie recordaba, o he trabajado con una versión de unas tarifas que se habían actualizado hace dos meses pero nadie me había dicho. Y lo del contrato de transporte que vence sin que nadie se entere hasta que el proveedor llama nos ha pasado a todos. El problema de fondo no es que la gente no lea la documentación, es que encontrarla, saber si es la versión correcta y entenderla lleva tanto tiempo que es más fácil preguntar al de al lado. Un asistente que te responda al momento, con la fuente correcta, no sustituye el criterio de nadie pero sí elimina la excusa de "no sabía dónde estaba" o "yo tenía otra versión".
 
---
 
## Estratégicos
 
### 6. Previsión de demanda para planificación de capacidad de transporte
 
| | |
|---|---|
| **Problema** | La capacidad de transporte se planifica con previsiones del departamento comercial e históricos de transportistas, basándose en el Excel del año anterior e intuición. Siempre se falla. Si reservas de más, pagas huecos vacíos. Si reservas de menos, contratas de urgencia a precios de campaña. En marítimo los plazos de reserva son más largos y las penalizaciones mayores. En aéreo el coste por kilo es más alto y cada error pesa más. |
| **Tipo de IA** | Modelos predictivos (series temporales, regresión) que combinan histórico, estacionalidad, tendencias comerciales y variables externas. |
| **Datos** | Histórico de pedidos por cliente, producto, ruta y modo de transporte. Capacidad contratada vs utilizada por transportista, naviera y aerolínea. Calendario comercial. Estacionalidad y variables externas (congestión portuaria estacional, tendencias de mercado). |
| **ROI** | Reducción del sobrecoste por capacidad no utilizada y por contratación de emergencia en los tres modos. Mejor posición de negociación al comprometer volúmenes con mayor precisión. |
| **Riesgos** | Necesita histórico suficiente y de calidad. Picos imprevistos no se pueden anticipar. El equipo debe aprender a trabajar con rangos de confianza en lugar de un número fijo. La previsión solo es útil si se traduce en acción. |
 
**Perspectiva profesional** — He vivido campañas donde reservamos capacidad de más y pagamos huecos vacíos, y campañas donde nos quedamos cortos y tuvimos que contratar transporte de urgencia a precios que se comían el margen. Las dos situaciones duelen y las dos vienen del mismo sitio: tomar decisiones con un Excel del año pasado y la intuición de alguien que lleva tiempo en el sector. Esa intuición es valiosa y no desaparece, pero si la combinas con un modelo que te dice "con un 80% de probabilidad vas a necesitar entre X y Y camiones esta semana" o "vas a necesitar reservar Z TEUs en el próximo buque", las decisiones se toman con mucha más seguridad.
 
---
 
### 7. Estimación predictiva de ETAs
 
| | |
|---|---|
| **Problema** | Los tiempos de entrega se estiman por experiencia. Cuando la ETA falla, el cliente llama, comercial presiona, operaciones llama al transportista, y todos hacen de intermediarios. En marítimo los tránsitos son más largos y las variables más (congestión portuaria, transbordos, disponibilidad de atraque). En aéreo un retraso de horas puede hacer perder una conexión con efecto cascada. Nadie sabe con fiabilidad cuándo llega una carga hasta que está llegando. |
| **Tipo de IA** | Modelos predictivos que combinan histórico de tránsitos reales con datos en tiempo real (GPS, tracking AIS de buques, tracking aéreo, incidencias en ruta). El modelo recalcula continuamente: si un camión se avería y no llega a la aduana antes del cierre del viernes, el retraso no son las horas de avería sino los 3 días hasta el lunes. Si un buque pierde su ventana de atraque, el impacto incluye la conexión terrestre posterior. |
| **Datos** | Histórico de tránsitos reales (salida, entrega efectiva, ruta, modo, operador). Tiempos de despacho en aduanas. Posición en tiempo real (GPS, AIS, tracking aéreo). Horarios y calendarios de puntos críticos: aduanas, puertos, aeropuertos, incluyendo festivos. |
| **ROI** | ETAs basadas en datos reales de esa ruta, operador, modo y época del año. Reducción drástica de llamadas de seguimiento. Detección temprana de retrasos probables con margen para actuar. |
| **Riesgos** | Depende de la calidad del histórico. Eventos imprevistos no se anticipan. En multimodal (marítimo + terrestre, aéreo + última milla) cada tramo añade variabilidad. ETAs más precisas generan expectativas más altas. |
 
**Perspectiva profesional** — He tenido a mi equipo dedicando horas a llamar a transportistas para preguntar si van en plazo mientras el cliente nos llamaba a nosotros preguntando lo mismo. Todos haciendo de intermediarios de una información que nadie tenía realmente. Y lo peor no es el retraso en sí, es no darte cuenta de las consecuencias a tiempo. Un camión que se avería unas horas un viernes por la mañana parece un problema menor, pero si por esas horas no llega a la aduana antes del cierre y no abre hasta el lunes, acabas con tres días de retraso por algo que con visibilidad en tiempo real podrías haber resuelto de otra forma. En marítimo pasa lo mismo con las ventanas de atraque y los transbordos: un pequeño retraso en un punto genera un efecto cascada que, sin visibilidad, nadie ve hasta que es demasiado tarde. Un modelo que combine el histórico con lo que está pasando ahora no elimina los retrasos, pero te da dos cosas que hoy no tienes: visibilidad para anticiparte y credibilidad con el cliente cuando le das una fecha.
 
---
 
### 8. Optimización de modalidad de carga y transporte
 
| | |
|---|---|
| **Problema** | Para cada envío hay que decidir la modalidad más rentable: en terrestre, camión completo o grupaje; en marítimo, FCL o LCL; en aéreo, capacidad completa o consolidado. La decisión se toma con información incompleta — el sistema calculaba en kilos y no en volumen, haciendo imposible saber si compensaba llenar un camión, un contenedor o una posición aérea. En marítimo una mala decisión se arrastra semanas. En aéreo el coste por kilo es mayor y cada error pesa más. |
| **Tipo de IA** | Optimización y recomendación: analiza envíos pendientes y recomienda la modalidad más rentable por peso, volumen, destino, urgencia y tarifas. También puede recomendar el modo de transporte (marítimo vs aéreo según urgencia y coste). |
| **Datos** | Dimensiones y peso de cada unidad de carga (no solo kilos). Tarifas por transportista, naviera y aerolínea para carga completa y consolidada. Pedidos pendientes con destino, ventana de entrega y restricciones. Capacidades por tipo de vehículo, contenedor y posición aérea. Histórico de envíos con modalidad y coste real. |
| **ROI** | Recomendación automática de la modalidad y modo más rentable basada en datos reales. Visibilidad del coste real de cada decisión. Reducción del sobrecoste en los tres modos. En marítimo, donde los volúmenes son mayores, el impacto acumulado es especialmente alto. |
| **Riesgos** | Sin dato de volumen, el modelo no mejora el proceso actual. Las tarifas de consolidado dependen de disponibilidad del operador y carga de terceros. En aéreo la variabilidad de precios es mayor por estacionalidad. |
 
**Perspectiva profesional** — Cada semana tomábamos decenas de decisiones de carga completa o consolidada en terrestre, marítimo y aéreo basándonos en los kilos y en la experiencia, porque el sistema no calculaba volumen y no había forma rápida de comparar opciones entre modos de transporte. A veces pagabas un contenedor FCL que iba medio vacío y habría salido mejor por LCL, o mandabas aéreo consolidado algo que habría compensado esperar al próximo buque. No es que las decisiones fueran malas, es que se tomaban sin toda la información. Un sistema que te diga antes de contratar cuál es la opción más rentable con peso, volumen y tarifas reales en cualquier modo de transporte te quita la incertidumbre de una decisión que hoy se toma un poco a ciegas.
 
 
*Lidia García · Directora de Operaciones Logísticas · Abril 2026*
 
