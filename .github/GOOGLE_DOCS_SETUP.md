# Google Docs CV Auto-Update Setup

This workflow automatically updates your CV PDF from Google Docs.

## Setup Instructions

### 1. Your Google Docs Document ID

Your Document ID is: `1Qyy0QVUUeeclv68EEQlMzY81LZ-I7WehCkhIufQr8w8`

(Extracted from: https://docs.google.com/document/d/1Qyy0QVUUeeclv68EEQlMzY81LZ-I7WehCkhIufQr8w8/edit)

### 2. Make Your Google Doc Accessible

You have two options:

#### Option A: Publish to Web (Recommended - Simplest)
1. In Google Docs, go to **File** → **Share** → **Publish to web**
2. Click **Publish**
3. Copy the link (or just note that it's published)
4. The document ID from step 1 is what you need

#### Option B: Share Publicly
1. In Google Docs, click **Share**
2. Change access to **Anyone with the link** → **Viewer**
3. Copy the link
4. Extract the Document ID from the URL

### 3. Add GitHub Secret

1. Go to your GitHub repository
2. Navigate to: **Settings** → **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. Add this secret:
   - **Name**: `GOOGLE_DOCS_CV_ID`
   - **Value**: `1Qyy0QVUUeeclv68EEQlMzY81LZ-I7WehCkhIufQr8w8`

### 4. Configure the Workflow

The workflow is set to run daily at 2 AM UTC. To change the schedule, edit `.github/workflows/update-cv-from-google-docs.yml` and modify the cron schedule:

```yaml
schedule:
  - cron: '0 2 * * *'  # Daily at 2 AM UTC
```

You can also manually trigger it from the **Actions** tab in GitHub.

### 5. Test the Setup

1. Go to **Actions** tab in GitHub
2. Click **Update CV from Google Docs**
3. Click **Run workflow** → **Run workflow**
4. Check if it completes successfully

## Troubleshooting

- **"Failed to download"**: Make sure your Google Doc is published or shared publicly
- **"Document ID not configured"**: Check that you've added the `GOOGLE_DOCS_CV_ID` secret correctly
- **Manual trigger**: Go to **Actions** → **Update CV from Google Docs** → **Run workflow**

## Advantages of Google Docs

- ✅ No session cookies needed
- ✅ Simpler setup
- ✅ Easy to edit your CV
- ✅ Automatic PDF export
- ✅ No expiration issues
