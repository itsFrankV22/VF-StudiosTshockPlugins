# Protection Stones

## Descripción
**Protection Stones** es un plugin diseñado para proteger áreas en el servidor utilizando "piedras de protección". Estas piedras permiten a los jugadores administrar sus áreas protegidas y compartir acceso con otros usuarios.

## Comandos disponibles

### Información y gestión:
- **`/ps help`** – Muestra este mensaje de ayuda.
- **`/ps list`** – Muestra todas tus protecciones.
- **`/ps info {#}`** – Muestra información detallada sobre una protección específica.

### Colocación y movimiento:
- **`/ps set {#}`** – Coloca una de tus protecciones.
- **`/ps move {#}`** – Mueve una protección existente.
- **`/ps remove {#}`** – Desactiva una protección.

### Administración de acceso:
- **`/ps allow {#} {Jugador}`** – Agrega a un amigo a la protección.
- **`/ps disallow {#} {Jugador}`** – Elimina a un amigo de la protección.

### Administración de protecciones de otros jugadores:
- **`/ps add {PlayerName} {nv}`** – Añade una protección a un jugador.
- **`/ps del {PlayerName} {#}`** – Elimina una protección de un jugador.
- **`/ps checklist {PlayerName}`** – Muestra las protecciones de un jugador.

## Instalación
1. Descarga el archivo **ProtectionStones.dll** desde la sección de releases.
2. Coloca el archivo en la carpeta `ServerPlugins` de TShock.
3. Reinicia el servidor y usa `/ps help` para verificar que el plugin está funcionando.

> Requiere de La dependencia `Mono.Data.Sqlite` en la carpeta `bin`

## Soporte
Si tienes dudas o problemas, puedes contactar a **FrankV22**. ¡Espero que disfrutes usando Protection Stones! 🚀
