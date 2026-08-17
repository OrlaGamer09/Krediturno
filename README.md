# Krediturno

Sorteo diario del orden de atención para los 8 puestos comerciales. Un botón revuelve los puestos y muestra el orden 1–8 del día; el resultado se puede compartir por WhatsApp con un clic.

## Uso

Es una sola página, sin backend ni build. Para probarla localmente basta con abrir `index.html` en el navegador, o servirla con cualquier servidor estático:

```
npx serve .
```

## Cómo funciona

- **Equipo**: los 8 puestos (Kredit Planta Norte, Kredit Planta Centro, Fianti Planta, Call Center, Terceros Norte, Terceros Centro, Solux Zona 1, Solux Zona 2) están precargados. Se pueden editar desde "✎ Editar equipo" — el cambio se guarda en el navegador del dispositivo (`localStorage`), sin cuenta ni base de datos.
- **Sorteo**: un clic en "Sortear turnos de hoy" revuelve el equipo y asigna el orden 1–8. Solo se permite un sorteo por día; repetirlo pide confirmación porque reemplaza el orden ya asignado.
- **Compartir**: el botón de WhatsApp arma el texto del resultado y abre `wa.me` listo para enviar. "Copiar" deja el mismo texto en el portapapeles.
- Todo el estado (equipo y sorteo del día) vive en el dispositivo donde se usa — dos computadores no se sincronizan entre sí.

## Desplegar

Al ser un solo archivo HTML autocontenido (fuentes incluidas), sirve con cualquier hosting estático:

- **Netlify / Vercel**: arrastrar la carpeta o conectar el repo de Git; no requiere configuración de build.
- **GitHub Pages**: activar Pages sobre la rama principal, sirviendo desde la raíz.

## Empacar como app móvil (opcional, a futuro)

Si más adelante se necesita instalar como app en el teléfono en vez de abrirla en el navegador, se puede envolver este mismo `index.html` con [Capacitor](https://capacitorjs.com/) sin tocar la lógica de la página.
