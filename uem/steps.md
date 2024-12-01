# Steps
1. PXE Boot
	1. Send hardware information (for user to find and download drivers later) via automated script (cache as default for later use, can be overwritten if requested)
2. User selects device to setup
3. Create & Config WinPE image
	1. Create base WinPE image `copype [architecture] [C:\DeviceModelWinPE]` (insert arch from hardware info)
	2. Mount image `dism /Mount-Image /ImageFile:C:\DeviceModelWinPE\media\sources\boot.wim /MountDir:C:\mount` (accessible in `C:\mount`)
	3. Add drivers (from: `C:\DeviceModelDrivers`; select manually from specified dir)
	5. Add packages
		1. Network Support (Network protocols)
		2. PowerShell (Execute scripts)
		3. Disk Partitioning Util (Wipe drive)
		4. UEFI Support (Compatibility with newer hardware that only uses UEFI booting instead of BIOS)
		6. Language Packs (Multi language support)
	6. Add scripts `copy C:\scripts\setup.ps1 C:\mount\Windows\System32\`
	7. Config WinPE boot menu
		1. Modify BCD (Boot Config Data) to customize boot behavior/options/params `bcdedit /store C:\mount\Windows\System32\Config\BCD /set {default} bootmenupolicy legacy`
	8. Unmount image `dism /Unmount-Image /MountDir:C:\mount /Commit`
4. Select & Config WIM
5. Generalize WIM with Sysprep

## Future Features
- Capture, export and inject installed drivers into image as one of first PXE boot tasks (options: manual driver downloads dir; preexisting drivers on device; both)

## Questions
- Does app have to be added to system PATH to avoid constant admin prompts?
- Export as Bootable USB option

___
### **Step 2: Prototype the Basics**

Start experimenting with individual components to see how they work:

1. **Manually Build a WinPE**:
    
    - Use the Windows ADK tools to create and customize a WinPE image.
    - Add drivers, packages, and test booting on a virtual machine.
2. **Set Up a PXE Environment**:
    
    - Install and configure a PXE server.
    - Serve a WinPE image to a PXE-bootable client (physical or virtual).
3. **Run PowerShell Commands**:
    
    - Write and test basic PowerShell scripts for tasks like setting network configurations or partitioning drives.
    - Use Rust or C++ to invoke these scripts programmatically.

---

### **Step 3: Start Small Development**

Focus on building the minimum viable product (MVP):

1. **Frontend (Kotlin)**:
    
    - Create a simple GUI in Jetpack Compose Desktop for user input (e.g., selecting drivers or setting options for WinPE).
    - Use buttons to trigger actions like “Build WinPE” or “Deploy Image.”
2. **Backend Integration (Rust)**:
    
    - Write backend services in Rust for:
        
        - Executing DISM commands.
        - Managing PowerShell scripts.
        - Parsing configuration files.
    - Use HTTP or REST APIs to connect the Kotlin frontend to Rust backend.
        
3. **First Automation**:
    
    - Automate a single end-to-end task like building a WinPE with specific drivers and making it PXE-bootable.

---

### **Step 4: Refine and Expand**

1. **Expand Functionality**:
    
    - Add support for Sysprep.
    - Automate the creation of answer files from GUI inputs.
    - Include monitoring of PXE deployments in real time.
2. **Optimize Communication**:
    
    - Fine-tune how your frontend and backend communicate.
    - Implement logging and error handling for better debugging.
3. **Test Scalability**:
    
    - Test your app with multiple devices in a virtual environment.
    - Simulate large-scale deployments to ensure your app scales.

---

### **Step 5: Add Advanced Features**

1. **Template Management**:
    
    - Allow users to save and reuse deployment templates.
    - Implement caching for commonly used drivers or settings.
2. **Driver Management**:
    
    - Automate driver collection and injection based on detected hardware.
3. **Monitoring and Reporting**:
    
    - Build a monitoring dashboard to display deployment progress.
    - Add logs and notifications for completed tasks.