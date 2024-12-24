# Stealth_USB_Recon_Tool_Mark_2

### **Description**  
This project is a stealthy program designed to collect system and network information from a Windows machine without raising suspicion. It operates without displaying any visible windows or requiring user interaction. The gathered information is stored in a hidden file on the USB drive. The concept can be implemented in **C**, **C++**, or **C#**, offering flexibility for developers.  

---

### **How It Works**  
1. **Execution**:  
   - The program is run from a USB drive.  
   - It automatically collects system and network information using PowerShell commands.  

2. **Stealth Mode**:  
   - The program runs in the background with no visible interface or prompts.  
   - It uses a hidden PowerShell process to execute commands silently.  

3. **Data Storage**:  
   - The information is saved in a hidden text file (`ipconfig_output.txt`) in a directory named `Green_good_file` on the USB drive.  
   - The file is hidden using the `attrib +h +r +s` command.  

4. **Windows-Only**:  
   - The tool is specifically designed for Windows and leverages native system commands.  

5. **Alternative Implementations**:  
   - This functionality can also be implemented in **C++** or **C#**, which offer similar capabilities for process management and file handling.  

### **Code Explanation**  

1. **PowerShell Command**:  
   - Collects system information using `systeminfo` and network details using `ipconfig`.  
   - Saves the data in `E:\\Green_good_file\\ipconfig_output.txt`.  
   - Hides the file using `attrib +h +r +s`.  

2. **Hidden Execution**:  
   - The `STARTUPINFO` structure sets `si.wShowWindow` to `SW_HIDE`, ensuring no PowerShell window appears during execution.  

3. **Privilege Escalation**:  
   - `ShellExecute` runs PowerShell with elevated privileges (`runas`) to ensure the commands execute successfully.  

4. **Error Handling**:  
   - If the process fails to start with admin rights, the error code is displayed for debugging.  

---

### **Key Features**  
- **Fully Stealth**: Executes silently in the background without user interaction.  
- **Portability**: Works directly from a USB drive, requiring no installation.  
- **Windows Compatibility**: Leverages Windows PowerShell and command-line tools.  
- **Language Flexibility**: Can be implemented in **C**, **C++**, or **C#**.  

---

### **Setup and Usage**  
1. **Deploy**: Copy the compiled executable to a USB drive.  
2. **Run**: Clicking the executable on a Windows machine automatically gathers system and network data.  
3. **Data Retrieval**: The hidden text file containing the information is stored in the `Green_good_file` directory on the USB drive.  

---

### **Ethical Note**  
This tool is intended for authorized and ethical use only. Ensure you have explicit permission before deploying it on any system. Unauthorized use may violate laws and ethical guidelines.  
