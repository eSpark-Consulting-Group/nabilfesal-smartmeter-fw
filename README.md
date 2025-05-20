# MSM Smart Meter Firmware Development
#### Client Name: Nabil Fesal
#### Firm Name: Ein Technology Labs

## Flashing Instructions
### Credentials
admin - waqar@esparkconsultants.com
password - Creo0210332/*-

### Thingsboard login link for Admin access:
https://thingsboard.cloud/home

### How to connect device to ThingsBoard
1. Set a UID for it when first time setting up the device this will appear

2. And input the user and password in the MQTT factory and admin details (i.e. Dashboard 1 and Dashboard 2 access)
3. Goto Thingsboard and Add Device > Manage credentials > Input username password
4. Goto Dashboard > Create copy of Dashboard 1 > Label it unique like "Developer Dashboard -1" (this is to view the real time readings from the device with all the columns defined by our customer)
5. And after that create Dashboard 2 for the UID device, follow the same naming convention so easy for you to access it
6. See all the screenshots attached
![image](https://github.com/user-attachments/assets/08d55b9c-67d8-4dc2-926a-221d34d92bbf)
![image](https://github.com/user-attachments/assets/82b5c7a9-5082-44b0-8f51-93d76b2a7d28)
![image](https://github.com/user-attachments/assets/391b86e8-75c9-4837-aaac-853d3f283d9c)
![image](https://github.com/user-attachments/assets/b95bf1b9-490c-46f0-a146-286898e2311a)
![image](https://github.com/user-attachments/assets/5868b4cd-4818-49a9-b867-ca5b7b89c7e3)
![image](https://github.com/user-attachments/assets/172123d4-9c5d-4069-9ff2-3684bbaf231c)

**Note: For testing purposes you can use any combination to create UID. Just make sure you use the same in thingsboard etc.**
But for production UID is to follow the format below:
---------------------
UID
---------------------
<3 letter: vendor ID><1 number: type of asset><7 number: ID running number>
Vendor ID
- IND: Indkom

Type of Asset
- 0: OFP
- 1: CSU / LVDB
- 2-9: Reserve

Example (1):
IND00000001
- vendor: Indkom
- type: OFP
- ID: 0000001

Example (2):
IND10000001
- vendor: Indkom
- type: CSU
- ID: 0000001




