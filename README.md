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
   - ![Screenshot 2024-09-27 102640](https://github.com/user-attachments/assets/98c2582b-d262-44cf-a379-39feaf46784c)
   - In the Installation Keys tab unser the Sensor Downloads section, download the LimaCharlie executable and copy the Senor Key
   - ![Screenshot 2024-09-27 103051](https://github.com/user-attachments/assets/cf4e51c7-9ae2-4e09-867c-2ff2412c702e)




