## Few Windows Powershell Commands:

### To display files present in the directory
```bash
Get-ChildItem
```

### To display files present in the directory including hidden files and folders:
```bash 
Get-ChildItem -Force
```

### To create an Item:

#### For **Folder**:
```bash
New-Item -ItemType Directory -Name "Folder_Name"
```
#### For **File**:
```bash
New-Item -ItemType File -Name "File_Name.ext"
```

### To remove an Item:

#### For **Folder**:
```bash
Remove-Item Folder_Name
```
#### For **File**:
```bash
Remove-Item File_Name.ext
```

### To forcibly remove an Item:

#### For **Folder**:
```bash
Remove-Item Folder_Name -Recurse
```
#### For **File**:
```bash
Remove-Item File_Name.ext -Recurse
```

### To edit a file:

#### In Notepad:
```bash
notepad File_Name.txt
```
#### In default app:
```bash
Invoke-Item File_Name.txt
```
#### In VSCode:
```bash
code File_Name.txt
```

