# Firebase Project Setup Guide

## 1. Create a GitHub Repository

1. Open the GitHub template repository.
2. Click **Use this template → Create a new repository**.

## 2. Configure Firebase

1. Open the [Firebase Console](https://console.firebase.google.com/).
2. Create or select a Firebase project.
3. Go to **Add App → Web App**.
4. Copy the Firebase configuration and replace the values in `firebase-config.js`.
5. Enable **Authentication, Firestore, Storage, and Hosting**.
6. For Firestore and Storage, start in **Production mode**.

## 3. Clone the Repository

Clone your new GitHub repository to your local machine.

```bash
git clone <repository-url>
```

Navigate to the project directory.

## 4. Install Firebase CLI

Run the following commands if you have not already done so:

```bash
npm install -g firebase-tools
firebase login
```

## 5. Initialize Firebase

Run:

```bash
firebase init
```

Follow these prompts:

### Firebase Features

**Are you ready to proceed?**
- Yes

**Which Firebase features do you want to set up for this directory?**
- Select **Firestore** and **Hosting** using Space, then press Enter.

### Project Setup

**Please select an option:**
- Use an existing project

Select your Firebase project.

### Firestore Setup

**What file should be used for Firestore Rules?**
```text
firestore.rules
```

**What file should be used for Firestore indexes?**
```text
firestore.indexes.json
```

### Hosting Setup

**What do you want to use as your public directory?**
```text
public
```

**Configure as a single-page app (rewrite all URLs to /index.html)?**
- No

**Set up automatic builds and deploys with GitHub?**
- Yes

**File public/index.html already exists. Overwrite?**
- No

**For which GitHub repository would you like to set up a GitHub workflow?**
```text
user/repository
```

**Set up the workflow to run a build script before every deploy?**
- No

**Set up automatic deployment to your site's live channel when a PR is merged?**
- Yes

**What is the name of the GitHub branch associated with your site's live channel?**
```text
main
```

## 6. Update Firestore Rules

Replace the rules in the local `firestore.rules` file with the Firestore rules provided in the project README.

Run the following command to deploy the updated rules:

```bash
firebase deploy --only firestore:rules
```

This updates the Firestore rules in the Firebase Console to match your local rules file.

## 7. Push Changes to GitHub

Run:

```bash
git add .
git commit -m ""
git push origin main
```
