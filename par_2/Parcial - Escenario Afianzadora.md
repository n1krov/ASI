
Se adjunta Caso de Estudio: "SEGURO VIRTUAL" (Fuente: Revista mensual **Information Technology Nº 191 - Agosto 2013**) y la publicación digital **"Afianzadora Latinoamericana y su éxito con VMware"** extraída de http://www.datamation.com.ar/afianzadora-latinoamericana-y-su-exito-con-vmware-4193.

## Consignas

**A) Provisión de SI/TI**
**I) Los siguientes criterios han sido considerados para guiar la migración de las aplicaciones. Complete la tabla, de acuerdo con lo pedido (12ptos. 4 ptos cada criterio completamente correcto, sino 0pto)**

|                                                 | Escalabilidad | Disponibilidad | Requerimientos de HW |
| :---------------------------------------------- | :------------ | :------------- | :------------------- |
| **Especificación del criterio en el escenario** |               |                |                      |
| **Tipo de parámetro al que dará origen**        |               |                |                      |

**II) ¿Qué esquema de provisión y de qué recurso de SI/TI mantienen Afianzadora Latinoamericana con la empresa Manas TI?. Explique detallada, profunda y fundadamente. (8ptos)**

**B) Subsistema de Aplicación de SI/TI. Planificación de la capacidad. Subsistema de Seguimiento de los SI/TI (30 ptos - 10 ptos cada respuesta completamente correcta)**

**Para el escenario en estudio:**

**I. ¿Qué unidades de predicción natural (UPN) seleccionaría para planificar la demanda potencial en un ambiente informático de seguros de caución? Fundamente su respuesta.**

**II. ¿Cómo considera que puede ser el comportamiento de la carga de trabajo de esas UPN. Fundamente su respuesta.**

**III. ¿Con qué técnica de predicción estimaría la carga futura para cada UPN identificada en el punto B.I). Justifique la propuesta en forma individual**

## Artículo
### **Seguro virtual**
*Por Vanina Poledri*

---

Para ganar en disponibilidad y escalabilidad, Afianzadora implementó una solución de virtualización y mejoró su correo con una inversión de U$S 50.000.

**E**n seguros breves. Optimizando la infraestructura para ganar en agilidad y escalabilidad. Con ese objetivo en mente, todo el equipo de Afianzadora Latinoamericana, una de las líderes en seguros de caución, se abocó a un proyecto de reingeniería de procesos que les garantizara no solo el cumplimiento de las pólizas, que es el mercado donde operan, sino también dar una respuesta ágil a las grandes y pequeñas empresas a las que atienden. "Teníamos necesidades específicas, como en el caso de Afianzadora, donde sus especialistas deben emitir pólizas de hasta $100 millones, con la agilidad y el *expertise* del caso. La empresa creció en 2005 con un Blade Center de IBM y el plantel comercial pasó de ocho a 25. En ese momento, la infraestructura con la que contaba la empresa era básica: un centro de cómputos de dos servidores (en realidad, computadoras de escritorio) que comprendía el file server y los sistemas core de trabajo. La estructura tenía un presupuesto acotado".

> **"No se paraliza ningún procedimiento ni proceso y se asegura la continuidad de la operación"**
>
> — Fernando Galazzi, Gerente de Operaciones de Afianzadora

---

(Página 2)

to mínimo, por lo que buscaba una solución estable para no tener problemas legales", comenta Gustavo Estigarribia, CIO, quien, a su vez, se hizo cargo de Operaciones de la compañía. "La decisión, si bien recaía como responsable de la empresa en mí, sumó a las áreas operativas".

El llamado se apoyó en la consultora Manas IT, que sugirió una solución que realiza el soporte de usuarios y servidores. Fue, precisamente, esta consultora la que en 2011 alertó a Afianzadora de que la estructura les estaba quedando chica. "Hacía 5 años no habían pasado de 2 servidores y en los últimos 2 años habían pasado a 32 físicos, con los problemas que esto supone en la disponibilidad como en la escalabilidad. Si bien venían experimentando en el datacenter de la disponibilidad, necesitábamos centralizarla y lograr un buen *disaster recovery* de los datos".

"Manas nos sugirió que la mejor opción era virtualizar. Pensé también que agrupar todo a la nube, pero no me terminaba de convencer", dice Galazzi. Entonces, se consideraron tres opciones: Microsoft Hyper-V, XenServer o VMware. "La versión de Hyper-V de ese momento era más barata en la adquisición de licencias, pero era cruda en estabilidad", recuerda. "La elección de vSphere, socio de Manas IT, tiene lo mejor del mundo Microsoft con la facilidad y lo mejor de Linux en cuanto a la estabilidad", opina Estigarribia.

De este modo, se eligió a Sirtac (una empresa local que se armó con mis ex compañeros de facultad), por lo que se decidió construir el DC Core de Sirtac. "Arrancaron con un *assessment* y, de ahí, se cotizó la infraestructura de siete servidores de pruebas y los pusieron en un ambiente de prueba. 'A esto no lo creo, no tenía un punto de error', dice Estigarribia. Se migró de Zimbra (del cual Afianzadora es un *reseller*) y también de Microsoft.

La implementación se realizó con seis servidores Dell 8710 y está basada en su correo electrónico, más U$S 8.000 en licencias de Zimbra (el correo electrónico, que está en Windows e Intranet, ya es un servidor que maneja aplicaciones con AFIP, "ya que tenemos la obligación de facturar con Código de Barras y factura electrónica y hacer las pólizas electrónicas que se presentan a la AFIP y a la Superintendencia de Seguros". También se migró Sirtac, una solución de Afianzadora y un producto para la facturación con productos).

Una de las ventajas que rescata Galazzi sobre Zimbra es que ahora tienen para ampliar o achicar la capacidad del disco bajo en estos temas desde 1979 en forma de cascada. "Además, cada vez que hay que agregar espacio al disco sigue siendo un proceso muy lento; la modificación es totalmente transparente, los resultados son fabulosos", destaca, y agrega: "Se hizo lo mínimamente necesario para una empresa que no tiene un equipo de IT propio".

La migración del correo a Zimbra implicó que nada por el cambio de interfaz del usuario final, acostumbrados al Outlook. "Se migraron en fases los correos de las 40 personas, durante un mes, sin contar en Buenos Aires, más las sucursales de Salta, Mendoza, Mar del Plata y Rosario. Era la primera gran migración".

"La migración de Zimbra fue un éxito. Se hizo por proveedor nuevo, migrando cada cuenta de los usuarios a que estaban en servidores distintos a uno solo en rack, permitiendo el uso en cascada".

El cuello de botella fue una "mala implementación de BlackBerry, que para Estigarribia 'requería reiniciarla bastante', aunque pondera que 'el resultado que obtuvimos del nuevo proveedor fue bueno'. La verdad es que fue una experiencia positiva", afirma el gerente de Operaciones de Afianzadora. "Teníamos caídas de servicio y no podíamos estimar el riesgo de que haya roto".

"Otro beneficio que no se tuvo en cuanto a la capacidad de crecimiento es la posibilidad de escalar en la cantidad de servidores. No se para ningún procedimiento ni proceso y se asegura la continuidad de la operación".

La administración también tiene ventajas. "La practicidad de hacerlo vía remota nos da más celeridad. Hacemos ajustes replicando el servidor físico, lo que la herramienta nos permite hacer transparente, más las alarmas visuales se pueden prender cuando el servidor necesita más mantenimiento", cierra Galazzi.

#### **A paso seguro**
La nueva infraestructura incluyó servidores Dell, provistos por el sistema de leasing replicados con VMware, virtualizados. La implementación, desde el *assessment* del servicio, duró entre 15 y 20 días. "Pudimos balancear la carga y transcurrir el verano sin serios inconvenientes, tras lo que la empresa pudo certificarla", aclara Estigarribia.

#### **HIGHLIGHTS**
Solución de alta disponibilidad a la plataforma de correo, que también sirve de entorno al sistema de facturación electrónica.
**Inversión:** U$S 42.000 en hardware y U$S 8.000 en consultoría e implementación.
**Protagonista:** Fernando Galazzi, Gerente de Operaciones de Afianzadora.

#### **TECNOLOGÍA**
**Software:** VMware vSphere 5, Sirtac.
**Consultoría:** Manas IT, Zimbra.
**Hardware:** 2 Servidores Dell 8710, 2 servidores Quad Core, 50 diskettes ReoIgb y 8 Gb de ram.
**Almacenamiento:** Dell PowerVault.
**Proveedores:** Sirtac, Silver, Jabber.
**Telecomunicaciones:** Personal, Movistar, Telefónica/Telefónica Fija.

## Resolución
