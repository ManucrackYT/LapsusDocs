---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 🔄 How the Updater works?

Lapsus Updater is a brand new feature added in 2.8.2 and newer versions. It auto searches for new versions in the Lapsus Client repository every time you start the app. If there's a new version it will install the .zip called update.zip to the Lapsus Client folder and extract it into a temp folder (temp\_folder) which will automatically delete (including  after it moves the new files to the main directory.\
\
**It is really important to backup settings.json or you will lose all your personal values.** You can **optionally** make backup of other files like database.sqlite or your modified configuration.\
\
Now let's continue with some question you may have:

<details>

<summary>Can I paste the whole settings.json from the previous version to the new version?</summary>

**No. Don't do it.** If the new version has modifications in settings.json and you paste the older settings.json you can break the app or have some limitations or bugs

</details>

<details>

<summary>How can I run the Updater in Lapsus Client?</summary>

You can search for updates just by stopping the app and running it again like you usually do (using NodeJS, NPM or PM2). Once it starts again it will search for new updates

</details>

<details>

<summary>The Updater has failed while updating, what should I do?</summary>

If the Updater says that the installation has failed, you can report the error (if it displays an error code) or just run the app again to try again, that should work

</details>

<details>

<summary>I'm running a previous version that doesn't include the Updater, can I have it?</summary>

**No.** The Updater is meant to work in 2.8.2 or higher versions. If you try to implement the Updater to a previous version you will break the app

</details>

<details>

<summary>I don't want the Updater to automatically search for new updates</summary>

There isn't a manual search mode right now, it will always run when you start the app but don't worry, we will work on a manual mode

</details>

<details>

<summary>I have updated succesfully and the app is running but when i stop the process and try to run it fails saying the port is already in use</summary>

After an update is successfully completed, Lapsus Client restarts using PM2, a module that makes the app stay 24/7 online, even if you close the page or the SSH connection, there's already a guide about this when you install Lapsus Client for the first time. If you want to continue using NodeJS/NPM instead of PM2 just type `pm2 stop LapsusClient` and you will be able to use your favourite run command

</details>

<details>

<summary>I'm trying to run an unreleased version (not published yet in Github) and every time I run the app it auto downgrades to the latest official version</summary>

Yeah. You should not have unreleased versions or modifications from an advanced version so the Updater blocks this and makes an auto downgrade to avoid using these leaks. Just developers are whitelisted

</details>
