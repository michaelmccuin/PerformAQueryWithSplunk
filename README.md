<h1>Perform a Query with Splunk</h1>

<h2>Description</h2>

📊 **Overview**
  - Conducted a hands-on practical lab using the Splunk platform, focusing on uploading data, performing basic searches, and identifying potential security issues within an e-commerce environment. The primary objective was to enhance skills in using Splunk for security analysis and incident response.
    
🔍 **Key Points**
  - Initial Search and Field Examination: Conducted an initial search to confirm data ingestion, retrieving thousands of events, and analyzed fields such as host, source, and sourcetype.
  - Focused Search: Narrowed down search results to events from the mail server, identifying over 9000 relevant events.
  - Incident Analysis: Performed detailed searches to locate failed SSH login attempts for the root account, uncovering over 300 events.

🚀 **Objectives**
  - Validate Data Ingestion: Confirm data from Buttercup Games' mail servers was correctly ingested and indexed in Splunk.
  - Perform Effective Searches and Document Findings: Utilize SPL for targeted searches to identify security incidents and provide detailed documentation.
  - Improved Data Accessibility: Create a visual representation of data to enhance clarity by highlighting daily patterns and trends, making the data more accessible for analysis and decision-making.

<h2>Project Walk-Through:</h2>

**Step 1: Add Data to Splunk Cloud**  
  1. Add data to Splunk Cloud for analysis. <br/>
  ![Image 1](https://i.imgur.com/X4NUPno.png)
  2. Upload the file. <br/>
  ![Image 2](https://i.imgur.com/1HApmDB.png)
  3. Select this to automatically set the host value to the first segment of the file path, ensuring consistent and accurate identification of the originating machine for each event. <br/>
  ![Image 3](https://i.imgur.com/l8yDZL7.png)
  4. After submitting the upload with the specified settings, confirm that Splunk has successfully ingested the data and will display the correct details for further analysis. <br/>
  ![Image 4](https://i.imgur.com/frS2eEE.png)
  5. The file was uploaded successfully. <br/>
  ![Image 5](https://i.imgur.com/NbVNRwE.png)

**Step 2: Perform and Evaluate Search**  
  1. Perform All Time search of uploaded data. <br/>
  ![Image 6](https://i.imgur.com/Qw8Hlu7.png)
  2. This sample log entry shows the host as www1, the source as Splunk Query.zip:./www1/access.log, and the sourcetype as access_combined_wcookie. This provides context for me to locate the mail server. <br/>
  ![Image 7](https://i.imgur.com/xjol91h.png)

**Step 3: Narrow Search**  
To pinpoint failed SSH logins for the root account on the mail server, I conducted a search focused on the mailsv host. <br/>
![Image 8](https://i.imgur.com/0gItF5M.png)

**Step 4: Further Narrow Search**  
Refined the search further by using "index=main host=mailsv fail* root" to specifically locate failed SSH login attempts for the root account on the mail server, leveraging the "fail*" wildcard to capture all variations of the term "fail." The search has ultimately been narrowed down from 109,864 to 346 events. <br/>
![Image 9](https://i.imgur.com/M9SUAZ6.png)

**Step 5: Create Visual Representation of Data**  
Creating a bar graph of the failed login attempts enhances comprehension by clearly illustrating daily patterns and trends, making it easier to identify peak failure times and potential security threats. <br/>
![Image 10](https://i.imgur.com/wWLKeW3.png)
