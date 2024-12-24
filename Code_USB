#include <windows.h>
#include <stdio.h>

int main() {
    // PowerShell command to execute
    const char *command = "-Command \"systeminfo > E:\\Green_good_file\\ipconfig_output.txt; ipconfig >> E:\\Green_good_file\\ipconfig_output.txt; attrib +h +r +s /s /d E:\\Green_good_file\\ipconfig_output.txt; exit\"";

    // Create a hidden PowerShell process
    STARTUPINFO si = { sizeof(STARTUPINFO) };
    si.dwFlags = STARTF_USESHOWWINDOW;
    si.wShowWindow = SW_HIDE; // Hidden window

    PROCESS_INFORMATION pi;

    // Requesting elevated privileges to run PowerShell with Admin rights
    if (ShellExecute(NULL, "runas", "C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\powershell.exe", (LPSTR)command, NULL, SW_HIDE) <= (HINSTANCE)32) {
        // Error handling if unable to run with elevated privileges
        DWORD error = GetLastError();
        printf("Failed to execute command with elevated privileges. Error code: %lu\n", error);
        return 1;
    }

    return 0;
}
