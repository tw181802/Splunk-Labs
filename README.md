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

Save the child dataset.
Select the Successful requests dataset.
a. Add a child dataset called `purchases` with an `Additional Constraints` value of `action=purchase`
`productId=*`.
b. Click Preview to see a test sample of your results, and verify the events match your constraints.

<img width="705" alt="d12" src="https://github.com/user-attachments/assets/bfe0e705-e1ff-45a6-820e-948c478dcb5b">

Select the Web requests event and add a child dataset named: `Failed requests`
a. In the `Additional Constraints` field, type: `status>399`
b. Click `Preview` to see a test sample of your results, and verify the events match your constraints.
c. Save the child dataset.
16. Under the Failed requests dataset, add a child dataset named: removed
a. In the `Additional Constraints` field, type: `action=remove productId=*`
b. Click `Preview` to see a test sample of your results, and verify the events match your constraints.
c. Save the child dataset.
17. Verify your dataset shows the root event as Web requests, with two child datasets (Successful requests
and Failed requests), each of which has one additional child dataset (purchases and removed)

<img width="711" alt="d13" src="https://github.com/user-attachments/assets/d7c401f2-b981-4b13-b328-ca1218e25773">

<img width="690" alt="d14" src="https://github.com/user-attachments/assets/c3db552f-c616-4b8b-beca-47309d79bbf4">

<img width="860" alt="d15" src="https://github.com/user-attachments/assets/f52f4578-42c6-415f-ae89-c74c47c7f970">

You can see the datasets and childs
<img width="889" alt="d16" src="https://github.com/user-attachments/assets/28d62b43-f0c1-4b84-a07b-31bd8a6a3e98">

Test your data model by creating a pivot

<img width="850" alt="pivot" src="https://github.com/user-attachments/assets/9794c2ca-9c08-4875-a0f8-87a232250125">

Select the Web requests dataset.
In the New Pivot window, change the following:
— Change Filters from All Time to Last 7 days
— Split Rows by action taken and click Add To Table

<img width="647" alt="d18" src="https://github.com/user-attachments/assets/7d41de24-b916-45cb-8d5b-5f193c2edcf4">
<img width="347" alt="d19" src="https://github.com/user-attachments/assets/46095a1f-87f2-4d6b-b8a3-5739c93192f1">

— Split Columns by date_mday and click Add To Table

<img width="534" alt="d20" src="https://github.com/user-attachments/assets/1aa4b5e9-c8e6-43d9-acdb-d29df6d5ffb6">

<img width="829" alt="d21" src="https://github.com/user-attachments/assets/30ad4494-36b7-4c8a-90fa-0ff0f30e5dd0">

From the `Add Field` drop-down list on the right, select `Eval Expression.`
b. In the `Eval Expression` field, type: `strftime(_time,"%m-%d %A")`

<img width="888" alt="d23" src="https://github.com/user-attachments/assets/ae5fe7e9-7059-4ca1-b180-15457cd8f54b">

<img width="690" alt="d24" src="https://github.com/user-attachments/assets/7b99cd91-7933-408f-89af-678a96ea9502">

<img width="879" alt="d22" src="https://github.com/user-attachments/assets/666b4e73-da8f-413c-8422-d4b787c2198c">

Click Pivot.
a. Select the Web requests dataset.
b. Change the time filter to the Last 7 days.
c. Split Rows by action taken. Click Add To Table.
d. Split Columns by day. Click Add To Table. (This is the new eval expression field we created in the last task.)
e. Click Save As and select Dashboard Panel

<img width="809" alt="d26" src="https://github.com/user-attachments/assets/e441a688-3edb-4294-b772-78be2a5dfccb">
For Dashboard Title, type: `Weekly Website Activity`
g. For Panel Title, type: Shopping cart activity by day
h. Click Save.


Verify that you are still in the Search & Reporting app. If necessary, click to expand the Apps menu next
to the splunk> logo at the top left of the window and choose Search & Reporting. If a window appears
asking you to take a tour, click Skip.
8. Navigate to Settings > Data models. Select the Buttercup Games Site Activity data model.
a. Make sure the Web requests root dataset is selected.
b. Click Add Field and select Lookup.
c. From the Lookup Table drop-down list, select http_status_lookup.
d. For the Input section in the Field in Lookup drop-down list, ensure code is selected.
e. From the Field in Dataset drop-down list, select status. (You may need to scroll down the list to
see this value.) This maps the status field in your indexed data to the code column in the lookup
table.

<img width="606" alt="d28" src="https://github.com/user-attachments/assets/f96bd585-c152-41d1-b0bf-a1d1b39a39b4">

<img width="407" alt="d27" src="https://github.com/user-attachments/assets/5eb1b384-6da7-4f9f-b503-9a21d4e3039b">


For the lookup Output section in the Field in Lookup field, check the description check box.
g. In the Display Name type: status description.
h. Click the Preview button. You should see a description column in the results.

<img width="603" alt="d29" src="https://github.com/user-attachments/assets/15264893-4582-48de-8e97-81504332ac38">

Click Pivot.
a. Select the Web requests dataset.
b. Change the Filter to Last 7 days.
c. From Split Rows, add the status description attribute and click Add To Table.
d. Click the + button to split by another row and add the status attribute. Click Add To Table.

<img width="820" alt="d30" src="https://github.com/user-attachments/assets/a9854011-77e2-454a-ad9a-ee8874ea72ff">

Verify that in addition to the event count, the table shows two columns, one for status description
and one for status.

Split Columns by day and click Add To Table.
g. Click Save As and select Dashboard Panel.
h. Select Existing and select Weekly Website Activity.
i. For the Panel Title, type: Web requests summary
j. Click Save.

<img width="398" alt="d32" src="https://github.com/user-attachments/assets/fa1049c9-2fb4-4a6c-81e1-ad54b5c13f95">


<img width="864" alt="d33" src="https://github.com/user-attachments/assets/0c2c658f-2dbf-4983-b412-4a107c73a77a">


For Field Name, type: day
d. For Display Name, type: day
e. Click Preview to verify your eval expression returns results.

<img width="834" alt="d17" src="https://github.com/user-attachments/assets/912abcb3-328e-4285-9932-d2d381161bf3">


Select the Column chart icon from the table formats on the left.

<img width="874" alt="d34" src="https://github.com/user-attachments/assets/e25b68b6-576b-47cf-ac8a-b57d560b9fcb">

<img width="785" alt="d36" src="https://github.com/user-attachments/assets/bfca5845-504b-4311-9234-b962cf000901">


<img width="695" alt="d37" src="https://github.com/user-attachments/assets/6ec587bf-d835-48a4-ba1f-bf43f4266678">


<img width="861" alt="d38" src="https://github.com/user-attachments/assets/473c2398-c96f-4cf0-bb97-6a2c4ec36a0e">

## Accelerated Modules

Navigate to Settings > Data models.
a. In the Data Models view, ensure that App: All is selected.
b. Click on the Owner: Any drop down and select your username.
c. You should see only the Buttercup Games Site Activity data model. Verify that the lightning bolt
icon is grey, showing that the data model is currently not accelerated.

<img width="818" alt="d39" src="https://github.com/user-attachments/assets/b31372b5-a3a4-4c9c-9fc3-8321e582eff3">

In the Buttercup Games Site Activity row, select Edit > Clone.
3. In the Clone Data Model window, prepend “Acc” so that the New Title is “AccButtercup Games Site Activity”. (Note: The New ID field will automatically update.)

<img width="409" alt="d40" src="https://github.com/user-attachments/assets/e6074c8f-457e-4a7b-abc8-6f3b97d76fdc">
Click Clone.

In the AccButtercup Games Site Activity row, select Edit > Edit Acceleration
![Uploading d41.png…]()









