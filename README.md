# FortiGate_VM
How to build your own FortiGate Firewall Lab on Virtual Box


Requirements: 
    - Free Account on Support Fortinet
    - Virtual Box
    - QEMU Emulator or any virtual image converter 

Steps: 
  1) Login (https://customersso1.fortinet.com/)
  2) <img width="1055" height="540" alt="1" src="https://github.com/user-attachments/assets/5766fa8a-a747-481b-8bde-a65104414fe1" />
  3) <img width="1056" height="413" alt="2" src="https://github.com/user-attachments/assets/02db769f-7cbb-4eb9-a46b-8116e5d8bde3" />
  4) Extract the .KVM FortiGate image into a desired path let's call it "C:\FFG_PATH"
  5) Make sure QEMU's path is in your 'System Environment Variables' (If you will use another converter to convert from .KVM to .VDI skip this)
  6) Use this command to convert the image "qemu-img convert -p -f qcow2 -O vdi fortios.qcow2 fortios.vdi"
  7) 
 
  
