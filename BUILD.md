# Build

Building the plugin for publishing follows the steps outline in the [official documentation](https://code.visualstudio.com/api/working-with-extensions/publishing-extension).

```powershell
cd vscode-unreal-angelscript
npm install -g '@vscode/vsce'
npm install
vsce package
```

After packaging, you can create a release by using the github CLI:
```powershell
cd vscode-unreal-angelscript
$packageJson = Get-Content .\package.json -Raw | ConvertFrom-Json
gh release create "$($packageJson.version)" "unreal-angelscript-$($packageJson.version).vsix"
```