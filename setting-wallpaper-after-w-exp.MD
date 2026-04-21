1. Delete cached wallpaper

    C:\Users\Admin\AppData\Roaming\Microsoft\Windows\Themes

  Delete these files if present:
  - TranscodedWallpaper
  - CachedFiles (folder — delete entire folder)

2. Reset theme to default

    start %windir%\Resources\Themes\aero.theme

 👉 This forces Windows to reload its theme engine (important step)

3. Now apply wallpaper via PowerShell (direct)
   Open CMD and run:

       powershell -command "Add-Type -AssemblyName presentationframework;[System.Windows.MessageBox]::Show('Applying Wallpaper')"

   (Just to initialize PowerShell properly)\
   Then run:

      powershell -command "(Add-Type '[DllImport(\"user32.dll\")]public static extern int SystemParametersInfo(int uAction,int uParam,string lpvParam,int fuWinIni);' -Name a -Pas)::SystemParametersInfo(20,0,'C:\Users\Admin\Downloads\dan-freeman-wAn4RfmXtxU-unsplash.jpg',3)"
