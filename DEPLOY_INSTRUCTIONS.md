# How to Deploy to Render

1.  **Push to GitHub**:
    *   Create a new repository on GitHub.
    *   Push this entire project (`bhakti-qa` folder) to the repository.

2.  **Create Web Service on Render**:
    *   Go to [dashboard.render.com](https://dashboard.render.com/).
    *   Click **New +** -> **Web Service**.
    *   Connect your GitHub repository.

3.  **Configure Service**:
    *   **Name**: `bhakti-qa` (or any name).
    *   **Region**: Choose closest to you.
    *   **Branch**: `main` (or `master`).
    *   **Root Directory**: Leave empty (since we have a root `package.json`).
    *   **Runtime**: `Node`.
    *   **Build Command**: `npm run build`
        *   *This runs the script in root package.json which builds client and installs server deps.*
    *   **Start Command**: `npm start`
        *   *This runs the script in root package.json which starts the server.*

4.  **Environment Variables**:
    *   Scroll down to "Environment Variables" and add:
        *   `NODE_ENV`: `production`
        *   `JWT_SECRET`: (Generate a random strong string)
        *   `DATABASE_URL`: (See step 5)

5.  **Database (PostgreSQL)**:
    *   **Option A: Render PostgreSQL (Recommended)**
        *   Click **New +** -> **PostgreSQL**.
        *   Create a database.
        *   Copy the **Internal Database URL** (if deploying web service in same region) or **External Database URL**.
        *   Paste this as the value for `DATABASE_URL` in your Web Service environment variables.
    *   **Option B: External DB (Supabase, Neon, etc.)**
        *   Get the connection string from your provider and use it as `DATABASE_URL`.

6.  **Deploy**:
    *   Click **Create Web Service**.
    *   Render will build and deploy your app. It might take a few minutes.

## Troubleshooting
*   **Build Failures**: Check the logs. Ensure `npm run build` works locally.
*   **Database Errors**: Ensure `DATABASE_URL` is correct and the database is accessible.
