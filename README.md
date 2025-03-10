# MSM Smart Meter Firmware Development
#### Client Name: Nabil Fesal
#### Firm Name: Ein Technology Labs

## Flashing Instructions
### Credentials
#### Passwords
1. admin12345678  (admin) - working
2. admin@441322@ (factory) - working
3. admin@888@  (factory)
4. IESB24 (factory)

### Thingsboard activation link for Admin access:
https://thingsboard.cloud/api/noauth/activate?activateToken=cw1SWGwyK_XTECwcFvxPzOgyQMnWDgCkzLayzq9S

### How to connect device to ThingsBoard
1. Flash the [ATSAM image](https://github.com/eSpark-Consultants/nabilfesal-smartmeter-fw/tree/main/Binaries/Extracted/ATSAMD20G17) using jlink commander.
2. Flash the [V3S image](https://github.com/eSpark-Consultants/nabilfesal-smartmeter-fw/tree/main/Binaries/Extracted/V3S) to SD card using Rufus and plug it into the board.
3. Set a UID when the device is first powered up. Make sure to create a unique UID which is not a taken by any device in the cloud.
4. Enter admin password and login to the device.
5. Tap on 'i' symbol. Then again tap on 'i' symbol and login with admin password.
6. Go to MQTT and set these details.
   a. Broker IP: `thingsboard.cloud`
   b. Broker Port: `1883`
   c. Interval: `60`
   d. Username: `INDKOM`
   e. Password: `IND10`
   f. Topic: `v1/devices/me/telemetry`
8. Repeat from step 5 and login from factory details. Goto system and then Mqtt and set all details from point 6 except username set to `INDKOMF`.
9. Goto Thingsboard and Entities > Devices > Add Device.
10. Set the name and label to device uid assigned in point 3. 
11. Click on the created device then manage credentials and set these details.
    a. Client ID: {UID} or {UID}-2
    b. Username: Assigned to device in previous steps
    c. Password: Assigned to device in previous steps
13. Repeat steps from step 9 for factory device. Add -2 in name and label.
14. Goto Dashboard > Create copy of Dashboard 1 (Export and Import the dashboard) > Label it unique like "Developer Dashboard -1" (this is to view the real time readings from the device with all the columns defined by our customer)
15. And after that create Dashboard 2 for the UID device, follow the same naming convention so easy for you to access it
16. See all the screenshots attached
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




