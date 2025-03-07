### 1. Installation

- Move `vault-manager.cmd`, `start-vault-manager.cmd.vbs` files to `C:\Users\USER\AppData\Local\Programs\obsidian` (where `USER` is your username)
- Create a shortcut to `start-vault-manager.cmd.vbs` in the same directory. - **This will be your new default starting point for Obsidian.**
- Rename it to for example "obsidian-vaults". (remember to use different name than "Obsidian")
- In Properties change its icon by choosing the `Obsidian.exe`.

Now replace every old Obsidian shortcut with your new one (those shortcuts you can rename to "Obsidian").

### 2. Tip - Search launching:
When using Windows Search (or PowerToys Run) it will still point to old Obsidian shortcut.

Remove old:
- Remove `Obsidain` shortcut form `C:\ProgramData\Microsoft\Windows\Start Menu\Programs`.

Add new:
- Open `C:\Users\Tomek\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` directory and make a shortcut to `obsidian-vaults` (new Obsidian Shortcut).
- Here you can rename it to "Obsidian".

###### You can add new shortcut to original directory `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` however you need admin privileges.