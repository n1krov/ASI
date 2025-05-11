
# 🛰️ HTTP Ping - Grupo 7

Este proyecto permite simular un "ping" a un servidor HTTP utilizando Python y un entorno visual mejorado gracias a `pwntools`. Además, se provee un script en Bash que automatiza todo el proceso: iniciar un servidor web, activar el entorno virtual y ejecutar el script principal.

---

## 📁 Archivos

- `http_ping.py`: script principal que realiza peticiones HTTP periódicas al servidor.
- `runtest.sh`: script Bash que inicia el servidor y ejecuta el ping.
- `requirements.txt`: contiene las dependencias necesarias (por ejemplo, `pwntools`, `requests`).

---

## 🚀 Requisitos

- Python 3
- `pip`
- Entorno virtual (`venv`) creado en la raíz del proyecto

---

## ⚙️ Instalación

1. **Cloná o descargá el proyecto.**

2. **Creá y activá un entorno virtual:**

```bash
   python3 -m venv venv
   source venv/bin/activate
```

3. **Instalá las dependencias:**


```bash
   pip install -r requirements.txt
```

---

## 🧪 Uso

Una vez que el entorno virtual esté configurado e instalado:

```bash
chmod +x runtest.sh
./runtest.sh
```

Este script:

* Muestra un banner decorativo.
* Inicia un servidor HTTP en el puerto `8081`.
* Activa el entorno virtual.
* Ejecuta `http_ping.py` para empezar a enviar peticiones al servidor.

---

## ❌ Salida segura

Para detener la ejecución, simplemente presioná `Ctrl + C`. Ambos scripts están preparados para manejar la interrupción limpiamente y cerrar los procesos de forma segura.

---

## 🧠 Notas

* El intervalo entre peticiones HTTP está definido en `http_ping.py` (línea 10). Podés modificarlo si necesitás ajustar la frecuencia de los pings.
* El servidor HTTP sirve el contenido del directorio actual.

