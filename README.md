# scoop-bucket

- raycast.json
  - Scoop bucket for [Raycast for Windows](https://www.raycast.com/windows).

## Usage

```powershell
scoop bucket add raycast https://github.com/himihiromu/scoop-bucket
scoop install <package_name>
```

## Notes

- Raycast
  - Raycast is distributed via the Microsoft Store. This manifest downloads the Store stub installer (exe) and runs it.
  - The installer may show a UAC prompt.
  - The stub installer's hash may change between downloads. If hash check fails, use `scoop install raycast -s` to skip verification.
  - Official install methods: [Microsoft Store](https://apps.microsoft.com/detail/9PFXXSHC64H3) or `winget install raycast`.

## Updating the manifest

- Raycast

  1. Check the latest version at https://www.raycast.com/changelog/windows
  2. Update `version` in `raycast.json`.
  3. Download the installer and compute the SHA256 hash:
     ```powershell
     Invoke-WebRequest -Uri "https://get.microsoft.com/installer/download/9PFXXSHC64H3" -OutFile "RaycastInstaller.exe"
     (Get-FileHash -Algorithm SHA256 .\RaycastInstaller.exe).Hash.ToLower()
     ```
  4. Update `hash` in `raycast.json`.
