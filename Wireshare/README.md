#   Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool


## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets
- First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").


- Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

  <br>
   <br>
  <p align="center">
  <img width="1329" height="587" alt="Image" src="https://github.com/user-attachments/assets/4d77d1ce-aeb6-4ffe-b7d8-528fb46dfed8" />

  </p>
  <br>
  <br>

- Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.
 <br>
   <br>
  <p align="center">
  <img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/fe34867f-be37-49ee-b73d-c87bc3f51c76" />
 </p>
  <br>
  <br>

  ### Step 2: Generate Login Traffic
  - Open a web browser and navigate to http://testphp.vulnweb.com/login.php.

- Enter any dummy credentials. For this example, we'll use:

   Username: darling

   Password: measatest143

- Click the login button. The login will fail, but the data has already been sent across the network.

 <br>
   <br>
  <p align="center">
<img width="996" height="568" alt="Image" src="https://github.com/user-attachments/assets/75ad4169-c19c-44f9-9391-63db18540570" />

 </p>
  
  
### step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

 <br>
   <br>
  <p align="center">
<img width="1919" height="517" alt="image" src="https://github.com/user-attachments/assets/24898bfb-4f11-4c3c-83aa-ac994cb3fdde" />

 </p>
  <br>
  <br>

### step 4: Inspect the Packet to Find Credentials 

- In the filtered packet list, you should see a packet with information like "POST /userinfo.php". Select this packet.

- In the Packet Details pane below the list, expand the following sections:

Hypertext Transfer Protocol

HTML Form URL Encoded

- Inside the "HTML Form URL Encoded" section, you will see the credentials you entered in plaintext.

 <br>
   <br>
  <p align="center">


  ![Image](https://github.com/user-attachments/assets/e61a5a77-ca46-47f7-9920-79d86a4b0446)


 </p>
  <br>
  <br>

---

## Result
The experiment successfully intercepts the login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network:

This result confirms the inherent security flaw of the HTTP protocol. Any sensitive data sent over HTTP is transmitted openly, making it trivial to intercept.
