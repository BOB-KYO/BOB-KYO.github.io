# GitHub Pages Personal Academic Website Setup Notebook

Audience: students with little or no frontend experience and only basic Python knowledge.

This document is written in a notebook-style format. Each step is a self-contained record that explains why the step matters, what to do, and what result to expect. At this stage, the notes cover the process from creating a GitHub account to reaching the current milestone: a basic live website at `https://lijingzhu1.github.io/`.

---

## Step 1. Create a GitHub Account

> Goal: create a GitHub account, because GitHub Pages uses a GitHub repository to host the website.
>
> Actions:
> 1. Open https://github.com/
> 2. Click `Sign up`
> 3. Enter your email, password, and username
> 4. Follow the registration steps
>
> Notes:
> - The username matters because the personal website URL is tied to it.
> - For an academic website, the username should be formal, simple, and easy to recognize.

Suggested screenshots:
- GitHub homepage with the `Sign up` button
- GitHub registration page

---

## Step 2. Verify the Email and Sign In

> Goal: make sure the account is fully activated and ready to use.
>
> Actions:
> 1. Open the email inbox used during registration
> 2. Find the verification email from GitHub
> 3. Click the verification link
> 4. Return to GitHub and sign in
>
> Notes:
> - Without email verification, some GitHub features may be limited.
> - Later steps such as creating repositories, enabling Pages, and pushing updates all depend on having a usable account.

Suggested screenshots:
- Email verification message
- GitHub home page after login

---

## Step 3. Create the Personal Website Repository

> Goal: create the special repository used by GitHub Pages for a user site.
>
> Actions:
> 1. Click the `+` icon in the top-right corner of GitHub
> 2. Choose `New repository`
> 3. Set the repository name to `lijingzhu1.github.io`
> 4. Choose `Public`
> 5. Click `Create repository`
>
> Notes:
> - The repository name must exactly match the GitHub username pattern.
> - If the username is `lijingzhu1`, the repository must be `lijingzhu1.github.io`
> - GitHub recognizes this naming pattern as a user website.

Key rule:

```text
Repository name = GitHubUsername.github.io
Example: lijingzhu1.github.io
```

Suggested screenshots:
- New repository page
- Example of the correct repository name

---

## Step 4. Choose an Initial Website Template

> Goal: avoid building the site from scratch and instead start from a working template.
>
> Actions:
> 1. Choose a GitHub Pages or Jekyll template
> 2. Put the template files into the `lijingzhu1.github.io` repository
> 3. Keep the base structure so the site can run first
>
> Notes:
> - At this stage, the priority is not visual design. The priority is getting a working site online.
> - For students without frontend experience, starting from a template is much safer than writing raw HTML and CSS.
> - All later cleanup and simplification depend on the template already building correctly.

Suggested screenshots:
- Template repository homepage
- Repository structure after applying the template

---

## Step 5. Enable GitHub Pages Deployment

> Goal: let GitHub automatically build and publish the website.
>
> Actions:
> 1. Open the repository `Settings`
> 2. Click `Pages` in the left sidebar
> 3. In `Build and deployment`, choose:
>    - Source: `Deploy from a branch`
>    - Branch: `main` or `master`
>    - Folder: `/ (root)`
> 4. Save the settings
>
> Notes:
> - If the template follows the standard GitHub Pages or Jekyll structure, GitHub will build the site automatically.
> - The first deployment may take a few minutes.
> - After deployment, GitHub will show the site URL.

Suggested screenshots:
- `Settings > Pages`
- Branch and folder selection

---

## Step 6. Add Homepage Content and Create the First Live Version

> Goal: make the website more than an empty template and publish at least one accessible version.
>
> There are two common ways to do this:
>
> Option A: edit directly on GitHub  
> Best for students with no local development experience.
>
> Option B: clone the repository locally and edit files on the computer  
> Better for users who expect to make repeated updates.
>
> At this stage, the goal is simple: get a first working homepage online.

If using the local workflow, the basic commands are:

```bash
git clone https://github.com/lijingzhu1/lijingzhu1.github.io.git
cd lijingzhu1.github.io
```

After making changes locally:

```bash
git add .
git commit -m "Initial website setup"
git push
```

Notes:
- For beginners, editing in the GitHub web interface is simpler.
- For later tasks such as cleaning folders, simplifying configuration, and editing multiple pages, a local clone is more efficient.

Suggested screenshots:
- GitHub web editor
- Terminal after a successful `git clone`

---

## Step 7. Wait for Deployment and Check the URL

> Goal: confirm that the website is actually published, not just stored in the repository.
>
> Actions:
> 1. Open the repository `Actions` or `Pages` page
> 2. Wait for the build to finish
> 3. Visit `https://lijingzhu1.github.io/`
> 4. Check whether the page opens normally
>
> Notes:
> - If the page loads, the first deployment stage is complete.
> - If styles are broken, links fail, or images do not appear, the cause is usually a path or configuration issue.

Suggested screenshots:
- Successful GitHub Actions build
- The first live homepage

---

## Step 8. Current Progress Record

> Current completed status:
> - A GitHub account exists
> - The personal website repository has been created
> - A template-based first version has been set up
> - The site is live at `https://lijingzhu1.github.io/`
>
> This means the first milestone, going from zero to a live website, has already been completed.
>
> The next priority is no longer "Can the site go online?"
> The next priority is:
> 1. Simplify the template
> 2. Make the structure easy for students to maintain
> 3. Keep only essential sections such as `About`, `Projects`, and `CV`

---

## Step 9. What the Next Phase Will Do

> The next phase is not about rebuilding the site from scratch.
> It is about simplifying and organizing the existing site.
>
> Main goals:
> - Remove unnecessary sections
> - Simplify the navigation bar
> - Clean up `_config.yml`
> - Keep only the files students actually need to edit
> - Write instructions that work for users with zero frontend experience

The next round of edits will focus on:
- `About`: a short personal introduction
- `Projects`: portfolio or research/project highlights
- `CV`: a resume link or CV page

---

## Simple Mental Model for Students

> At this stage, students can think about the website like this:
>
> - GitHub repository = where the website source files are stored
> - Markdown files = page content
> - `_config.yml` = site-wide settings
> - GitHub Pages = the service that automatically turns those files into a website
>
> In other words, students do not need frontend development knowledge.
> They mainly need to learn how to:
> 1. Edit a small number of Markdown files
> 2. Understand a small number of configuration fields
> 3. Commit changes and wait for GitHub to redeploy the site

---

## Suggested Next Collaboration Step

> If the next task is only to continue writing documentation or refining the teaching notes, cloning the repository is not required yet.
>
> But if the next task is to directly edit the website repository, for example:
> - clean the repository structure
> - simplify `_config.yml`
> - reduce the navigation bar
> - delete unnecessary pages
> - verify links
>
> then cloning `lijingzhu1.github.io` locally will make the work much easier.

Recommended local setup:

```bash
git clone https://github.com/lijingzhu1/lijingzhu1.github.io.git
cd lijingzhu1.github.io
```

Once the repository is cloned and the local path is available, the next phase can focus on simplifying the site into a student-friendly version with only `About`, `Projects`, and `CV`.
