# Auto Generate Folder and File with content

## Steps

### 1- Get Folder Name with path

```powershell
$input_name = Read-Host "Please enter name "

$current_path = $PWD.Path

$folderName = "$input_name"
$folderPathCtrl = Join-Path $($current_path) "js" "controllers" $folderName.ToLower()
```

### 2- File Name and path

```powershell
$fileAddControllerJs = "add$($input_name)Ctrl"
$fileAddController = "$($fileAddControllerJs).js"
$fileAddControllerPath = Join-Path $($folderPathCtrl) $($fileAddController)
```

### 3- Create folder

```powershell
if (!(Test-Path $folderPathCtrl)) {
    New-Item -ItemType Directory -Path $folderPathCtrl
    Write-Host "Folder created: $folderPathCtrl"
} else {
    Write-Host "Folder already exists: $folderPathCtrl"
}
```

### 4- Create file with content

```powershell
$contentAddCtrl = "app.controller('$($fileAddControllerJs)', ['`$filter', '$($modleName)', '`$stateParams', '`$scope', 'flashService', '`$state', '`$rootScope', 'cfpLoadingBar', 'toaster',function(`$filter, $($modleName), `$stateParams, `$scope, flashService, `$state, `$rootScope, cfpLoadingBar, toaster) {}]);"

if (!(Test-Path $fileAddControllerPath)) {
    New-Item -ItemType File -Path $fileAddControllerPath
    Write-Host "File created: $fileAddControllerPath"

    Add-Content -Path $fileAddControllerPath -Value $contentAddCtrl
    Write-Host "Content added to file. $contentAddCtrl"
} else {
    Write-Host "File already exists: $fileAddControllerPath"
}
```
