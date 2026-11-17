# Ondas · laboratorio de seguridad web

Aplicación de música **ficticia** que sirve de laboratorio para practicar seguridad web
(módulos PPS, Hacking Ético y Gestión de Incidentes). Es un único `index.html`
(HTML + CSS + JavaScript) sin servidor ni base de datos; el estado se guarda en el
`localStorage` del navegador.

Demo (GitHub Pages): https://javier132006.github.io/Web-Ciber/

## Aviso

Las vulnerabilidades están puestas **a propósito** (credenciales en el código, autenticación
en el cliente, XSS, IDOR). No reutilices este patrón en una aplicación real ni uses
contraseñas reales. Todos los datos y cuentas son ficticios. Practica solo en tu propia
instancia local y no ataques servicios de terceros.

## Ejecutar en local

```bash
git clone https://github.com/javier132006/Web-Ciber.git
cd Web-Ciber
python3 -m http.server 8000 --bind 127.0.0.1
```

Abre http://127.0.0.1:8000. Cuenta de prueba: `ana` / `ana123`.

## Retos

La sección **Laboratorio** de la aplicación incluye cinco retos: código fuente, control de
acceso, XSS basado en DOM, XSS almacenado e IDOR. Aquí no se publican las soluciones.

> Versiones: `index.html` (raíz) es la versión **corregida** frente a XSS (reto opcional).
> La versión **vulnerable con los cinco retos** está en `lab-vulnerable/`
> (https://javier132006.github.io/Web-Ciber/lab-vulnerable/). Practica en local con ella.

## Pruebas

Abre `tests/xss.test.html` desde el servidor local; el título de la pestaña indica `ALL PASS` o `FAIL`.

## Despliegue

Se publica con GitHub Pages desde la rama `main`, carpeta raíz. Al ser un sitio estático no
necesita contenedor. Si se quisiera con Docker bastaría una imagen de nginx que sirva
`index.html`, publicada solo en `127.0.0.1`.

## Estructura

| Fichero | Descripción |
|---|---|
| `index.html` | Aplicación con el XSS corregido |
| `lab-vulnerable/index.html` | Versión original con los cinco retos |
| `tests/xss.test.html` | Prueba de regresión contra XSS |
| `.gitignore` | Evita subir `.env`, bases de datos y registros |
| `README.md` | Este documento |
| `LICENSE` | Licencia MIT |
