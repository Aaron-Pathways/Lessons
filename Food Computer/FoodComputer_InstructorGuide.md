# Enabling Drive Api and Test User

### Step 1: Create a Google Cloud Project
Follow [This Guide Created By Google](https://developers.google.com/workspace/guides/create-project) to create a Google Cloud Project. Make sure you're using the Google account you desire.


### Step 2: Python Google Api Quickstart
Follow the [This Python Quickstart](https://developers.google.com/drive/api/quickstart/python). **HOWEVER**, select `External` for the User type in the Oath consent form.

This starter code will throw an error; we will fix it in the next steps.


### Step 3: Finalizing Config
You will need to add yourself as a Test User in order for OAuth to verify: 
1. Navigate to your project dashboard 
2. In the left pane, select `Api's and Services` -> `OAuth consent screen`
3. In the **Scopes** section, select `ADD OR REMOVE SCOPES`
4. Search for `Drive`
5. Select these two Scopes then **Update**:

        .../auth/drive.file

        .../auth/drive.metadata.readonly
6. In the **Test Users** section, select `Add Users`
7. Add yoself. You can use any **Google Account** email here


### Step 4: Finalizing Code
Located in the quickstart code copied from step 2, append the `SCOPES` list with this scope:
        
`https://www.googleapis.com/auth/drive.file`

>*Tip*: Chunking the functionality of the quickstart code into respective modules will make custom implementations much easier to work with. **See [Food Computer](https://github.com/Aaron-Pathways/food-computer/tree/dev) implementation*

At this point, your code should be able to successfully prompt you to sign in via OAuth and exit with no faults upon successful authentication. If you have files in your Google Drive, they will show in the console output.

---

# Adding Students to Project
Once "Api Designees" have been determined for each group, Gather their emails and add them as test users:
>Note: This method is only if you want to use the instructor's project as a centralized OAuth location. Should students need their own google projects, they can just follow the `Enabling Drive Api and Test User` section of this document.

1. Follow **Step 3** above to get to the Test Users screen
2. Add Users
3. Create seperate **OAuth credentials** for each user. **Use a naming convention**!
4. Disburse the credentials as either a file or text to each user. Final format should be `credentials.json`




