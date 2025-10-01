## **🖥️ Mini Guide: Fixing Missing ARandR Icon on Arch Linux**

### **❗ Problem**

ARandR is installed, but it does **not appear in the application menu** because the `.desktop` file points to a wrong executable or is missing.

---

### **1️⃣ Check ARandR Installation**

Open a terminal and run:

```bash
which arandr
```

* Typical path: `/usr/bin/arandr` ✅
* On some systems (like yours): `/usr/sbin/arandr` ⚠️

---

### **2️⃣ Create or Edit `.desktop` File**

1. Open a new `.desktop` file:

```bash
sudo nano /usr/share/applications/arandr.desktop
```

2. Paste the following content (adjust `Exec` if your ARandR path is different):

```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=ARandR
Comment=Screen layout editor for X
Exec=/usr/sbin/arandr
Icon=preferences-desktop-display
Terminal=false
Categories=Utility;X-Misc;
```

3. Save and exit (`Ctrl+O`, Enter, `Ctrl+X`) 💾

---

### **3️⃣ Update Desktop Database**

Run:

```bash
sudo update-desktop-database
```

---

### **4️⃣ Check the Menu**

* Open your application menu 🏠
* ARandR should now appear with the correct icon 🖼️ and launch properly ▶️
