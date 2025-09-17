# Apunte Detallado (ASI): RUO, DyAC y Sistema de Gestión de Flotas

> [!note] Propósito del apunte  
> Llevarte de **cero** a **experto** en tres pilares de Administración de Sistemas de Información (ASI):
> 
> 1. **RUO** (Rol, Ubicación y Organización del área de SI/TI), 2) **DyAC** (Descripción y Análisis de Cargos) y 3) **modelado/capacidad** de un **Sistema de Gestión de Flotas**.  
>     Avanzamos de lo básico a lo avanzado, con contexto, ejemplos y buenas prácticas.
>     

---

## 0) Mapa mental del contenido

- **RUO** → Por qué SI/TI existe, dónde se ubica y cómo se organiza.
    
- **DyAC** → Cómo definir puestos clave (p. ej., Gerente de SI/TI) con criterios de RR.HH. y métricas.
    
- **Flotas** → Cómo traducir negocio en carga técnica (UPN, SLA, variables de comportamiento) y dimensionar.
    

> [!tip] Lectura recomendada  
> Recorre en orden. Al final hay **checklists**, **errores comunes**, **buenas prácticas** y **tendencias**.

---

## 1) RUO (Rol, Ubicación y Organización)

### 1.1 ¿Qué es RUO?

- **Rol:** la **razón de ser** del área de SI/TI (qué valor entrega al negocio).
    
- **Ubicación:** **dónde** se inserta en la organización (reportes, autonomía, centralización/descentralización).
    
- **Organización:** **cómo** se estructura (funcional, por proyectos, híbrida; qué subáreas y relaciones tiene).
    

> [!example] Analogía  
> RUO es como el **diseño de un equipo deportivo**:
> 
> - **Rol**: a qué juega (defensivo/ofensivo).
>     
> - **Ubicación**: en qué liga y con qué independencia decide.
>     
> - **Organización**: cómo distribuye posiciones y coordinaciones en la cancha.
>     

### 1.2 Por qué importa en ASI

- Alinea SI/TI con **estrategia** y **modelo operativo** del negocio.
    
- Reduce fricción entre áreas (operaciones, comercial, finanzas) → **flujo de valor** más rápido.
    
- Permite **priorizar** inversiones, **gobernar** riesgos y **medir** resultados (KPIs/SLA).
    

### 1.3 RUO propuesto (caso AGUNSA)

#### Rol: “Hacer algo con ellos” (coproducción)

- **Qué es:** SI/TI trabaja **junto a** las áreas usuarias (co-diseño, pruebas en sitio, adopción).
    
- **Cómo se usa:** squads mixtos negocio–tecnología, discovery con usuarios, iteraciones cortas.
    
- **Por qué así:** en logística multi-país los procesos varían por **leyes/clientes**; coproducir acelera adopción y reduce retrabajo.
    

> [!example] Caso práctico  
> Planificación de rutas: logística define reglas y restricciones; SI/TI integra motores de ruteo, UI y telemetría en ciclos de mejora continua.

#### Ubicación: Delegada (descentralizada con estándares)

- **Qué es:** autonomía local para responder a mercados/regulaciones, con **lineamientos corporativos** (arquitectura, seguridad, datos).
    
- **Cómo se usa:** decisiones tácticas locales + gobierno corporativo común (comités, blueprints).
    
- **Por qué así:** cambia **rápido** la realidad de cada plaza (combustible, normativa, tráfico).
    

#### Organización: por **proyectos funcionales** (estructura híbrida)

- **Qué es:** equipos temporales orientados a objetivos (p. ej., “Flotas”), integrando personas de Desarrollo e Infraestructura.
    
- **Cómo se usa:**
    
    - **Desarrollo de Aplicaciones:** Analista Funcional, Arquitecto SW, Devs, QA.
        
    - **Infraestructura/SecOps:** IT Manager, DBA, Soporte, Seguridad.
        
    - **Líderes de Proyecto:** orquestan equipos mixtos y relacionamiento con usuarios.
        
- **Por qué así:** **acopla** entrega rápida con **estándares comunes** (datos/seguridad).
    

> [!note] Variantes
> 
> - **Funcional pura:** eficiencia y especialización, pero menos flexibilidad.
>     
> - **Por productos/squads:** autonomía y foco, pero riesgo de “islas” si no hay gobierno de arquitectura.
>     

---

## 2) DyAC (Descripción y Análisis de Cargos)

### 2.1 ¿Qué es y para qué sirve?

- **Qué es:** ficha estructurada (formato Chiavenato) que define **misión, responsabilidades, autoridad, requisitos, competencias** y **métricas** de un cargo.
    
- **Para qué:** alinea expectativas, habilita selección/inducción, gestión del desempeño y **gobierno** del área.
    

### 2.2 Plantilla práctica (Gerente de SI/TI)

```markdown
### DyAC – Gerente de SI/TI
- **Misión:** Alinear SI/TI con objetivos de negocio; asegurar disponibilidad, seguridad y eficiencia de la plataforma tecnológica.
- **Dependencia:** Dirección General / COO.  
- **Reportes directos:** Jefes de Desarrollo e Infraestructura.  
- **Relaciones clave:** Operaciones, Comercial, Finanzas, RR.HH., Proveedores.

#### Responsabilidades (qué hace)
- Estrategia y portafolio de TI; roadmap y priorización.  
- Arquitectura y seguridad (IAM, datos, continuidad, DRP).  
- Gestión de proveedores y contratos; presupuesto.  
- Gobierno de proyectos (PMO), KPIs y SLA; auditoría y cumplimiento.

#### Autoridad (qué puede decidir)
- Estándares tecnológicos y de datos; políticas de seguridad.  
- Asignación de recursos; contratación tecnológica dentro de budget.  
- Priorización de iniciativas y escalamiento de incidentes críticos.

#### Requisitos (qué se espera)
- Educación: Ing. en Sistemas (o afín); posgrado deseable (PM/Negocios).  
- Experiencia: 8–10 años en TI, 5+ en liderazgo.  
- Competencias: liderazgo, negociación, storytelling ejecutivo, data literacy.

#### Indicadores (cómo se mide)
- Disponibilidad (%), MTTR/MTBF, cumplimiento de SLA.  
- Desvío presupuestario (%), ROI de proyectos.  
- Satisfacción de usuario (CSAT/NPS), seguridad (incidentes, hallazgos).
```

> [!tip] Métricas que “mueven la aguja”  
> Prioriza 5–7 KPIs accionables y acordados con negocio. Evitá paneles “navideños”.

### 2.3 RACI recomendado (alto nivel)

|Actividad / Rol|Gerente SI/TI|Jefe Desarrollo|Jefe Infra/SecOps|Líder de Proyecto|Usuario Clave|
|---|--:|--:|--:|--:|--:|
|Definir estrategia TI|**A/R**|C|C|I|C|
|Priorizar portafolio|**A/R**|C|C|C|C|
|Arquitectura/Seguridad|**A**|C|**R**|I|I|
|Entrega de proyecto|A|C|C|**R**|C|
|Operación/Soporte|I|I|**R**|I|C|

> **A** = Accountable, **R** = Responsible, **C** = Consulted, **I** = Informed.

---

## 3) Gerente de SI/TI vs Líder de Proyecto (LP)

### 3.1 Diferencias esenciales

|Dimensión|Gerente de SI/TI|Líder de Proyecto|
|---|---|---|
|**Horizonte**|Estratégico (área completa)|Táctico (proyecto específico)|
|**Decisiones**|Estándares, inversiones, talento|Alcance, plan, riesgos, calidad|
|**Éxito**|SLA, seguridad, ROI portafolio|Entrega a tiempo/costo/calidad|
|**Stakeholders**|Comité ejecutivo, áreas core|Sponsor, equipo, usuarios finales|
|**Habilidades**|Negocio+arquitectura, gobierno|PMBOK/Ágil, facilitación, reporting|

> [!warning] Error común  
> “Como liderás un proyecto grande, sos Gerente de TI”. **No**: el gerente gobierna **toda** la función TI (estrategia+operaciones).

---

## 4) Sistema de Gestión de Flotas (capacidad y rendimiento)

### 4.1 ¿Qué es y por qué “transaccional en tiempo real”?

- **Qué:** plataforma que ingiere **telemetría** (GPS/sensores), calcula rutas, gestiona planillas/turnos/incidentes e integra con ERP/BI.
    
- **Por qué transaccional:** predominan **transacciones cortas y frecuentes** (eventos/seg) con **baja latencia** esperada por operación.
    

> [!example] Flujo típico  
> GPS (vehículo) → API/MQ → validación/reglas → persistencia → actualización de mapa/UI → alertas.

### 4.2 UPN (Unidades de Predicción Natural)

#### Concepto

- Métricas **de negocio** que **explican** la carga técnica.
    
- Se diseñan para **predecir** crecimiento de uso vs. recursos.
    

#### UPN clave (caso flotas)

- **APM**: Actualizaciones de Posición por Minuto.
    
- **LSM**: Lecturas de Sensores por Minuto.
    
- **ROCD**: Rutas Optimizadas Calculadas por Día.
    
- **AIGD**: Alertas/Incidentes Generados por Día.
    
- **RGU**: Reportes Generados por Usuario.
    

> [!note] Regla de oro  
> Si duplicás la **flota activa**, suben **APM/LSM** ~linealmente (manteniendo intervalos).

### 4.3 Relaciones simples (para estimar carga)

```[text]
# Llegadas (throughput)
APM (msg/s) ≈ (N_vehículos) / (intervalo_GPS_en_segundos)

# Ejemplo:
# 300 vehículos, 1 GPS cada 5 s → 300/5 = 60 msg/s

LSM (msg/s) ≈ N_vehículos × tasa_evento_por_vehículo
```

> [!example] Cálculo rápido de almacenamiento  
> 300 veh × 12 msg/min × 1440 min/día = **5.184.000** posiciones/día.  
> A 150 B efectivos/registro ≈ **~740 MB/día** solo GPS (sin índices ni sensores).

### 4.4 SLA (externos) y objetivos (internos)

**Externos (experiencia usuario):**

- GPS en UI: **≤ 3 s** (p95)
    
- Ruta: **≤ 10 s** (p95)
    
- Reporte on-demand: **≤ 30 s** (p95)
    
- Disponibilidad servicios críticos: **≥ 99,9%** mensual
    

**Internos (salud del sistema):**

- Utilización CPU/Disco: **≤ 70–80%** en picos
    
- Latencia extremo a extremo (vehículo→UI): **≤ 1–2 s** media
    
- **Back-pressure** controlado (colas con límites y reintentos exponenciales)
    

> [!tip] Pirámide de control  
> **SLA** visibles se sostienen con **SLO** internos (p95/p99), telemetría (APM/LSM), y **pruebas de carga** periódicas.

### 4.5 Variables de comportamiento (fiabilidad operacional)

- **Fiabilidad** (MTBF alto), **Disponibilidad** (≥ 99,9%), **Mantenibilidad** (MTTR bajo).
    
- **Seguridad** (IAM, cifrado en tránsito/descanso, hardening).
    
- **Performabilidad**: degradación **graciosa** ante fallos (graceful degradation).
    

### 4.6 Arquitectura de referencia (high level)

- **Ingesta**: HTTP/MQTT + cola de mensajería (event streaming).
    
- **Procesamiento**: microservicios con **autoscaling**; validación, enriquecimiento, reglas.
    
- **Persistencia**:
    
    - **OLTP** (posiciones recientes, incidentes);
        
    - **TSDB**/Data Lake (históricos);
        
    - **Cache** (map tiles, últimas posiciones).
        
- **APIs/UI**: web para despacho + móvil para choferes.
    
- **Observabilidad**: métricas (APM/LSM), trazas, logs, tableros de SLO/SLA.
    
- **Seguridad**: IAM, roles por contexto, cifrado, rotación de secretos.
    

> [!warning] Errores frecuentes en flotas
> 
> - Persistir **todo** en una única base OLTP (crece y se vuelve lenta).
>     
> - No definir **UPN** → incapacidad de proyectar capacidad.
>     
> - Omitir **back-pressure** → tormenta de reintentos y caídas en cascada.
>     
> - Olvidar **retención/archiving** de históricos (costos y performance).
>     

---

## 5) Cómo defender la propuesta (speech técnico–negocio)

1. **RUO colaborativo** porque la operación logística varía por plaza y cliente: coproducir acelera adopción y reduce retrabajo.
    
2. **Ubicación delegada** con estándares globales equilibra velocidad local y control corporativo.
    
3. **Organización por proyectos funcionales** permite foco (objetivos claros) + gobierno (arquitectura/seguridad).
    
4. **UPN** traducen negocio a carga; si sube la flota, suben APM/LSM y planificamos recursos.
    
5. **SLA** centrados en operación: si GPS > 3 s, se pierden decisiones en tiempo real.
    
6. **Variables de comportamiento** garantizan continuidad (99,9%), seguridad y recuperación rápida (MTTR).
    

---

## 6) Buenas prácticas (resumen accionable)

- **RUO**
    
    - Acordá el **rol** con negocio (valor esperado).
        
    - Definí **foros de gobierno**: comité de demanda, arquitectura, seguridad.
        
    - Mantené **catálogo de servicios** TI con **SLA**.
        
- **DyAC**
    
    - Escribí **misión** en 1–2 oraciones medibles.
        
    - Ligá **responsabilidades** a **KPIs** concretos.
        
    - Usá **RACI** para evitar solapamientos.
        
- **Flotas**
    
    - Definí **UPN** y fórmulas simples (APM/LSM).
        
    - Diseñá **SLO p95/p99** previos al SLA.
        
    - Separá **OLTP** (reciente) de **histórico** (TSDB/Lake).
        
    - Implementá **colas**, **circuit breakers** y **retry con jitter**.
        
    - Plan de **retención/archiving** y **simulaciones de carga** trimestrales.
        

---

## 7) Errores comunes (y cómo evitarlos)

- **Confiar en organigramas sin procesos** → agrega **procesos de priorización** y **métricas**.
    
- **SLA sin monitoreo** → define **métricas** y visibilidad real-time.
    
- **Arquitectura monolítica para eventos** → usa colas/event streaming y caché.
    
- **No probar picos** (fin de mes, campañas) → ejecuta **tests estacionales** y **runbooks**.
    

---

## 8) Tendencias actuales en ASI aplicables

- **Producto digital/Value stream** sobre proyectos aislados (foco en outcomes continuos).
    
- **FinOps**: costo como métrica de diseño (autoescalado, right-sizing).
    
- **Plataformas de datos**: separación claro **OLTP/analítica**, feature stores.
    
- **Security by design**: Zero Trust, IAM granular, SBOM y gestión de secretos.
    
- **Observabilidad** integral: métricas, trazas distribuidas y SLOs como contrato.
    

---

## 9) Checklists rápidos

### 9.1 RUO

-  Rol definido con outcomes de negocio.
    
-  Ubicación (reportes, autonomía, foros).
    
-  Organización (subáreas, perfiles, RACI).
    
-  Gobierno (priorización, arquitectura, seguridad).
    

### 9.2 DyAC

-  Misión y responsabilidades claras.
    
-  Autoridad explícita.
    
-  KPIs/SLA de puesto.
    
-  Competencias y experiencia requeridas.
    

### 9.3 Flotas

-  UPN (APM, LSM, ROCD, AIGD, RGU).
    
-  Fórmulas de llegada y almacenamiento.
    
-  SLA externos y SLO internos p95/p99.
    
-  Arquitectura con colas, cache y storage por tipo.
    
-  Observabilidad y planes de pico/fallo.
    

---

## 10) Frases para la puesta en común (sonar experto)

- “Elegimos **coproducción** en el Rol porque reduce el time-to-value y mejora la adopción en operaciones multi-país.”
    
- “La **ubicación delegada** balancea respuesta local con **estándares** globales de arquitectura y seguridad.”
    
- “Modelamos la carga con **UPN**: al subir la flota, crecen **APM/LSM**; por eso escalamos ingesta y storage.”
    
- “Nuestros **SLA** (GPS ≤ 3 s, Rutas ≤ 10 s) responden al impacto operativo; detrás hay **SLO p95/p99** y pruebas de carga.”
    
- “Separamos **OLTP** de **histórico** para mantener latencias bajas hoy y explotar analítica mañana.”
    

---

> [!note] Cierre  
		> Con RUO bien definido, DyAC profesionalizado y un modelo de flotas sustentado en **UPN+SLA+arquitectura de eventos**, podés defender la propuesta ante negocio y sostenerla en operación.%% %% %%  %% %% %%