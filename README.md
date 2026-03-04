```powershell
This project consisted of building a complete virtualization environment using Hyper‑V by creating and configuring a main virtual machine (TP6), then integrating nested virtualization, storage management, internal networking, and multiple checkpoints to replicate the real tasks performed by a system administrator in a professional environment.
```
<img width="950" height="309" alt="image" src="https://github.com/user-attachments/assets/990de4e5-0701-420e-b5ad-601e05aacde6" />



1. Create the VM named TP6 with the following configuration
```powershell
Right‑click on the server, then:
```
<img width="632" height="289" alt="image" src="https://github.com/user-attachments/assets/f4137103-3a7c-4e25-b88c-e835e0911a10" />

<img width="605" height="456" alt="image" src="https://github.com/user-attachments/assets/0dae98d4-11a4-4194-85db-2724401772f7" />

The screenshot shows a summary confirming all the parameters configured for the TP6 virtual machine: name, Generation 2, 6 GB of memory, a 40 GB virtual disk stored in C:\VMs\TP6, no network connection, and installation of the system from the Windows Server 2022 ISO. You simply need to click Finish to complete the creation of the virtual machine.

```powershell
To enable the creation of standard checkpoints with file storage in C:\VMs\TP6,
 right‑click on the TP6 virtual machine and then select the corresponding option.
```
<img width="529" height="373" alt="image" src="https://github.com/user-attachments/assets/11659caf-11bf-40ef-8d9c-2dfe40a28bcc" />
<img width="757" height="374" alt="image" src="https://github.com/user-attachments/assets/7ad49189-c766-407e-a08f-5553975fbe5b" />

2. Create the checkpoint whose name is provided in Parameter1 to capture the initial configuration of your TP6 virtual machine.

   To create the checkpoint, you must first power off the VM, then right‑click on it and select the appropriate option
   <img width="1256" height="281" alt="image" src="https://github.com/user-attachments/assets/8f495fa2-d746-4bec-8b22-5fa191825b0a" />

3. Add a new empty disk to your TP6 virtual machine
   ```powershell
   To add a new disk, right‑click on the virtual machine and then follow the steps shown in the screenshots.
   ```
   <img width="1219" height="1244" alt="image" src="https://github.com/user-attachments/assets/a167db40-0c5b-4eaa-9743-916af825df14" />

   4. Initialize and format the new disk using the default settings
     ```powershell
      First, right‑click on the VM, then select “Connect” to access it and complete the configuration.
     Finally, initialize and format the disk as shown in the screenshot.
     ```
     <img width="1265" height="1324" alt="image" src="https://github.com/user-attachments/assets/4a4afa8e-804c-4258-926b-41f9c2e9c2a3" />























