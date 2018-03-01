# crc-error-detection
A simulation tool implementing CRC algorithm to transmitted messages.


![alt text](https://raw.githubusercontent.com/karakasis/crc-error-detection/master/readme-images/1.png)

The interface is divided into 5 main parts:
- Message list (1)
- Numerical Module-2 Tabs (2)
- Input message box (auto / manual) (3)
- Information box for each message (4)
- Result board (auto mode only) (5)




## Key Function Analysis

###### Command: *File> Mode>*
- Automatic
  
  The user introduces the prerequisites to simulate one sending of messages from the broadcaster
  - Binary Messages:
  
    Enter the number of messages
  - Bits per Message:
  
    Enter the number of bits that will transfer each message
  - Bit Error Rate:
  
    Enter the BER of the channel in decimal format
  - Binary Polynomial:
  
    Enter the binary combination to be used in the transmission

Once all the necessary information has been entered with Start, the message packet is sent.


![alt text](https://raw.githubusercontent.com/karakasis/crc-error-detection/master/readme-images/2.png)

- Manual

  The user introduces the prerequisites to simulate sending a message from the broadcaster
  - Binary Message:
  
    Enter the binary message to be transmitted
  - Binary Polynomial:
    
    Enter the binary combination to be used in the transmission
   - Noise Altered:

     Select whether the message will be spoiled
     - If selected: *(if correctly entered above)*
     
       - Bit Errors:
       
         Selection of bits that will be spoiled (at least one - Multiple bits are selected using ctrl + click)

After all the necessary information is inserted with the Add option, the message is added to the message packet and transmitted. As each message may have a different length or polynomial or noise alteration, it is obvious that it is not right to retain final results, so the function of the results is not accessible in manual mode.

![alt text](https://raw.githubusercontent.com/karakasis/crc-error-detection/master/readme-images/3.png)

## Frame Analysis

  - Message list:
  
    After each transmission (manual or auto) to the left of the interface, the list is filled with messages. By selecting one of these,     the user can see what happens when transmitting totally in the information box (green box) or modulo-2 process in the central tab       box.
    
    Select (Show): the user can filter the results shown in the list.
  - Tabs of numeric modulo-2
  
    It consists of 2 tabs:
    - CRC Transmitter:
      Displays the modulo-2 performed before transmitting to the transmitter to produce the FCS.
    - CRC Receiver:
      Displays the modulo-2 that occurs after transmission to the recipient to control the CRC.
  - Information box for each message
  
    In this context, the user sees information about a selected message:
    - Index, unique number that corresponds to the message
    - Binary Polynomial, the binary combination used to transmit the message
      (only available for mode: manual)
    - Transmitted, the message was transmitted
    - Received, the message received by the recipient
    - Noise Altered, true or false depending on whether it was altered
      the message from the silent channel (this value is true regardless of whether the message was detected by the CRC)
    - CRC Detected, true or false depending on whether the CRC detected the message as incorrect
    - Bit-Errors, the number of bits that were altered when transmitting the message
    - Re-transmit, (is only visible if the message was altered during transmission and the CRC marked it as corrupted)
      re-transmits the message as CRC detected it as corrupted
  - Result board (auto only)
    In this context, the user sees the statistics for a message packet:
    (Information can be displayed in 2 ways, either as a percentage or in an integer count)
    - Noise Altered Data, the percentage / number of messages that arrived at fault with the recipient
    - CRC Detected, the percentage / number of messages that you have
      were detected as incorrect by the CRC
    - CRC Not Detected, the percentage / number of messages that you have
      have arrived in error with the recipient but were not detected by the CRC.
    - Bit-Errors, a table that matches the number of bits with the number of messages having so many bit errors

## Analysis of secondary operations
###### Command: *File> Screenshot*
  Snapshot download and save to the Windows or the file execution file (OS rests)
###### Command: *File> Import CRC*
  Loading a .crc file from a previous run
###### Command: *File> Export as CRC*
  Save the current simulation in .crc file format
###### Command: *File> Clear Simulation*
  Delete any results the interface has generated (attention does not display a message)
###### Command: *Edit> Run Target Simulation*
  Insertion by the user of the number of messages and execution of exercise B as requested in the job
###### Command: *Edit> Run Random Simulation*
  Performing random simulation (with predefined thresholds that can be edited by the user, see Below *)
###### Command: *Edit> Batch Re-Transmission*
  Retransmits messages that have been flagged by the CRC as incorrect
###### Command: *Edit> Change Results Format*
  Changes the way the data appears in the results box (between percentages and integer values)
###### Command: *Edit> Customize Random Simulation*
  Edit Custom Values in Random Transmission Mode (attention has not been given to the input control structure, so the results depend on   the user input values)
###### Command: *Edit> Change Font Size*
  String size control
