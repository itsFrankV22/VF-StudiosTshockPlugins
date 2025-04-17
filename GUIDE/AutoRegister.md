# AutoRegister

> [!NOTE]
> If you speak English please visit [AutoRegisterEN](./GUIDE/AutoRegister_En.md)

## Descripción
**AutoRegister** es un sistema que automatiza el proceso de registro de jugadores en TShock. Cuando un jugador nuevo se une al servidor, su cuenta se crea automáticamente y se le asigna una contraseña. Si el servidor tiene activado el inicio con UUID, la cuenta se vincula al UUID del jugador.

## Funcionamiento

1. **Registro automático**:  
   - Si el jugador es nuevo y su nombre no está registrado, se genera una cuenta automáticamente.
   - Se le asigna una contraseña aleatoria y se le informa a través del chat privado.
   - Si el servidor tiene inicios con UUID habilitados, el jugador será registrado con su UUID en lugar de solo su nombre.

2. **Inicio con UUID**:  
   - Si el servidor tiene activado el inicio con UUID, el jugador podrá entrar sin necesidad de usar `/login`, ya que su cuenta estará vinculada a su UUID.
   - Si la opción no está activada, el jugador deberá iniciar sesión con `/login <Usuario> <Contraseña>` en futuras conexiones.

3. **Casos especiales**:  
   - Si un jugador con el mismo nombre ya está registrado, **no se creará una nueva cuenta**.
   - En lugar de registrarse automáticamente, se le notificará que la cuenta ya existe y deberá usar `/login` para acceder.

## Instalación y Configuración
1. Descarga el archivo **AutoRegister.dll** desde la sección de releases.
2. Coloca el archivo en la carpeta `ServerPlugins` de TShock.
3. Reinicia el servidor para activar el plugin.
4. Si deseas habilitar el inicio con UUID, asegúrate de configurar `EnableUUIDLogin = true` en `TShock.Config.json`.

## Seguridad y Administración
- Es recomendable que los jugadores **guarden su contraseña** en un lugar seguro.
- Los administradores pueden gestionar cuentas manualmente con comandos de TShock.
- Si un jugador pierde su contraseña, un administrador puede usar `/user password <Usuario> <NuevaContraseña>` para restablecerla.

## Soporte
Si tienes dudas o problemas, puedes contactar a **FrankV22**. ¡Espero que este sistema facilite la administración de jugadores en tu servidor! 🚀
