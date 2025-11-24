# How to Push Your Project to GitHub

Since this is your first time using Git, we need to set up your identity and create the first "save" (commit) of your code.

## Step 1: Configure Git (Run in Terminal)
Copy and run these commands one by one in your terminal to tell Git who you are:

```bash
git config --global user.name "Tanishq"
git config --global user.email "tanishq@example.com"
```
*(You can replace the email with your actual email if you want)*

## Step 2: Save Your Code (Commit)
Now, let's save all the files we created:

```bash
git add .
git commit -m "Initial commit: Bhakti Q&A App"
```

## Step 3: Create Repository on GitHub
1.  Log in to [GitHub.com](https://github.com).
2.  Click the **+** icon in the top-right and select **New repository**.
3.  **Repository name**: `bhakti-qa`
4.  **Description**: Bhakti Question & Answer Website
5.  **Public/Private**: Choose whichever you prefer.
6.  **Initialize this repository with**: Leave all unchecked (No README, No .gitignore).
7.  Click **Create repository**.

## Step 4: Connect and Push
After creating the repository, GitHub will show you a page with commands. Look for the section **"…or push an existing repository from the command line"**.

Copy and run those commands. They will look like this:

```bash
git remote add origin https://github.com/YOUR_USERNAME/bhakti-qa.git
git branch -M main
git push -u origin main
```

## Step 5: Deploy to Render
Once your code is on GitHub:
1.  Go to [dashboard.render.com](https://dashboard.render.com).
2.  Click **New +** -> **Web Service**.
3.  Select your `bhakti-qa` repository.
4.  Render will automatically detect the `render.yaml` file and configure everything!
