The workflow uses a Google Sheet data source.
The sheet is not publicly accessible.
Access can be granted upon request.
When the workflow is triggered via the n8n URL the first applicant record is read from the Application Data tab sheet. 
A link to the associated label image for the applicant record is then used by Open AI Vision to read the data on the image label.
A validation check is then made between the data items from the applicant record and those of the label image.
Discrepancies are then logged in the COLA Validation tab sheet.
At this time only the first applicant record is being processed with AI-Powered label validation
Steps to run the prototype
1.Open the Google sheets link, click to request access.
2.View the applicant records in the Applicant Data tab sheet
3.View the COLA Validation Data tab sheet where the validation log will be written
4.Click the provided url to run the AI-powered label validation workflow
5.Open the Google sheets link to view the validation log data in the COLA Validation tab sheet

Brief documentation of approach, tools used, and assumptions made

The AI-Vision Assisted label validation reads data items from a record and checks for a match with an uploaded image hosted on the Weebly website.
The n8n cloud-native validation workflow is triggered by the provided Url as a webhook. The workflow then executes a workflow configuration and reads the applicant record.
The Vision API request is then prepared, a call to OpenAI Vision API is made then the comparison and matching process is performed.
The validation output is then formatted and written to the Google worksheet via the provided URL.

Only one record can be processed at this time. After the first applicant record is processed, any of the other two applicant records can be copied to the first row and the workflow can be repeated.
