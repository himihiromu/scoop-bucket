# scoop-raycast

Scoop bucket for [Raycast for Windows](https://www.raycast.com/windows).

## Usage

```powershell
scoop bucket add raycast https://github.com/<your-username>/scoop-raycast
scoop install raycast
```

## Notes

- Raycast is distributed as an MSIX package. This manifest uses `Add-AppxPackage` for installation.
- An elevated terminal may be required.
- Official install methods: [Microsoft Store](https://ray.so/download-windows) or `winget install raycast`.

## Updating the manifest

1. Check the latest version at https://www.raycast.com/changelog/windows
2. Download the new MSIX and compute the SHA256 hash:
   ```powershell
   (Get-FileHash -Algorithm SHA256 .\Raycast.Package_<version>_<hash>_x64.msix).Hash.ToLower()
   ```
3. Update `version`, `url`, and `hash` in `raycast.json`.
