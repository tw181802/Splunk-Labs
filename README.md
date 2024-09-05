<img src ="https://github.com/user-attachments/assets/ebef05b3-f58d-463a-8d9a-4679fd357359" width="100">

# Splunk Lab - Field Extraction
# Login Screen
Enter your credentials

<img width="901" alt="loginscreen" src="https://github.com/user-attachments/assets/744e3057-de45-4b16-8cd9-2a82a9ad9f40">


## Search
Once logged in click `Search & Reporting`
Use this search to search the web index for all events in the last 24 hours for the `access_combined` sourcetype that contain the keyword `mobile`:


![Screenshot 2024-09-04 143521](https://github.com/user-attachments/assets/49e6b6e6-2463-4eda-accb-6244edb7e22c)

## SPL Query
Enter `index=web sourcetype=access_combined mobile`

![Screenshot 2024-09-04 143644](https://github.com/user-attachments/assets/d8b79dc2-8a87-4c42-ad5d-cfa4d01b914a)

Right click in the Event Viewer section and select > Extract Fields

![Screenshot 2024-09-04 143753](https://github.com/user-attachments/assets/42e59d08-907e-42cb-a1eb-34dd63fa187d)

## Event Actions > Extract Fields
![Screenshot 2024-09-04 143819](https://github.com/user-attachments/assets/ee66ebcf-780f-4512-bead-24a6dfdeda1e)


1. Select Regular Expression/Regex.
2. Add an extracted field for the IP address value:
   - Highlight the IP address value, which appears as the very first field, in the sample event.
   - In the Field Name field, type: `src`
   - Click Add Extraction.
   ![Screenshot 2024-09-04 143929](https://github.com/user-attachments/assets/d2fdb70f-f6d8-4e88-8a98-0d39bf50e6a0)

   **NOTE:** To view the pop-up box with the Field Name field, you may need to click on the highlighted IP address.
![Screenshot 2024-09-04 144006](https://github.com/user-attachments/assets/67902644-590f-4809-ba1f-aefe969931a0)

3. Add Extraction and Preview.
![Screenshot 2024-09-04 144108](https://github.com/user-attachments/assets/ed1ee09f-fd3b-43e8-94f4-5c24cb52874d)

4. Back at the top of the screen under Select Fields, highlight the last number in the event:
   - In the Field Name box, type: `transactionId`
   - Click Add Extraction.
![Screenshot 2024-09-04 144134](https://github.com/user-attachments/assets/72248f04-be28-41e0-b007-03a10a64fbc8)

<img width="813" alt="fieldextractionsexamples" src="https://github.com/user-attachments/assets/24f1dccd-195a-46c3-93bd-426e5ac11357">

Now Click "Save"

<img width="960" alt="gameextract" src="https://github.com/user-attachments/assets/21991768-48ac-40e0-9d7e-21ddef450e01">


## Delimiter Time

Search for all events in the last 30 days for the `SimCubeBeta` sourcetype in the `games` index using this search:

<img width="960" alt="filteroutipandtransaction" src="https://github.com/user-attachments/assets/83f4208d-7cb2-44d9-b376-6e9ee94e558d">

`src` field in left column example below:
<img width="680" alt="srctags" src="https://github.com/user-attachments/assets/3f60188e-5b73-40cf-af62-faefd1f94e9d">

`transactionID` field in left column example below:
<img width="682" alt="transactionsid" src="https://github.com/user-attachments/assets/199337c5-0aed-4e94-b175-4c592fd79d57">

Saved Report

<img width="948" alt="savereport" src="https://github.com/user-attachments/assets/c04f00b5-6106-4758-b4e6-60e692cc1ffe">

## Can Save the Report

I labeled it `L1S1`.

You can see the report listed
<img width="958" alt="reports" src="https://github.com/user-attachments/assets/a1a90fcf-acb1-4590-b9e2-7c1e9a037a80">



## Extract Field

Search games w/ this SPL query -> `index=games sourcetype=SimCubeBeta`

 <img width="944" alt="gamessimcub" src="https://github.com/user-attachments/assets/ce870897-6c5a-4ad0-948e-fb8e77699527">
Extract Field -> Click the arrow (>) under the information icon (i) in the first event to see which fields are extracted.

<img width="935" alt="extractfieldsgames" src="https://github.com/user-attachments/assets/b2d8e07f-2c49-40cd-83ca-0b8724558ba7">


1. Delimiter: Select Comma.
   
   <img width="920" alt="delimiterfieldextraction" src="https://github.com/user-attachments/assets/69199df7-7820-406e-9ff5-abbe572625b5">



Next Screen: 
<img width="712" alt="commadelimiter" src="https://github.com/user-attachments/assets/77f2a8ca-cf83-4e00-b16b-8c6dfcd559b0">


2. Rename all the fields as follows (in this order):
<img width="928" alt="renamefield" src="https://github.com/user-attachments/assets/7cf03e2c-9ef5-4548-a59d-4035125df975">


   - `field1` > `time`
   - `field2` > `src`
   - `field3` > `version`
   - `field4` > `misc`

<img width="813" alt="examplegamesnewfilter" src="https://github.com/user-attachments/assets/caaaea57-f1d0-4316-be19-4125f9cc0eae">

   Now you can see them listed.
   
3. Click Versions.
   
<img width="536" alt="newfieldsgame" src="https://github.com/user-attachments/assets/de7049b3-e285-4233-9152-6c50af5131a8">

4. In the Fields sidebar, underneath the Interesting Fields section, click `+ Extract New Fields`.
   
   <img width="693" alt="newlycreatedfields" src="https://github.com/user-attachments/assets/d86077d2-0656-477b-aca2-19740cfeb9dd">

   - On the Select Sample Event screen, click the first event to select it as a sample event.
   - Verify that the event now appears towards the top as a sample event.
   - Click the Next button at the top of the screen.
     
<img width="960" alt="anotherregexuser" src="https://github.com/user-attachments/assets/0bd570b1-50c9-4a0a-8d3f-1ef1733fec54">

<img width="959" alt="regexfornamechangegames" src="https://github.com/user-attachments/assets/e7021eda-f6ff-401a-9ec7-e1c65777b540">


5. Select the Regular Expression method and click Next.
   - Give it a Field Name of `User`.
   - Click Add Extraction.
The Others Field Names are we changed are `Action`, `CharacterName`, `CurrentStanding`
## Explore the fields I just created in Search link on the Success! page

1. Click the arrow (`>`) under the information icon (`i`) in the first event to see which fields are extracted.
2. Verify that in addition to the delimited fields we created earlier (`misc`, `src`, `time`, `version`), you also see the newly created fields using regular expressions (`Action`, `CharacterName`, `CurrentStanding`, `User`).

# Splunk Lab - Data Models

# Login Screen
Enter your credentials

<img width="901" alt="loginscreen" src="https://github.com/user-attachments/assets/744e3057-de45-4b16-8cd9-2a82a9ad9f40">


## Data Models
Once logged in click `Settings` > `Data Models`

<img width="887" alt="datamodels1" src="https://github.com/user-attachments/assets/8814dd5c-51f4-4ffe-abda-73026f6a200c">

Click

<img width="885" alt="datamodels2" src="https://github.com/user-attachments/assets/9e54dc01-f26c-4446-8c73-f836ddcc10b1">

I Named this one `ButterCup Games Site Activity` 

<img width="733" alt="dm3" src="https://github.com/user-attachments/assets/ca7058b4-0367-44d1-80c1-457360b00d15">

Click Add Dataset
<img width="877" alt="dm4" src="https://github.com/user-attachments/assets/91422fb3-9193-4c5a-902d-f1e4952e09f2">

Click Add Event Dataset and name it `Web Request` set Constraints > `index=web sourcetype=access_combined` > Click `Preview`

<img width="879" alt="dm5" src="https://github.com/user-attachments/assets/217f7864-6662-4a21-9a3d-dc84353aa9ac">

Here is example of the preview

<img width="879" alt="dm6" src="https://github.com/user-attachments/assets/c02d4b3e-47ee-4cef-906a-b7472dcac742">

Click `Add Field` > `Auto-Extracted`

<img width="861" alt="dm7" src="https://github.com/user-attachments/assets/0c844153-f85f-447d-8788-d9bb2d9767fe">

Select the checkboxes
Click the check boxes to select the following fields, and rename them for pivot users as indicated:
``— action > action taken
— bytes > size
— categoryId > product category
— clientip > client IP
— date_mday > date_mday 
— productId > product ID
— product_name > product name
— req_time > request time
— status > status``

<img width="732" alt="dm8" src="https://github.com/user-attachments/assets/1b6895f3-05be-4de1-8c06-07bd6e9e8809">

Click `Add Datasets` > `Child`

<img width="870" alt="dm9" src="https://github.com/user-attachments/assets/6f676112-8ca8-4d25-98a0-78d05a70e2fb">

Verify the events match your constraints. Events from `index=web
sourcetype=access_combined` should start with an IP address, and contain `GET` or `POST` message fields and web URLs. Note: If the preview does not match the expected results, check
the Constraints field you typed to ensure there are no mistakes. Keep the Sample: 1,000 events selection at this time. Click Save to save the root event.

<img width="875" alt="dm10" src="https://github.com/user-attachments/assets/ae91b2f4-1f49-4ceb-9a9f-8fb2a758598b">

## Task Add two child events, one for actions that were successful (status<400) and one for actions that failed (status>399.)
13. Click `Add Dataset` and select `Child`.

    <img width="856" alt="d11" src="https://github.com/user-attachments/assets/a411961b-56fb-4e3b-a20f-8f86935a72f7">

a. In the Dataset Name field, type: `Successful requests`
b. In the `Additional Constraints` field, type: `status<400`

c. Click `Preview` to see a test sample of your results.<img width="877" alt="d10" src="https://github.com/user-attachments/assets/d49d3fe8-9622-4f69-ab86-3c73f341206e">

d. Verify the events match your constraints. Check the number field value that comes just after the
string field that starts with the word “GET” or “POST”. The number should be less than 400
<img width="875" alt="dm10" src="https://github.com/user-attachments/assets/0b5fbca5-60d1-44fc-aedc-f7aaf20d9496">

<img width="856" alt="d11" src="https://github.com/user-attachments/assets/ec68a248-5627-4914-a075-58e768f63798">



