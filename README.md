[README.md](https://github.com/user-attachments/files/30068207/README.md)
# RACK::GUARD — MBSE IoT · Detección de Intrusión en Gabinetes de Telecomunicaciones

Sitio web estático (HTML + CSS + JavaScript vanilla, sin dependencias) que presenta el
artículo científico **"MBSE: Diseño, Modelado e Implementación de un Prototipo Experimental
IoT para la Detección de Intrusión en Gabinetes de Telecomunicaciones"**.

> Prototipo IoT de bajo costo que detecta apertura de puertas e impactos mecánicos en racks
> de telecomunicaciones (Capa 1 del modelo OSI), diseñado con **Model-Based Systems
> Engineering (MBSE)** y el estándar **SysML** como única fuente de verdad.

**Autores:** Lenyn Duarte · Luis Morales · Rafael Cosme
**Institución:** Universidad Tecnológica de Panamá — Centro Regional de Veraguas · FISC
**Evento:** JIC-Nacional 2026, X Congreso IESTEC

---

## Resultados destacados

| Métrica | Valor |
|---|---|
| Efectividad en detección de intrusiones | **98 %** |
| Índice de falsos positivos | **< 3 %** |
| Trazabilidad de requisitos (MBSE Fase 6) | **100 %** |

## Stack técnico documentado

- **Sensores:** Reed Switch magnético + SW-420 piezoeléctrico (comparador LM393)
- **Pasarela:** script Python que parsea a JSON validado
- **Persistencia:** MySQL sobre contenedor Docker, auditado con DBeaver
- **Red segura:** VLAN 99 + ACL extendida simuladas en Cisco Packet Tracer
- **Modelado:** SysML (BDD / IBD / requisitos paramétricos)

---

## Estructura del repositorio

```
.
├── index.html            # Página principal
├── assets/
│   ├── css/styles.css     # Identidad visual: consola de seguridad
│   └── js/app.js          # Interactividad vanilla (filtros, copiar, reveal)
├── README.md
├── LICENSE
└── .gitignore
```

## Cómo verlo localmente

No requiere build ni instalación. Cualquiera de estas opciones:

```bash
# Opción 1 — abrir directamente
xdg-open index.html      # Linux
open index.html          # macOS

# Opción 2 — servidor local (recomendado)
python3 -m http.server 8000
# luego visita http://localhost:8000
```

## Publicar en GitHub Pages

1. Sube el repositorio a GitHub.
2. Ve a **Settings → Pages**.
3. En *Source* elige la rama `main` y la carpeta `/ (root)`.
4. Guarda. En unos minutos el sitio estará en
   `https://<tu-usuario>.github.io/<nombre-del-repo>/`.

El archivo `.nojekyll` incluido evita que GitHub Pages procese el sitio con Jekyll.

## Características del sitio

- Panel de estado en vivo con reloj y rotación de eventos simulados
- Bloques de código con botón de copiar (SQL, VLAN, ACL)
- Matriz de calibración filtrable (ruido ambiental / intrusión)
- Animaciones de aparición al hacer scroll (respetan `prefers-reduced-motion`)
- Navegación responsive con menú móvil
- Accesible: foco de teclado visible, HTML semántico

## Licencia

Ver [`LICENSE`](LICENSE). El contenido del artículo pertenece a sus autores.
