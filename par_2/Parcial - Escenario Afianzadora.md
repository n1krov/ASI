
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

Empresa joven. Optimización tecnológica. Baja inversión. Alta disponibilidad. Cuatro variables, todas relacionadas con Afianzadora Latinoamericana.

**Esta compañía ofrece seguros de caución** que son instrumentos de garantía por los cuales el asegurador garantiza al beneficiario el cumplimiento de las obligaciones no dinerarias de un tercero que es el tomador de las pólizas. 
Dentro del mercado asegurador es uno de los rubros más pequeños y, aunque las grandes compañías lo ofrecen, también es provisto por empresas especializadas, como es el caso de Afianzadora, que factura $100 millones al año.

La firma **nació en el 2005 con un plantel compuesto por los tres dueños más ocho personas**. Con solo once empleados, en ese momento la infraestructura tecnológica que se desplegó fue básica: **un servidor** (en realidad, era *una computadora personal* que cumplía tal fin) y **las estaciones de trabajo para los usuarios**. 

> **"No se paraliza ningún procedimiento ni proceso y se asegura la continuidad de la operación"**
>
> — Fernando Gagazzi, Gerente de Operaciones de Afianzadora

---

(Página 2)

Teníamos un presupuesto mínimo, por lo que buscábamos software open source para no tener problemas legales. Recuerda Fernando Gagazzi, gerente de operaciones de Afianzadora. Con esa estructura, a su cargo quedó también el área de sistemas, y actualmente continúa como responsable de la misma, además de sus tareas operativas. 
Desde el inicio, Afianzadora se apoyó en la consultora Manas TI para la gestión tecnológica, que realiza el soporte de usuarios y el mantenimiento. Fue precisamente esta consultora la que en el 2011 alertó a Afianzadora de que la estructura les estaba quedando chica. Es que seis años no habían pasado en vano. De los originales 11 usuarios, habían pasado a 35, y eso era evidente tanto en la disponibilidad como en la lentitud que estaban experimentando en el uso de los aplicativos. El objetivo fue darle alta disponibilidad a la plataforma sin complejizarla y lograr un buen respaldo de los datos. 
«Manas nos sugirió que la mejor opción era virtualizar. Pensé también en migrar todo a la nube, pero no me terminó de cerrar», reconoce Gagazzi. Entonces la consultora les propuso dos opciones, Microsoft Hyper-V y VMware. «La versión de Hyper-V de ese momento era un poco más barata en la adquisición, pero estaba más cruda en estabilidad», recuerda Enrique Estigavirga, socio de Manas-TI. «La de VMware es fácil de manejar, tiene lo mejor del mundo Microsoft en la facilidad y lo mejor de Linux en cuanto a la estabilidad», opina Estigavirga. 
Para ese entonces la arquitectura de Afianzadora era un mix de los mundos de Microsoft y Linux, por lo que se decidió continuar con esa mezcla. La implementación se realizó con un presupuesto de U\$S42.000 para invertir en servidores, storage, cintas de backup y en las licencias de Zimbra (también de VMware) para correo electrónico, más U\$S 8.000 dólares en consultoría, que fue provista por Manas TI.
#### A paso seguro. 
La nueva infraestructura incluye servidores Dell —adquiridos con el sistema de leasing—, replicados con máquinas virtualizadas. La implementación, desde que llegaron los servidores, duró entre 15 y 20 días, con virtualización y simulacro de carga y transacciones para evitar inconvenientes, tras lo que se migró en forma definitiva. «Arrancaron con una infraestructura de 7 servidores, y ahora tienen 20. Crearon un ambiente de prueba y de calidad que no tenían», detalla Estigavirga. 
Se migró también el core de seguros (que es de DC Sistemas y está basado en Linux) así como las autorizaciones de usuarios; otras funcionalidades están en Windows e Integra, que es un servidor que maneja aplicaciones con AFIP, «ya que tenemos la obligación de facturar con código de autorización electrónica y hacer las pólizas electrónicas a favor de la aduana, que se presentan a la AFIP a través del SIAP», detalla, Gagazzi. También se migró Sirius, un servidor que maneja la relación de afianzadora con productores y brokers.
Una de las ventajas que resalta Gagazzi es la flexibilidad que ahora tienen para ampliar o modificar los servidores. «Trabajo en estos temas desde 1979, y con la tecnología tradicional, cada vez que hay que agregar memoria o espacio en discos sigue siendo un problema. Ahora, cualquier modificación es totalmente simple. Las máquinas virtuales son fabulosas», destaca, y agrega que eso es algo sumamente necesario para una empresa que no tiene un equipo interno de sistemas. 
La migración del correo a Zimbra fue algo más traumática, más que nada por el cambio de interfaz para los usuarios acostumbrados al Outlook. «Se migró el histórico de correos de las 40 personas distribuidas entre la sede en Buenos Aires, más las sucursales en Córdoba, Mendoza, Mar del Plata y Rosario, que acceden a esta prestación», enumera Gagazzi.
Este cambio se hizo en paralelo. «La migración de Zimbra fue conviviendo con el servidor nuevo, migrando cada cuenta de a una, pese a que estaban en servidores distintos y de distintas marcas, permitiendo el uso en paralelo».
El cuello de botella fue una pequeña parte: El servidor de BlackBerry, que para Estigavirga «es una herramienta bastante tosca», aunque para Gagazzi sigue siendo bueno el resultado que obtienen los smartphones del proveedor canadiense. En cuanto a la disponibilidad, el gerente de operaciones es terminante: «No tuvimos caídas de servicio y ni una máquina virtual que se haya roto». Otro beneficio ganado es en cuanto a la capacidad de crecimiento «La posibilidad de escalar en las máquinas, sea en memoria o disco, es enorme. No se paraliza ningún procedimiento y proceso, mientras tanto, y se asegura la continuidad de la operación». 
La administración también ganó ventajas. «La practicidad más concreta es cuando hacemos ajustes replicando el servidor físico, lo que la herramienta hace automáticamente, más las alarmas visuales que se encienden cuando el servidor necesita más rendimiento, cierra Gagazzi.
#### **HIGHLIGHTS**
**Objetivo:** Darle alta disponibilidad a la plataforma sin tener que complejizarla y mejorar el sistema de correo electrónico. 
**Plazo:** Cuatro meses.
**Inversión:** U\$S42.000 en hardware y software, U\$S 8.000 en consultoría e implementación. 
**Líder de proyecto:** Fernando Gagazzi, gerente de operaciones de afianzadora.
#### **TECNOLOGÍA**
**Solución:** VMware Sphere 5, VMware Simbra.
**Proveedor:** Manas-TI y VMware. 
**IT Corporativa:** 
**Hardware:** Dos servidores del R710 32 GB de RAM, dos procesadores Quad-Core, cincuenta Desktops Banghó Y tres notebooks Dell.
**Software:** VMware vCenter, Zimbra Integra, Sirius, DC Sistemas, SQL Server.
**Telecomunicaciones:** IPLAN (internet), Movistar (móvil), Telefónica (telefonía fija).

## Resolución
