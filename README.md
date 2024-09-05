# Login Screen

## Search

Use this search to search the web index for all events in the last 24 hours for the `access_combined` sourcetype that contain the keyword `mobile`:

<img width="901" alt="loginscreen" src="https://github.com/user-attachments/assets/744e3057-de45-4b16-8cd9-2a82a9ad9f40">

![Screenshot 2024-09-04 143521](https://github.com/user-attachments/assets/49e6b6e6-2463-4eda-accb-6244edb7e22c)

![Screenshot 2024-09-04 143644](https://github.com/user-attachments/assets/d8b79dc2-8a87-4c42-ad5d-cfa4d01b914a)


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

<img width="960" alt="gameextract" src="https://github.com/user-attachments/assets/21991768-48ac-40e0-9d7e-21ddef450e01">

## Can Save the Report

I labeled it `L1S1`.

## Delimiter Time

Search for all events in the last 30 days for the `SimCubeBeta` sourcetype in the `games` index using this search:

<img width="960" alt="filteroutipandtransaction" src="https://github.com/user-attachments/assets/83f4208d-7cb2-44d9-b376-6e9ee94e558d">

<img width="680" alt="srctags" src="https://github.com/user-attachments/assets/3f60188e-5b73-40cf-af62-faefd1f94e9d">

<img width="682" alt="transactionsid" src="https://github.com/user-attachments/assets/199337c5-0aed-4e94-b175-4c592fd79d57">

<img width="948" alt="savereport" src="https://github.com/user-attachments/assets/c04f00b5-6106-4758-b4e6-60e692cc1ffe">

<img width="958" alt="reports" src="https://github.com/user-attachments/assets/a1a90fcf-acb1-4590-b9e2-7c1e9a037a80">

## Extract Field

1. Delimiter: Select Comma.
2. Rename all the fields as follows (in this order):
   - `field1` > `time`
   - `field2` > `src`
   - `field3` > `version`
   - `field4` > `misc`
   
   Now you can see them listed.

3. Click Versions.

4. In the Fields sidebar, underneath the Interesting Fields section, click `+ Extract New Fields`.
   - On the Select Sample Event screen, click the first event to select it as a sample event.
   - Verify that the event now appears towards the top as a sample event.
   - Click the Next button at the top of the screen.

5. Select the Regular Expression method and click Next.
   - Give it a Field Name of `User`.
   - Click Add Extraction.

## Explore the fields I just created in Search link on the Success! page

1. Click the arrow (`>`) under the information icon (`i`) in the first event to see which fields are extracted.
2. Verify that in addition to the delimited fields we created earlier (`misc`, `src`, `time`, `version`), you also see the newly created fields using regular expressions (`Action`, `CharacterName`, `CurrentStanding`, `User`).
