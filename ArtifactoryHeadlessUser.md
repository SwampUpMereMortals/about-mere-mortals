# Artifactory headless user setup - SwampUP 2017 Talk

## 1. Admin login
First login to artifactory as an admin user.
Open the black management menu on the left and click the person looking icon at the bottom.
You'll want to select "Users" under "Security"
![Admin Menu](/images/1-AdminMenu.png)

## 2. User Management
This will land you on the User Management page.
You'll want to create a new user, so click the "+ New" button in the upper left.
![Users Management](/images/2-UsersManagement.png)

## 3. Add New User
This will land you on the Add New User page.
You'll need to setup a password for this user.
I highly recommend using a password manager to generate and store a random password
as you'll need this password later on if you have issues.
You'll want to add this user to the cideploy group.
This group was created earlier in the [Create CI Group](CreateCIGroup.md) instructions.

![Add New User](/images/3-AddNewUser.png)

## 4. Login As Ci User
Now that you've created the CI user, you'll need to log in as that user to generate it's api key.
(Hint: you can also generate api keys with the [JFrog](https://www.jfrog.com/confluence/display/CLI/JFrog+CLI))
Once logged in, you'll need to click on the "Welcome, mortal-ci" in the upper right to access the user profile.

![Login As Ci User](/images/4-LoginAsCiUser.png)

## 5. Unlock Profile
Upon switching to the profile page, the profile must be unlocked with the headless user's password.

![Unlock Profile](/images/5-UnlockProfile.png)

## 6. Generate Api Key
Once the profile is unlocked, you can click the little gear icon to generate an api key

![Generate Api Key](/images/6-GenerateApiKey.png)

## 7. Copy Key to clipboard
Copy the key to the clipboard using the copy button, and this is the api key you can use with travis-ci or the jfrog cli
to do headless operations.

If the key gets compromised, and admin can simple revoke this key and generate a new one.

![Copy Key to clipboard](/images/7-CopyKey.png)
