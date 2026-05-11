please copy
"@echo off
title Network Stack Cleanup
echo ===========================================
echo Cleaning up Network Stack and DNS...
echo ===========================================

:: ล้างค่า DNS Cache
echo 1/5 Flushing DNS...
ipconfig /flushdns

:: คืนค่า IP Address (Release/Renew)
echo 2/5 Releasing IP Address...
ipconfig /release
echo 3/5 Renewing IP Address...
ipconfig /renew

:: รีเซ็ต Winsock Catalog (แก้ปัญหาการเชื่อมต่อซอฟต์แวร์)
echo 4/5 Resetting Winsock...
netsh winsock reset

:: รีเซ็ต TCP/IP Stack
echo 5/5 Resetting TCP/IP...
netsh int ip reset

echo ===========================================
echo Network Cleanup Complete!
echo It is recommended to restart your computer.
echo ===========================================
pause"
then past it on notepad save it with .bat file
