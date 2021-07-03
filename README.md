# ![](./doc/img/regedit.png) windows-registry
Just some useful Registry Stuff.
For general Information about the Windows Registry see e.g. [Wikipedia](https://en.wikipedia.org/wiki/Windows_Registry).

You may also be interested in my [windows-config Repository](https://github.com/EnnoxHD/windows-config).

---

## Disclaimer
>THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

For more Information see [License](./LICENSE).

---

## 1. Show Seconds in System Clock
### Effect
| Before | After |
|--------|-------|
|![17:59](./doc/img/showsecondsinsystemclock/oldclock.png)|![18:01:43](./doc/img/showsecondsinsystemclock/newclock.png)|

### Registry Value
```
  Key: HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced
Value: ShowSecondsInSystemClock
 Type: DWORD
 Data: 0x00000001
```

### \*.reg Files
**Enable:** [ShowSecondsInSystemClock_Enable.reg](./src/showsecondsinsystemclock/ShowSecondsInSystemClock_Enable.reg)

**Disable (Windows default):** [ShowSecondsInSystemClock_Disable.reg](./src/showsecondsinsystemclock/ShowSecondsInSystemClock_Disable.reg)

### Required Action
- [ ] **Reopen or refresh**
- [x] **Log off**
- [ ] **Restart**

---

## 2. Real Time is universal
### Effect
Configures Windows to use [UTC](https://en.wikipedia.org/wiki/Coordinated_Universal_Time) instead of Local Time for [RTC](https://en.wikipedia.org/wiki/Real-time_clock).
This is especially useful for Dual-Boot Systems with Windows and Linux.
See [Archlinux Wiki](https://wiki.archlinux.org/index.php/System_time#UTC_in_Windows) for more Information.

| Before | After |
|--------|-------|
|![20:00:00](./doc/img/realtimeisuniversal/oldtime.png)|![22:00:00](./doc/img/realtimeisuniversal/newtime.png)|

### Registry Value
```
  Key: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation
Value: RealTimeIsUniversal
 Type: DWORD
 Data: 0x00000001
```

### \*.reg Files
**Enable:** [RealTimeIsUniversal_Enable.reg](./src/realtimeisuniversal/RealTimeIsUniversal_Enable.reg)

**Disable (Windows default):** [RealTimeIsUniversal_Disable.reg](./src/realtimeisuniversal/RealTimeIsUniversal_Disable.reg)

### Required Action
- [ ] **Reopen or refresh**
- [ ] **Log off**
- [x] **Restart**

---

## 3. User Folders
### Effect
Removes User Folders from 'This PC' View and Tree in the File Explorer.
The Folders are still available through the User Folder itself.
See [Wikipedia](https://en.wikipedia.org/wiki/File_Explorer) for more Information.

| Before | After |
|--------|-------|
|![](./doc/img/userfolders/3dobjects.png) 3D Objects| removed from 'This PC' View and Tree |
|![](./doc/img/userfolders/desktop.png) Desktop | removed from 'This PC' View and Tree |
|![](./doc/img/userfolders/documents.png) Documents | removed from 'This PC' View and Tree |
|![](./doc/img/userfolders/downloads.png) Downloads | removed from 'This PC' View and Tree |
|![](./doc/img/userfolders/music.png) Music | removed from 'This PC' View and Tree |
|![](./doc/img/userfolders/pictures.png) Pictures | removed from 'This PC' View and Tree |
|![](./doc/img/userfolders/videos.png) Videos | removed from 'This PC' View and Tree |

### Registry Keys
```
3D Objects:
-----------
Key: -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{0DB7E03F-FC29-4DC6-9020-FF41B59E513A}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{0DB7E03F-FC29-4DC6-9020-FF41B59E513A}
```
```
Desktop:
--------
Key: -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}
```
```
Documents:
----------
Key: -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{A8CDFF1C-4878-43be-B5FD-F8091C1C60D0}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{d3162b92-9365-467a-956b-92703aca08af}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{A8CDFF1C-4878-43be-B5FD-F8091C1C60D0}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{d3162b92-9365-467a-956b-92703aca08af}
```
```
Downloads:
----------
Key: -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{374DE290-123F-4565-9164-39C4925E467B}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{088e3905-0323-4b02-9826-5d99428e115f}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{374DE290-123F-4565-9164-39C4925E467B}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{088e3905-0323-4b02-9826-5d99428e115f}
```
```
Music:
------
Key: -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{1CF1260C-4DD0-4ebb-811F-33C572699FDE}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{3dfdf296-dbec-4fb4-81d1-6a3438bcf4de}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{1CF1260C-4DD0-4ebb-811F-33C572699FDE}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{3dfdf296-dbec-4fb4-81d1-6a3438bcf4de}
```
```
Pictures:
---------
Key: -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{3ADD1653-EB32-4cb0-BBD7-DFA0ABB5ACCA}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{24ad3ad4-a569-4530-98e1-ab02f9417aa8}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{3ADD1653-EB32-4cb0-BBD7-DFA0ABB5ACCA}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{24ad3ad4-a569-4530-98e1-ab02f9417aa8}
```
```
Videos:
-------
Key: -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{A0953C92-50DC-43bf-BE83-3742FED03C9C}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{f86fa3ab-70d2-4fc7-9c99-fcbf05467f3a}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{A0953C92-50DC-43bf-BE83-3742FED03C9C}
     -HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{f86fa3ab-70d2-4fc7-9c99-fcbf05467f3a}
```

### \*.reg Files
| Folder | Enable | Disable (Windows default) |
|--------|--------|---------|
|![](./doc/img/userfolders/3dobjects.png) 3D Objects| [Remove3DObjects_Enable.reg](./src/userfolders/Remove3DObjects_Enable.reg) | [Remove3DObjects_Disable.reg](./src/userfolders/Remove3DObjects_Disable.reg) |
|![](./doc/img/userfolders/desktop.png) Desktop | [RemoveDesktop_Enable.reg](./src/userfolders/RemoveDesktop_Enable.reg) | [RemoveDesktop_Disable.reg](./src/userfolders/RemoveDesktop_Disable.reg) |
|![](./doc/img/userfolders/documents.png) Documents | [RemoveDocuments_Enable.reg](./src/userfolders/RemoveDocuments_Enable.reg) | [RemoveDocuments_Disable.reg](./src/userfolders/RemoveDocuments_Disable.reg) |
|![](./doc/img/userfolders/downloads.png) Downloads | [RemoveDownloads_Enable.reg](./src/userfolders/RemoveDownloads_Enable.reg) | [RemoveDownloads_Disable.reg](./src/userfolders/RemoveDownloads_Disable.reg) |
|![](./doc/img/userfolders/music.png) Music | [RemoveMusic_Enable.reg](./src/userfolders/RemoveMusic_Enable.reg) | [RemoveMusic_Disable.reg](./src/userfolders/RemoveMusic_Disable.reg) |
|![](./doc/img/userfolders/pictures.png) Pictures | [RemovePictures_Enable.reg](./src/userfolders/RemovePictures_Enable.reg) | [RemovePictures_Disable.reg](./src/userfolders/RemovePictures_Disable.reg) |
|![](./doc/img/userfolders/videos.png) Videos | [RemoveVideos_Enable.reg](./src/userfolders/RemoveVideos_Enable.reg) | [RemoveVideos_Disable.reg](./src/userfolders/RemoveVideos_Disable.reg) |
|![](./doc/img/userfolders/folder.png) **All Folders** | [RemoveAllFolders_Enable.reg](./src/userfolders/RemoveAllFolders_Enable.reg) | [RemoveAllFolders_Disable.reg](./src/userfolders/RemoveAllFolders_Disable.reg) |

### Required Action
- [x] **Reopen or refresh**
- [ ] **Log off**
- [ ] **Restart**

---

## 4. Enable Hex Numpad
### Effect
| Before | After |
|--------|-------|
| enter Unicode code points in decimal | ... in hexadecimal |
| (`Alt pressed` + up to 4 `Numpad` digits) | (`Alt pressed` + `+` + up to 4 `Numpad` or `{A,B,C,D,E,F}` digits) |

- An overview is available at [altcodeunicode.com](https://altcodeunicode.com/how-to-use-alt-codes/).

### Registry Value
```
  Key: HKEY_CURRENT_USER\Control Panel\Input Method
Value: EnableHexNumpad
 Type: REG_SZ
 Data: 1
```

### \*.reg Files
**Enable:** [EnableHexNumpad_Enable.reg](./src/enablehexnumpad/EnableHexNumpad_Enable.reg)

**Disable (Windows default):** [EnableHexNumpad_Disable.reg](./src/enablehexnumpad/EnableHexNumpad_Disable.reg)

### Required Action
- [ ] **Reopen or refresh**
- [ ] **Log off**
- [x] **Restart**

## 5. Disable Logon Background Image
### Effect
| Before | After |
|--------|-------|
| Image gets displayed at Logon | Single color background at Logon |

### Registry Value
```
  Key: HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\System
Value: DisableLogonBackgroundImage
 Type: DWORD
 Data: 0x00000001
```

### \*.reg Files
**Enable:** [DisableLogonBackgroundImage_Enable.reg](./src/disablelogonbackgroundimage/DisableLogonBackgroundImage_Enable.reg)

**Disable (Windows default):** [DisableLogonBackgroundImage_Disable.reg](./src/disablelogonbackgroundimage/DisableLogonBackgroundImage_Disable.reg)

### Required Action
- [x] **Reopen or refresh**
- [ ] **Log off**
- [ ] **Restart**

## 6. Disable Flashing Taskbar Icons
### Effect
| Before | After |
|--------|-------|
| Window icons requesting user attention flashes 7 times | No flashing icons on Taskbar |

### Registry Value
```
  Key: HKEY_CURRENT_USER\Control Panel\Desktop
Value: ForegroundFlashCount
 Type: DWORD
 Data: 0x00000000
```

### \*.reg Files
**Enable:** [ForegroundFlashCount_Enable.reg](./src/foregroundflashcount/ForegroundFlashCount_Enable.reg)

**Disable (Windows default):** [ForegroundFlashCount_Disable.reg](./src/foregroundflashcount/ForegroundFlashCount_Disable.reg)

### Required Action
- [x] **Reopen or refresh**
- [ ] **Log off**
- [ ] **Restart**

## 7. Always display new windows in the foreground
### Effect
| Before | After |
|--------|-------|
| A new window may wait 200 seconds in the background | All windows appear instantly in the foreground |

### Registry Value
```
  Key: HKEY_CURRENT_USER\Control Panel\Desktop
Value: ForegroundLockTimeout
 Type: DWORD
 Data: 0x00000000
```

### \*.reg Files
**Enable:** [ForegroundLockTimeout_Enable.reg](./src/foregroundlocktimeout/ForegroundLockTimeout_Enable.reg)

**Disable (Windows default):** [ForegroundLockTimeout_Disable.reg](./src/foregroundlocktimeout/ForegroundLockTimeout_Disable.reg)

### Required Action
- [x] **Reopen or refresh**
- [ ] **Log off**
- [ ] **Restart**

## 8. Always show Recycle Bin in Explorer Tree
### Effect
| Before | After |
|--------|-------|
| The Recycle Bin is not shown in the Explorer Tree by default. | Always shows the Recycle Bin. |

### Registry Value
```
  Key: HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID\{645FF040-5081-101B-9F08-00AA002F954E}
Value: System.IsPinnedToNameSpaceTree
 Type: DWORD
 Data: 0x00000001
```

### \*.reg Files
**Enable:** [RecycleBinInExplorerTree_Enable.reg](./src/recyclebininexplorertree/RecycleBinInExplorerTree_Enable.reg)

**Disable (Windows default):** [RecycleBinInExplorerTree_Disable.reg](./src/recyclebininexplorertree/RecycleBinInExplorerTree_Disable.reg)

### Required Action
- [x] **Reopen or refresh**
- [ ] **Log off**
- [ ] **Restart**

## 9. Context menu entries for Explorer
For custom context menu entries in the Explorer see [this post on StackOverflow](https://stackoverflow.com/a/29769228).

## 10. Windows 11 Customizations

### Restore Windows 10 Start
Registry Value:
```
  Key: HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced
Value: Start_ShowClassicMode
 Type: DWORD
 Data: 0x00000001
```

### Start left aligned
Registry Value:
```
  Key: HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced
Value: TaskbarAI
 Type: DWORD
 Data: 0x00000000 (left), 0x00000001 (center)
```

### Taskbar Size
Registry Value:
```
  Key: HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced
Value: TaskbarSi
 Type: DWORD
 Data: 0x00000000 (small), 0x00000001 (medium), 0x00000002 (large)
```

### Disable Snap Assist Flyout
Registry Value:
```
  Key: HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced
Value: EnableSnapAssistFlyout
 Type: DWORD
 Data: 0x00000000
```

### Restore Windows 10 Explorer
Registry Value:
```
  Key: HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced
Value: SeparateProcess
 Type: DWORD
 Data: 0x00000001
```
