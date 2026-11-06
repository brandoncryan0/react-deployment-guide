# Set Up Git

Git tracks changes to your project over time. Before you can publish the project to GitHub, initialize Git inside the project folder and create your first commit.

## Check Your Current Folder

Before running Git commands, make sure PowerShell is open inside your React project folder.

You can check the current folder by running:

```bash
pwd
```

On Windows PowerShell, you can also run:

```bash
Get-Location
```

Your current directory should be the root of the React project.

## Initialize Git

Run:

```bash
git init
```

This creates a local Git repository inside the current project folder.

Git stores its internal tracking information in a hidden `.git` folder.

You normally do not need to edit anything inside this folder manually.

## Check the Repository Status

Run:

```bash
git status
```

Git will show which files are currently untracked or modified.

If this is a new repository, most project files will probably appear as untracked.

## Review `.gitignore`

Before creating your first commit, check that your project has a `.gitignore` file.

A typical Vite project should ignore files and folders such as:

```text
node_modules/
dist/
.env
```

These files usually should not be committed.

### Why `node_modules` Is Ignored

The `node_modules` folder can contain thousands of generated dependency files.

Other developers can recreate these files by running:

```bash
npm install
```

The project only needs to store the dependency information in files such as:

```text
package.json
package-lock.json
```

### Why `.env` Files Are Often Ignored

Environment files may contain private values such as:

- API keys
- tokens
- database credentials
- service configuration

Do not commit sensitive information to a public GitHub repository.

## Stage the Project Files

Run:

```bash
git add .
```

The period means:

```text
all changed files in the current project
```

This moves the files into Git's staging area.

You can think of the process like this:

```mermaid
flowchart LR
    A[Project Files] -->|git add| B[Staging Area]
    B -->|git commit| C[Local Git History]
```

## Check the Staging Area

Run:

```bash
git status
```

The files should now appear under a section such as:

```text
Changes to be committed
```

Review the list before continuing.

## Create the First Commit

Run:

```bash
git commit -m "Initial commit"
```

A commit records a snapshot of the staged project files.

The message:

```text
Initial commit
```

briefly describes what the commit contains.

## Check the Commit History

Run:

```bash
git log
```

You should see your new commit along with information such as:

- commit identifier
- author
- date
- commit message

Press `q` to exit the log view if necessary.

## If Git Asks for Your Name or Email

The first time you create a commit, Git may ask you to configure your identity.

Run:

```bash
git config --global user.name "Your Name"
```

Then:

```bash
git config --global user.email "you@example.com"
```

Use the name and email address you want associated with your Git commits.

After configuring them, run the commit command again.

## Verify the Repository

Run:

```bash
git status
```

After the first commit, you should see a message similar to:

```text
nothing to commit, working tree clean
```

This means your current project files have been committed successfully.

## Next Step

Once your first commit exists, continue to [Publish to GitHub](github.md).
