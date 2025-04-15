# EasyAutoBackup

## Descripción
**EasyAutoBackup** es un plugin que automatiza la creación de copias de seguridad del mundo y la carpeta `tshock` cada hora. Los backups pueden ser instalados posteriormente, pero el orden y método de instalación son responsabilidad del usuario.

## Funcionamiento

1. **Creación automática de backups**:
   - Cada **1 hora**, se genera un respaldo del mundo y la carpeta `tshock`.
   - Los backups se almacenan en una carpeta específica para su gestión.

2. **Gestión de backups**:
   - Se mantiene un límite de **75 backups activos**.
   - Cuando se alcanza el límite, los backups más antiguos son eliminados y su registro se guarda en un archivo `.log`.

3. **Instalación de backups**:
   - Se puede instalar un backup anterior mediante comandos.
   - **Nota:** La instalación del backup es responsabilidad del usuario, y el plugin **no verifica la compatibilidad o integridad del proceso**.

## Comandos

| Comando | Descripción |
|---------|------------|
| **`/backup list`** | Muestra la lista de backups disponibles. |
| **`/backup create`** | Genera un backup manualmente en lugar de esperar el ciclo automático. |
| **`/backup install [id]`** | Instala un backup específico usando su ID. |

**Permiso:** `backup.manage`

## Instalación y Configuración
1. Descarga el archivo **EasyAutoBackup.dll** desde la sección de releases.
2. Coloca el archivo en la carpeta `ServerPlugins` de TShock.
3. Reinicia el servidor para activar el plugin.
4. Puedes verificar y gestionar backups con `/backup list`.

## Seguridad y Administración
- Es recomendable revisar los backups periódicamente para asegurarse de que se están generando correctamente.
- Los administradores pueden eliminar backups manualmente si es necesario.
- **Importante:** La instalación de backups podría sobrescribir datos, por lo que se recomienda hacer pruebas antes de restaurar.

## Soporte
Si tienes dudas o problemas, puedes contactar a **FrankV22**. ¡Espero que este sistema facilite la gestión de backups en tu servidor! 🚀
