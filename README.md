# ![](./doc/img/regedit.png) windows-registry
Just some useful Registry Stuff.
For general Information about the Windows Registry see e.g. [Wikipedia](https://en.wikipedia.org/wiki/Windows_Registry).

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
