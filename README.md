
**This project consisted of building a complete virtualization environment using Hyper‑V by creating and configuring a main virtual machine (TP6), then integrating nested virtualization, storage management, internal networking, and multiple checkpoints to replicate the real tasks performed by a system administrator in a professional environment.**

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

   <img width="1125" height="320" alt="image" src="https://github.com/user-attachments/assets/5dc67803-e415-4c20-baf3-189465d90b02" />

 <img width="1173" height="299" alt="image" src="https://github.com/user-attachments/assets/bf5e03ea-0608-4dbc-9371-2f068686d486" />

<img width="1096" height="791" alt="image" src="https://github.com/user-attachments/assets/588b413d-7b88-4a94-b703-31fd9d1b1beb" />

5. creating a file on the new disk TP6
   <img width="1035" height="362" alt="image" src="https://github.com/user-attachments/assets/3bf1df4a-ca4c-445a-8dfa-f8c6ec3d924e" />

6. create the checkpoint to capture the addition and use of the new virtual disk.
   <img width="946" height="365" alt="image" src="https://github.com/user-attachments/assets/7ef23b4f-fe05-4a68-845b-9902131819e5" />
```powershell
For this step, I turn off the TP6 virtual machine, then in Hyper‑V Manager I right‑clicked on the VM and selected “Checkpoint” to generate a snapshot.
 Once the checkpoint was created, I simply renamed it CheckPoint2_06 to match the parameters required for the assignment.
```
7. Perform the required steps to create the STP6 nested virtual machine inside TP6, configured with 1GB of RAM and a 5GB virtual hard disk.
   
```powershell
   On the host machine, follow the required steps (see screenshot) to allow TP6 to enable Hyper‑V and support nested virtualization.
```
<img width="1275" height="366" alt="image" src="https://github.com/user-attachments/assets/57ab714f-43ef-4e52-ad97-9ec1650e7702" />

then on the VM TP6 we will do:
<img width="1270" height="1349" alt="image" src="https://github.com/user-attachments/assets/e63872c8-3d72-439f-af48-59c374bf9199" />

<img width="859" height="369" alt="image" src="https://github.com/user-attachments/assets/3521dd06-d918-4ccc-b56b-2e2ae3b16149" />
This screenshot shows the final screen of the virtual machine creation wizard for STP6 in Hyper‑V. The red box displays a complete summary of the selected configuration: the VM name (STP6), the generation type (Generation 2), the assigned memory (1024 MB, or 1 GB), the network status (Not Connected), and the location of the virtual hard disk created for this machine. This screen is only used to verify that all parameters are correct before creating the VM. To finalize the creation of STP6, simply click the Finish button, indicated by the red arrow.
<img width="592" height="262" alt="image" src="https://github.com/user-attachments/assets/a84b7831-eb76-461a-9317-274470dcd805" />


8. For the TP6 virtual machine, create another checkpoint to capture the addition of the disk and the nested virtualization configuration.
<img width="956" height="340" alt="image" src="https://github.com/user-attachments/assets/510c3035-ac13-4959-b572-78f662d14644" />


The screenshot shows the creation of the CheckPoint3_06 checkpoint, which appears as a new branch under CheckPoint2_06 in Hyper‑V Manager. This checkpoint plays an important role: it records the complete state of the TP6 virtual machine after enabling nested virtualization and creating the STP6 nested VM. It serves as a safe restore point, allowing you to return to this fully configured environment without repeating the complex steps involved in installing Hyper‑V inside TP6 and generating the nested virtual machine. In other words, CheckPoint3_06 captures and preserves the system state prepared for nested virtualization, as required in part 8 of the assignment.

9. Starting from the checkpoint created in step 6, connect your TP6 virtual machine to an Internal‑type virtual switch.

    On the host machine, right‑click on the server, then proceed as shown in the screenshot.
   <img width="1251" height="907" alt="image" src="https://github.com/user-attachments/assets/05a5eb3e-1760-4ab6-a429-ccfb66508add" />

10. Create another checkpoint to capture the addition of the disk and the network connection.

    <img width="836" height="371" alt="image" src="https://github.com/user-attachments/assets/4a8a658c-5279-4a90-a1ba-22df86534abc" />

This screenshot displays the complete hierarchy of checkpoints for the TP6 virtual machine in Hyper‑V. The first checkpoint, CheckPoint1_06, captures the initial state of the VM right after its creation. The second, CheckPoint2_06, records the state of the system after adding the 1 GB disk, initializing and formatting it (drive J:, label TP6_06), and creating the file file_06.txt. From this point, the VM evolves along two separate paths: CheckPoint3_06, which reflects the nested virtualization setup (installation of Hyper‑V inside TP6 and creation of the nested VM STP6), and CheckPoint4_06, which represents the network configuration step where TP6 is connected to an Internal virtual switch.


**Concluison:**

 Through the completion of this TP6, I learned how to build a fully functional virtualized environment, automate certain system administration tasks, and gain a deeper understanding of how virtual infrastructures operate. This work provides a strong foundation for managing, troubleshooting, and optimizing Hyper‑V environments in a professional setting.

 





























