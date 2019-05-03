# ![](./doc/img/regedit.png) windows-registry
Just some useful Registry Stuff.
For general Information about the Windows Registry see e.g. [Wikipedia](https://en.wikipedia.org/wiki/Windows_Registry).

---

## Disclaimer
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
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
|![](./doc/img/oldclock.png)|![](./doc/img/newclock.png)|

### Registry Value
```
  Key: HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced
Value: ShowSecondsInSystemClock
 Type: DWORD
 Data: 0x00000001
```

### \*.reg Files
**Enable:** [file coming soon]()

**Disable (Windows default):** [file coming soon]()

### Required Action
- [x] **Log off**
- [ ] **Restart**

---

## 2. Real Time is universal
### Effect
Configures Windows to use [UTC](https://en.wikipedia.org/wiki/Coordinated_Universal_Time) instead of Local Time for [RTC](https://en.wikipedia.org/wiki/Real-time_clock).
This is especially practical for Dual-Boot Systems with Windows and Linux.
See [Archlinux Wiki](https://wiki.archlinux.org/index.php/System_time#UTC_in_Windows) for more Information.

| Before | After |
|--------|-------|
|![](./doc/img/oldtime.png)|![](./doc/img/newtime.png)|

### Registry Value
```
Key: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation
Value: RealTimeIsUniversal
Type: DWORD
Data: 0x00000001
```

### \*.reg Files
**Enable:** [file coming soon]()

**Disable (Windows default):** [file coming soon]()

### Required Action
- [ ] **Log off**
- [x] **Restart**
