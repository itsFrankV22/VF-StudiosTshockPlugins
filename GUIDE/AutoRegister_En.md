# AutoRegister

> [!NOTE]
> Si hablas español porfa visita [AutoRegisterES](./GUIDE/AutoRegister.md)

## Description
**AutoRegister** is a system that automates the player registration process in TShock. When a new player joins the server, their account is automatically created and assigned a password. If the server has UUID login enabled, the account will be linked to the player's UUID.

## How It Works

1. **Automatic Registration**:  
   - If the player is new and their name is not registered, an account is automatically created.
   - A random password is assigned, and the player is informed via private chat.
   - If the server has UUID login enabled, the player will be registered with their UUID instead of just their name.

2. **UUID Login**:  
   - If the server has UUID login enabled, the player can log in automatically without needing to use `/login`, as their account will be linked to their UUID.
   - If the option is not enabled, the player will need to log in using `/login <Username> <Password>` in future connections.

3. **Special Cases**:  
   - If a player with the same name is already registered, **a new account will not be created**.
   - Instead of being registered automatically, they will be notified that the account already exists and must use `/login` to access it.

## Installation and Configuration
1. Download the **AutoRegister.dll** file from the releases section.
2. Place the file in the `ServerPlugins` folder of TShock.
3. Restart the server to activate the plugin.
4. If you want to enable UUID login, make sure to set `EnableUUIDLogin = true` in `TShock.Config.json`.

## Security and Administration
- It is recommended that players **keep their password** in a safe place.
- Administrators can manage accounts manually using TShock commands.
- If a player loses their password, an administrator can use `/user password <Username> <NewPassword>` to reset it.

## Support
If you have any questions or issues, you can contact **FrankV22**. I hope this system simplifies player management on your server! 🚀
