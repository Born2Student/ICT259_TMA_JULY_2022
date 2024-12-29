# ICT259 - Computer Networking

# ICT259 Tutor-Marked Assignment (TMA01) - July Semester 2022

### Question 1 (25 marks)

**Question 1(a) (4 marks)**

For the network in Figure Q1(a), discuss how network protocols and standards facilitate the transfer of data in this network by answering the following question.

If Host A sends a frame to Host B, identify the source Internet Protocol (IP), destination IP, source Media Access Control (MAC), and destination MAC addresses in the frame Host A sends to Host B.

<img width="926" alt="Screenshot 2024-12-28 at 5 32 29 PM" src="https://github.com/user-attachments/assets/8dff310a-bdb8-4b82-898d-6794e5aa0990" />

**ANS:**

According to the diagram, both Host A and Host B are connected within the same network and this is because the data link source address which is categorically managed in the layer 2 of the OSI model which is known as the data link layer is represented by the source MAC address. Meanwhile the data link destination address which also layer 2 is represented by the destination MAC address.

Therefore based on this information, the end-to end devices are the same in comparison with their point-to-point counterpart devices.

There would be no modifications to the respective layer 2 and layer 3 headers that are encapsulated in the data frame once the headers have been encapsulated at Host A.

The Ethernet header which is categorically stored in the layer 2 of the OSI model which is known as the data link layer will be encapsulated within the frame that is transmitted from Host A to Host B stores both the source MAC address of Host A which is 20.30.0.2 and the destination MAC address of Host B which is 00-11-11-44-44-44.

The Internet Protocol (IP) header which is categorically stored in the layer 3 of the OSI model which is known as the network layer will be encapsulated within the frame transmitted from Host A to Host B stores both the source IP address of Host A which is 20.30.0.2 and the destination IP address of Host B which is 20.30.0.3.

<img width="718" alt="Screenshot 2024-12-28 at 5 34 02 PM" src="https://github.com/user-attachments/assets/969ecd0e-92ca-48e1-a80e-ee8c8a15df30" />

**Question 1(b)**

<img width="623" alt="Screenshot 2024-12-28 at 5 35 09 PM" src="https://github.com/user-attachments/assets/6d3ef113-5e2e-4f71-89a3-9475e4a56705" />

Explain, in sequence, how the switch responds to each of the incoming frames based on the following series of events. For each transmission, include any entry made to the switch's MAC address table. Complete and include Table Q1(b) as part of your answer.

Assume all entries in the MAC address table will not expire during the duration of the series of events. 

Also, assume that there is sufficient memory space in the MAC address table for additional entries.

**Question 1(b)(i) (4 marks)**

PC 2 sends a frame to PC 4

**ANS:**

**Learning Process:**

Firstly, PC2 will transmit a frame to the switch. 

In the process known as learning, the switch learns that the frame was transmitted by PC2 from Fa0/2.

The switch would then identify the source MAC address stored in the frame layer 2 Ethernet header. 
 
Since the source MAC address from the frame is not stored in the switch MAC address table, the switch will therefore store the frame MAC address and its respective assigned port value which are AA-BB-CC-22-22-22 and Fa/02 into the MAC address table.

<img width="721" alt="Screenshot 2024-12-28 at 5 42 17 PM" src="https://github.com/user-attachments/assets/a920cf99-cd26-4217-b3b9-cb6f3bd471de" />

**Forwarding Process:**

As part of the forwarding process, the switch will search for the destination MAC address by searching for a possible match from within the MAC address table. 

However in the situation where a destination MAC address match cannot be found in the MAC address table, the switch would transmit the frame to all of its respective ports which are Fa0/1 and Fa0/3 excluding the incoming port Fa0/2.


**Question 1(b)(ii) (3 marks)**

PC 4 replies to PC 2

**ANS:**

**Learning Process**

Firstly, PC4 will transmit a frame to the switch. 

In the process learning, the switch learns that the frame was transmitted by PC4 from Fa0/3.

The switch would then identify the source MAC address stored in the frame layer 2 Ethernet header. 

Since the source MAC address from the frame is not stored in the switch MAC address table, subsequently the switch therefore would then store the respective frame MAC address and its respective port and in this case is port value Fa0/3 to the MAC address table.

<img width="721" alt="Screenshot 2024-12-28 at 5 43 22 PM" src="https://github.com/user-attachments/assets/8de39473-3f30-44e4-97aa-fdccafcc865b" />

**Forwarding Process:**

As part of the forwarding process, subsequently the switch would perform a search for the destination MAC address by searching for a possible destination MAC address match from within the MAC address table. In a situation where a match has been found in the MAC address table of the switch, therefore the switch would transmit the reply in the form of a frame by the port Fa0/2 to PC2.


**Question 1(b)(iii) (3 marks)**

PC 3 sends a frame to PC 2

**ANS:**

**Learning MAC Addresses**

Firstly, PC3 will transmit a frame to the switch. 

In the process of learning, the switch learns that the frame was transmitted by PC3 from Fa0/2.

The switch would then identify the source MAC address stored in the frame layer 2 Ethernet header. 

Since the source MAC address from the frame is not stored in the switch MAC address table, subsequently the switch therefore would store the frame MAC address and its respective port value and in this case is Fa0/3 to the MAC address table.

<img width="721" alt="Screenshot 2024-12-28 at 5 44 24 PM" src="https://github.com/user-attachments/assets/34aa0573-3329-489d-bf2b-16c99768a860" />

**Frames Filtering**

As part of the frame filtering process, the switch will search for the destination MAC address by searching for a possible destination MAC address match from within the MAC address table. In a situation where a match has been found in the MAC address table of the switch and incoming port being used is the exact same as the destination port, the switch would then instead filter the frame by discarding it and transmitting it to PC2 without causing any damage to PC2 as it already has received the frame. 


**Question 1(b)(iv) (3 marks)**

PC 1 sends a multicast frame

**ANS:**

**Learning MAC Addresses**

Firstly, PC1 will transmit a multicast frame to the switch. 

In the process of learning, the switch learns that the multicast frame was transmitted by PC1 from its respective port value Fa0/1.

The switch would then identify the source MAC address stored in the multicast frame layer 2 Ethernet header. 

Since the source MAC address from the multicast frame is not stored in the switch MAC address table, the switch will therefore store the frame MAC address and its respective port value and in this case is Fa0/1 to the MAC address table.

![Screenshot 2024-12-28 at 11 42 03 PM](https://github.com/user-attachments/assets/f2b0670c-e1da-442d-89df-ea555335e71d)

**Forwarding A Multicast Frame:**

As part of the forwarding process, the switch would determine whether the frame is a multicast or broadcast frame by checking its destination MAC address. Since in this situation it is a multicast frame, the switch would the transmit the multicast frame to all of its respective ports which are Fa0/2 and Fa0/3 excluding the incoming port value Fa0/1.

**Question 1(b) (8 marks)**

<img width="623" alt="Screenshot 2024-12-28 at 5 40 53 PM" src="https://github.com/user-attachments/assets/b7a02e6c-1d8e-4a44-b644-6c51a4d53298" />

**ANS:**

![Screenshot 2024-12-28 at 11 42 34 PM](https://github.com/user-attachments/assets/33fd9978-7dda-4888-a244-0f90fce182e8)


### Question 2 (27 marks)

The network topology in Figure Q2 has network address 50.0.0.0. PC1 is a member of the IT-VLAN, and PC2 is a member of the ENG-VLAN.

![Screenshot 2024-12-28 at 11 44 13 PM](https://github.com/user-attachments/assets/5e9e243c-9829-412d-a2c7-887d1088de67)

Apply an IPv4 addressing scheme using a fixed-length subnet mask to the network. Illustrate your scheme by completing the following tasks.

**Question 2(a) (4 marks)**

Copy Figure Q2 to your answer script. 

Use the shape of a rectangle to represent the PC and switch, and an oval for the router. 

Label all the devices with names either inside or beside the shaped objects. 

Indicate the following on the diagram you have drawn.

**Question 2(a)(i)**

All the networks by enclosing each with a circle

**ANS:**

![Screenshot 2024-12-28 at 11 46 53 PM](https://github.com/user-attachments/assets/9b156a21-7736-4631-abb0-e0d685f1fc86)

**Question 2(a)(ii)**

The location of the default gateway(s) by a pointing arrow with labels

**ANS:**

![Screenshot 2024-12-28 at 11 47 20 PM](https://github.com/user-attachments/assets/99f909b7-4388-4a75-a3bb-de5dd2dc62c7)

**Question 2(b) (2 marks)**

If the network administrator uses seven subnet bits, give the subnet mask in the following representations. 

Explain your answer.

**Question 2(b)(i)**

Dotted decimal notation

**ANS:**

![Screenshot 2024-12-28 at 11 50 11 PM](https://github.com/user-attachments/assets/a785c88f-31b4-4f58-9fc5-98e3d22d68ad)
![Screenshot 2024-12-28 at 11 50 24 PM](https://github.com/user-attachments/assets/3bc1d0c7-e125-4b24-b2a0-f3689c44f5e1)

**Question 2(b)(ii)**

Prefix length

**ANS:**

![Screenshot 2024-12-28 at 11 51 07 PM](https://github.com/user-attachments/assets/bc87e6f7-74cf-40dd-abcd-ae4259cc074a)

**Question 2(c) (6 marks)**

Starting from the left of Figure Q2, assign Subnet 10, Subnet 20, Subnet 30, Subnet 40, Subnet 50, Subnet 60, Subnet 70, … to all the networks you have circled in Q2(a).

Based on seven subnet bits, obtain the IP address of the first six subnets based on the subnet list given above. 

That is from Subnet 10 to Subnet 60. Show your binary working bits.

**ANS:**

![Screenshot 2024-12-28 at 11 55 58 PM](https://github.com/user-attachments/assets/9ea902e2-5f02-4c18-8071-729b4d3093cb)
![Screenshot 2024-12-28 at 11 56 12 PM](https://github.com/user-attachments/assets/8c1b66ac-7fa6-424e-899e-adbe8375f446)
![Screenshot 2024-12-28 at 11 56 25 PM](https://github.com/user-attachments/assets/1c62064c-deb1-4d42-8fb5-7cd3954c1fea)

**Question 2(d) (4 marks)**

Based on seven subnet bits, obtain the entire usable host range for Subnet 10 and Subnet 20. 

Show your working.

**ANS:**

![Screenshot 2024-12-28 at 11 57 46 PM](https://github.com/user-attachments/assets/dc94e456-2bb1-4604-9ee8-0998f5efec96)
![Screenshot 2024-12-28 at 11 57 59 PM](https://github.com/user-attachments/assets/ff1af671-6cba-4db5-8a48-c3a071dc9ed0)

**Question 2(e)**

Copy Figure Q2 to your answer script. On the diagram you have drawn, indicate the following:

**Question 2(e)(i) (2 marks)**

The interfaces of all the routers and SwitchA that you will use to set up the network

**ANS:**

![Screenshot 2024-12-29 at 12 08 16 AM](https://github.com/user-attachments/assets/13389f87-19ad-4ebd-9d31-9172bfe09393)

**Question 2(e)(ii) (9 marks)**

Based on your Q2(c) answers, assign an appropriate IP address to all the PCs, the two switches, and the routers' interfaces. 

Assign starting from the first usable host IP address of each subnet to as many host IP addresses as you need. 

Indicate the IP addresses on the diagram drawn. 

Explain your answers to the IP addresses of the two switches.

**ANS:**

![Screenshot 2024-12-29 at 12 08 40 AM](https://github.com/user-attachments/assets/c464e3d9-8ea2-4e59-aa9a-8d1cfece0fbc)
![Screenshot 2024-12-29 at 12 08 58 AM](https://github.com/user-attachments/assets/3aaf342e-37de-4842-9233-434d961aa8ad)
![Screenshot 2024-12-29 at 12 09 17 AM](https://github.com/user-attachments/assets/40508349-8f1a-41f4-bfa6-a70c30481cd4)
![Screenshot 2024-12-29 at 12 09 28 AM](https://github.com/user-attachments/assets/f4657712-1d6f-4517-9cb1-71c9b80d346a)
![Screenshot 2024-12-29 at 12 09 40 AM](https://github.com/user-attachments/assets/04997cf0-116a-4d38-bd16-36a5a05c24ec)
![Screenshot 2024-12-29 at 12 09 51 AM](https://github.com/user-attachments/assets/6b4d3a8a-1166-4298-842f-9149c83387a7)
![Screenshot 2024-12-29 at 12 10 01 AM](https://github.com/user-attachments/assets/961f0f0a-6da6-450f-8685-86858a0b0b78)


### Question 3 (40 marks)

This question is based on your answers to Q2. If you cannot complete Q2 or have no confidence in your answers, you may use the IP addresses given in Figure Q3 to answer Question 3.

However, 5 marks will be deducted from your total marks for this question.

![Screenshot 2024-12-29 at 11 35 33 PM](https://github.com/user-attachments/assets/fdac9a58-4994-4bbc-8b00-52b2ff654fd4)

Discuss how network protocols and standards facilitate the transfer of data in this network by answering the following based on your answers to Q2:

**Question 3(a) (6 marks)**

Assume that all the routers in the network shown in Figure Q2 are enabled with only Routing Information Protocol version 2 (RIPv2) routing protocol. 

Write down the router configuration commands to be entered on all the routers to achieve reachability in the entire network.

**ANS:**

![Screenshot 2024-12-29 at 11 38 56 PM](https://github.com/user-attachments/assets/18547968-0400-4644-9810-8da3e8abb01a)

**Question 3(b) (6 marks)**

Assume all the routers are configured with RIPv2 routing protocol. 

It is desired to have backup static routes for PC1 to reach PC3 and vice versa via Routers A, B, and C. 

Give the configuration command(s) to set up the static routes and indicate the router(s) where the commands are implemented.

**ANS:**

![Screenshot 2024-12-29 at 11 39 38 PM](https://github.com/user-attachments/assets/c28c4703-9dcf-4726-996c-43c563db9083)


**Question 3(c) (4 marks)**

![Screenshot 2024-12-29 at 11 38 12 PM](https://github.com/user-attachments/assets/250af626-e02d-4efd-a874-9ab6982f74c2)

**ANS:**

![Screenshot 2024-12-29 at 11 41 06 PM](https://github.com/user-attachments/assets/cf96ba70-8392-49d0-be5f-ea342a3240b8)






### Question 4 (8 marks)

![Screenshot 2024-12-29 at 12 14 40 AM](https://github.com/user-attachments/assets/75078cdd-e910-465e-b6b6-eaab7d884728)
![Screenshot 2024-12-29 at 12 14 56 AM](https://github.com/user-attachments/assets/6af31a6c-f52b-4a23-ae44-ff7e8b139b5d)

**ANS:**

![Screenshot 2024-12-29 at 12 15 44 AM](https://github.com/user-attachments/assets/f75e5732-0450-4232-a251-f618288da4fe)
![Screenshot 2024-12-29 at 12 15 57 AM](https://github.com/user-attachments/assets/171ba4ae-8151-4f85-b330-693a1997f5f5)
![Screenshot 2024-12-29 at 12 16 08 AM](https://github.com/user-attachments/assets/87e70d13-38c1-40bb-9388-cf6ca84fddcf)


