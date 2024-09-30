# SOAR-EDR-Setup

## Objective

The SOAR-EDR project aimed to enchance an organization's cybersecurity posture by making the incident response processes efficient, improving threat detection and mitigation efficiency, and reducing the time to respond to security incidents. The primary focus was to generate events and send alerts to different communication channels utilizing a SOAR platform with endpoint detection and response. This hands on experience was designed to deepen understanding of automation, integration, and incident response strategies. By meeting these goals, the project aimed to foster a proactive cybersecurity environment that not only responds to threats more effectively but also empowers security teams to focus on strategic initiatives. 

### Skills Learned

- Integration of SOAR platform with existing EDR solutions.
- Develop and deploy automated workflows for incident response, including threat detection and containment.
- Improved ability to analyze security logs and alerts, identifying anomalies.
- Technical proficiency, gained hands on experience with security tools and platforms.
- Develop detailed documentation of the workflows, configurations, and best practices, ensuring proficient use of tool amognst personnel.

### Tools Used

- LimaCharlie Security for endpoint security, threat detection, and incident response.
- Automation tools such as (Tines) to streamline workflows by automating repetitive tasks.
- Virtualbox to run a virtual machine and create events without harming my own computer.

## Steps
1. Create a playbook workflow and brainstorm what actions should the playbook take
   - To create the workbook, use any diagramming program/application. What was used for this project is draw.io
   - Use four rounded rectangles to start the workbook, the 4 rectangles will be labeled LimaCharlie, Tines, Slack, and Email
   - LimaCharlie sends a detection over to Tines, and Tines will then send a message with details over to Slack and one via Email
   - Add a rectangle to demonstrate the user prompt, with the question "Does the user want to islate the machine?"
   - If yes, LimaCharlie will isolate the machine. If no, message will be sent over to slack
![Screenshot 2024-09-26 110701](https://github.com/user-attachments/assets/e5678eb4-6531-41e0-a75a-21da582b21bb)
   - To run it back, LimaCharlie detects the HackTool and sends it over to Tines where it will send a message with details via Email and Slack
   - Tines will also ask the user if they want to isolate the machine, from the user prompt if yes then LimaCharlie will isolate the machine automatically and send a message to slack with the isolation status
   - If no, message will be sent over to Slack with the message saying "The computer was not isolated, please ivestigate"

2. Install and setup LimaCharlie. Also making sure the endpoint is connected and is generating events
   - Head over to the Installation Keys tab and create an installation key
   - ![Screenshot 2024-09-27 102640](https://github.com/user-attachments/assets/98c2582b-d262-44cf-a379-39feaf46784c) ![Screenshot 2024-09-27 103051](https://github.com/user-attachments/assets/cf4e51c7-9ae2-4e09-867c-2ff2412c702e)
   - In the Installation Keys tab under the Sensor Downloads section, download the LimaCharlie executable and copy the Senor Key
   - After the download is completed, open Powershell and navigate over to the downloads directory with the command "cd Downloads"
   - Type in "dir" and the LimaCharlie executbale can be seen in there
   - Type in in the LimaCharlie executbale file followed by "-i" then paste in the sensor key that was copied directly from the Installation Key tab
   - The computer name can now be seen under the Sensor List ![Screenshot 2024-09-27 105947](https://github.com/user-attachments/assets/ee987867-387c-46c2-9e67-c9d5c8e6db54) ![Screenshot 2024-09-27 110532](https://github.com/user-attachments/assets/f765058d-f43b-4547-9e4b-1384e9f9949c)
  
3. Generate telemetry and create a detection & response rule in LimaCharlie to detect those events where Tines will automate
   - Head over to LaZagne's github and click on the releases, then download the LaZagne file
   - In the windows settings, disable real time preotections so that the file can be downloaded (this was done in a VM)
   - At this point, LimaCharlie should have been able to detect that event (the LaZagne file) and give us some information to start generating our detection rule
   - In LimaCharlie, click on the "Automation" tab and proceed with "D&R Rules" and click on the "New Rule" button ![Screenshot 2024-09-30 115410](https://github.com/user-attachments/assets/3350a6d0-6ed0-4cd0-a695-b8875f887dd8)
   - When creating the rule, it doesn't necessarily have to be done from scratch. Instead, by using "credential" in the search tab, a rule similar to what is needed can be chosen from the list
  
4. Setup both Slack and Tines, then test the connection between LimaCharlie and Tines to make sure the SOAR is seeing the detection generated by LimaCharlie
   - Head over to the Slack website and create an account, then create a workspace with a channel named "alerts". This is where alert messages will go to from Tines after LimaCharlie detects an event
   - Navigate to the Tines website and create an account
   - Establish the link between LimaCharlie and Tines, start by adding a Webhook
   - Name it as "Retrieve Detections" and under description add "Retrieves LimaCharlie Detections"
   - To officially esrtablish the connection between the two, copy the Webhook URL then head over to LimaCharlie. Go to the "Outputs" tab, click on add output, select Detections, select Tines, name it and paste the Webhook URL into the Destination Host  ![Screenshot 2024-09-30 122108](https://github.com/user-attachments/assets/7d0e99af-ccf5-4726-bc39-7b0d0b7d029e) ![Screenshot 2024-09-30 122353](https://github.com/user-attachments/assets/1cdaa672-7639-48f0-9b0f-3bccb2f7df15) ![Screenshot 2024-09-30 122409](https://github.com/user-attachments/assets/31e1529a-ce05-46f1-abc2-102f19a9fe96)










