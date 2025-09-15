# 🐧 Essential Linux Commands Cheat Sheet

## 📁 File & Directory Management

1. **ls** – List files and directories  
2. **ls -l** – List files with detailed information  
3. **pwd** – Print working directory  
4. **cd** – Change directory  
5. **mkdir** – Create a new directory  
6. **rmdir** – Remove an empty directory  
7. **touch** – Create an empty file  
8. **cp** – Copy file/directory (not contents)  
9. **cp -r** – Recursively copy directory and its contents  
10. **mv** – Move or rename a file  
11. **rm** – Remove a file  

## 📄 File Viewing

12. **cat** – View contents of a file  
13. **less** – View file contents one page at a time  
14. **head** – Show first 10 lines of a file (default)  
15. **head -5** – Show first 5 lines of a file  
16. **tail** – Show last 10 lines of a file (default)  
17. **tail -5** – Show last 5 lines of a file  
18. **head -5 filename | tail -1** – Show the 5th line of a file  

## 🔐 Permissions

19. **chmod** – Change file permissions  
20. **chmod -R 755 folder_name** – Change permissions recursively for a folder  

## ⚙️ Process Management

21. **ps -aux** – Show all running processes  
22. **ps -aux | grep name** – Filter running processes by name  
23. **top** – Real-time view of system processes  
24. **kill PID** – Kill a process by its PID  
25. **ps -p PID** – Check if a process is running or terminated  

## 🌐 Networking

26. **ping** – Check network connectivity  
27. **ifconfig** – Show network interface details  
28. **ip addr** – Show actual network interface names  

## 📥 Downloading & Archiving

29. **wget** – Download files from the internet  
30. **gzip** – Compress a file  
31. **gunzip** – Decompress a `.gz` file  
32. **zip** – Archive multiple files/folders  
33. **zip -r myarchive.zip myfolder/** – Zip a directory recursively  
34. **unzip** – Extract files from a zip archive  

## 👤 User Info

35. **whoami** – Show current user  
36. **id** – Show user and group IDs  
37. **who** – Show logged-in users

