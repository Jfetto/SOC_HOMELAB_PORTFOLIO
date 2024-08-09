# INTRO

Today is 8/8/2024 
Setup will be the same as before
- local virtual box as the vulnerable host, sliver server  as the attcker and LC in my local browser as the blueteam.
- 

Todays attack will be going deeper into sliver and LC, to see what wil happen when the sliver implant fully connects a reverse shell.
i will be exfilling data from the host and adding a file to the host from the sliver server, i will be monitoring this interaction via LC and wireshark. 


the last lab i did was making a rule to dectes the outbound call from the inplant i will be turning that off and seeing what other rules we can make, and using the file hash as a tracker is not very good procedure as we can make the implant change its hash if needed but that is for later. 

_____________________________________________
we are live 
![image](https://github.com/user-attachments/assets/37fb115d-80bb-4038-bd38-740a144409cb)

I am adding in wireshark now, this tool can spot all the odd behavior that points right to a threat actor, the implant is very loud and in later sections i will ocompare the implants to a beacon,

This screenshot of this capture shows just how load the implant is, even if it can go under the radar of our SEIM if we are monitoring wireshark its not very hard to spot out the odd behavor. 
![image](https://github.com/user-attachments/assets/0645387f-ce2a-448d-9129-1efa62df2cd5)

I now have a reverse shell actve into the host.

![image](https://github.com/user-attachments/assets/e5397541-9941-40ee-ab46-d90a73f353c1)

LC is picking this up from the WEL telemetry 

![image](https://github.com/user-attachments/assets/87e63007-ccb0-4b47-9d4b-55b39b42b651)

from the event info we can see that it is usuing the chess.exe as the "Image"

![image](https://github.com/user-attachments/assets/1a63625a-0f8f-4c6a-9674-8598f667131f)

From all the events that i can go through and sort i cant find a single one that was able to detect the file being uploaded and downloded from the sliver server, I was also able to create a dir, thats not to say it is completly hidden as you can clearly see that a reverse shell is present and active. that should be all that I need to act on this.


a few test i want to try now is renaming the implant while its running. 
 - outcome of tests
renaming the implant : Did not close the session, the task manager did update but needed to be restarted, Lima charlie did not update yet to the new file name [It never updated :( ]. I find that pretty interesting, It did update in the filesystem tracker but it is still kicking out events for the chess.exe file to the timeline and live feed. 
![image](https://github.com/user-attachments/assets/dd8ec9d7-1634-432d-a842-b0729545c01c)
![image](https://github.com/user-attachments/assets/521b2f45-4d9b-4cf6-a688-3fc02bb66320)







