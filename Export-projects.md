# Export Projects
Here are the best ways to export your n8n projects to GitHub:

**Option 1: Manual Export & Push (Simplest)**

1. **Export from n8n:**
   - Go to each project/workflow in n8n
   - Click the menu (three dots) → **Download**
   - Save the workflow JSON files locally

2. **Create a GitHub repository:**
   ```bash
   git init my-n8n-projects
   cd my-n8n-projects
   git remote add origin https://github.com/YOUR_USERNAME/my-n8n-projects.git
   ```

3. **Organize and push:**
   ```bash
   # Create a folder structure
   mkdir -p projects
   # Move your exported JSON files here
   
   git add .
   git commit -m "Initial n8n projects export"
   git push -u origin main
   ```

**Option 2: Using n8n's Built-in Git Sync (if available)**

Some n8n versions support Git integration:
- In n8n settings, look for **"Git"** or **"Version Control"**
- Connect your GitHub repository
- Push workflows directly from n8n

**Option 3: Automate with n8n Workflow**

Create an n8n workflow to export all your projects:
- Use the n8n API to fetch all workflows
- Save them as JSON files
- Commit to GitHub

**Folder Structure Example:**
```
my-n8n-projects/
├── README.md
├── projects/
│   ├── project-1.json
│   ├── project-2.json
│   ├── project-3.json
│   ├── project-4.json
│   └── project-5.json
└── .gitignore
```

**Tips:**
- Add a `.gitignore` to exclude sensitive data
- Include a README documenting each project
- Track the version of n8n used
