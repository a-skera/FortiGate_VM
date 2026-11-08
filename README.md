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
  7) Let's assume you've copied the fresh new image 'fortios.vdi' to another path call it "C:\FFG_PATH_FOR_VBOX"
  8) Launch Virtual Box and use the configurations in the photos
  9) <img width="924" height="576" alt="9" src="https://github.com/user-attachments/assets/df95a6c6-c243-4591-afa0-bc3eb487b2d1" />
  10) <img width="1212" height="531" alt="10" src="https://github.com/user-attachments/assets/89eacd44-8f23-46da-a168-4b7c03ee5fe3" />
  11) <img width="1201" height="580" alt="11" src="https://github.com/user-attachments/assets/b86950ec-0594-42fd-9235-ed7fc76fcaef" />
  12) <img width="759" height="472" alt="12" src="https://github.com/user-attachments/assets/caa387ab-9b38-425c-945b-1cb156aead3f" /> (Boot Order)
  13) Configure the network adapter as you design your lab but for initial installation Enable Adapter 1 (NAT) and Adapter 2 (Bridged Adapter)
  14) Launch the Image (FG) then wait till everything is done
  15) Login using initial credentials username(admin) and password(  )
  16) We need two important things (Validate our free license) and (configure an interface of the machine to allow us access the login webpage of the firewall)
  
  
  17) Validate the License use command:
      
      'execute vm-license-options account-id your_email@example.com' # Replace the email with your registered Fortinet account email
      
      'execute vm-license-options account-password fake@password.com' # Replace the fake@password with your Fortinet account password'

      'execute vm-license'

       Press 'Y' to accept and launch the operation
  
   18) Let's have an overview on network interfaces use command:
       
       'get system interface physical' # Check the interface 1 - port 1 wit NAT IP and interface 2 - port 2 with 0.0.0.0 

   20) Let's configure interface 2 - port 2 in order to use the login Webpage use command:
       
        'config system interface'
       
        'edit port2'

        'set mode dhcp'

        'set defaultgw enable'

        'set allowaccess ping http https ssh'

        'next'

        'end'

   21) Wait 5 or 10 seconds then use the command:

       'get system interface physical' # to view the new ip on interface 2 - port 2

   22) On your host machine use the terminal to ping the IP
   
   23) Then use that IP on the browser to login normally
   
   24) 
       
       
   
  




 
  
