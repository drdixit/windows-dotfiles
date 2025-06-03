# Nerd Fonts
Grab The latest release [JetBrainsMono.zip](https://github.com/ryanoasis/nerd-fonts/releases/)<br>
unzip and install it.<br>
**`NOTE:`** Don't install it through select all and right click to install. This sometimes gives me error like fonts don't missing in windows terminal etc.<br><br>
By Far Down There is the best method to install fonts on windows 11 ~<br>
`Settings > Personalization > Fonts > you find install section drag and drop all the content in zip file accept README.md and OFL.txt`

# WezTerm Symbolic Links
**`NOTE:`** Dont Forget to change the name and location
```powershell
New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\.wezterm.lua" -Target "C:\Users\user\windows-dotfiles\.wezterm.lua"
```
sometimes it requires admin rights<br><br>
someother referances<br>
Command Prompt
```cmd
mklink "%USERPROFILE%\.wezterm.lua" "C:\path\to\your\dotfiles\wezterm.lua"
```
PowerShell
```powershell
New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\.wezterm.lua" -Target "C:\path\to\your\dotfiles\wezterm.lua"
```
#### There is also thing called hard links but i dont like it
Not Recommended
```powershell
# Create hard link (no admin rights needed)
New-Item -ItemType HardLink -Path "$env:USERPROFILE\.wezterm.lua" -Target "C:\dotfiles\wezterm.lua"
```
| Feature                       | Hard Link                               | Symbolic Link (Symlink)              |
| ----------------------------- | --------------------------------------- | ------------------------------------ |
| **Points to**                 | Actual file data on disk                | Path to another file or directory    |
| **Works across drives?**      | ❌ No                                    | ✅ Yes                                |
| **Works for directories?**    | ❌ No (files only)                       | ✅ Yes (files and directories)        |
| **Breaks if target deleted?** | ❌ No (data still accessible)            | ✅ Yes (link becomes broken)          |
| **Created with**              | `fsutil hardlink create` or `mklink /H` | `mklink` (files), `mklink /D` (dirs) |
| **NTFS required?**            | ✅ Yes                                   | ✅ Yes                                |
| **Counts as separate file?**  | ❌ No (shares same inode/data)           | ✅ Yes (new file pointing to another) |
| **Permissions needed**        | Standard                                | Admin or Developer Mode required     |
