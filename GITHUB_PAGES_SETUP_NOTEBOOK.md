# Build a Personal Professional Website with GitHub Pages

This handout introduces the basic tools behind a GitHub Pages website and outlines the setup process for a simple professional portfolio site.

The target outcome is a personal website that presents:
- an introduction or profile
- projects or portfolio items
- a CV

This guide assumes little or no prior web development experience.

---

## 1. Core Concepts

### What is GitHub?

GitHub is an online platform for storing, organizing, and updating project files.

In this project, GitHub serves three roles:
- repository hosting
- change tracking
- website publishing through GitHub Pages

![GitHub Logo](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)

### GitHub in Industry

GitHub is widely used in professional settings, not only in classrooms.

Common uses include:
- software development and product maintenance
- analytics and machine learning project management
- documentation and internal knowledge sharing
- code review and team collaboration
- portfolio and technical website publishing

GitHub experience is valuable because it demonstrates familiarity with modern technical workflows, version history, collaboration practices, and public project presentation.

Example 1: code review and team collaboration on GitHub  
Many organizations use pull requests and review workflows before accepting changes.

![GitHub Code Review Example](https://images.ctfassets.net/8aevphvgewt8/vKhwDJy0MsI9KYmvPizOl/1a57ca6665e90c3d2a95bcdd70741970/section-collaboration.webp)

Example 2: project planning with GitHub Projects  
Teams often use GitHub boards to organize tasks, features, and bugs.

![GitHub Projects Example](https://images.ctfassets.net/8aevphvgewt8/27eLhmIKAlEcRSEIyJvNCa/3e2df8371033833f91920ae9269f2595/section-project-management.webp)

Example 3: repository access management  
Organizations use GitHub to control who can view, edit, and manage repositories.

![GitHub Access Management Example](https://images.ctfassets.net/8aevphvgewt8/67xCi4ySv2uzIrU9D3ecS8/7a69be605ac676e20675bc7816063dc2/section-team-administration.webp)

### What is a repository?

A repository, usually called a repo, is a project folder stored on GitHub.

A repository may include:
- Markdown files
- images
- PDFs
- notebooks
- code
- website configuration files

For this website project, the repository contains all source files required to build and update the site.

### What is GitHub Pages?

GitHub Pages is a free hosting service that publishes website files directly from a GitHub repository.

For example, a repository named:

```text
lijingzhu1.github.io
```

can be published as:

```text
https://lijingzhu1.github.io/
```

### Why use this workflow in class?

This workflow is useful in a classroom setting because it is:
- free
- easy to maintain
- suitable for personal portfolios
- aligned with common research and industry practice

The workflow also keeps the focus on content, structure, and documentation rather than advanced frontend development.

---

## 2. Step 1: Create a GitHub Account

Create an account at:

```text
https://github.com/
```

Procedure:
1. Click `Sign up`
2. Enter an email address, password, and username
3. Complete email verification
4. Sign in

Purpose:
- the GitHub account will own the website repository
- the username will be part of the site URL

**Choose a professional username.** The GitHub username becomes part of the public website address and public online identity. For a professional portfolio site, the username should be formal, clear, and appropriate for use on a resume, CV, or portfolio.

![GitHub account creation form](week14/images/Signup.png)

---

## 3. Personal Website Templates on GitHub

GitHub includes a large collection of personal website repositories and themes.

A useful starting point is the GitHub topic page:

- GitHub personal website topic: https://github.com/topics/personal-website

This page collects many different kinds of personal website templates, including:
- professional portfolio websites
- portfolio websites
- developer portfolios
- minimal personal pages
- blog-style personal sites

Examples of commonly used templates:

### Academic Pages

- Website: https://academicpages.github.io/
- Repository: https://github.com/academicpages/academicpages.github.io
- Best for: profile sites with publications, talks, teaching, and CV content

### al-folio

- Repository: https://github.com/alshedivat/al-folio
- Best for: polished professional or academic sites with projects, publications, and a more design-focused layout

### academic-homepage

- Website: https://luost26.github.io/academic-homepage/
- Repository: https://github.com/luost26/academic-homepage
- Best for: lightweight professional or academic homepages with a simpler structure

### Minimal Light

- Website: https://minimal-light-theme.yliu.me/
- Repository: https://github.com/yaoyao-liu/minimal-light
- Best for: minimal one-page or low-maintenance professional websites

### Our course template

The course website template is adapted from an existing website template rather than built entirely from scratch.

In particular:
- the course workflow is based on the Academic Pages style of GitHub Pages site structure
- Academic Pages is one of the well-known website templates listed in the broader GitHub personal website ecosystem
- the course version is being simplified for classroom use so that attention stays on content and structure

---

## 4. Core Files and Working Model

Most of the work in this project is concentrated in a small number of file types:

- `.md` files: page content written in Markdown
- `_config.yml`: site-wide configuration
- image and PDF files: supporting assets

Working model:

```text
GitHub account = identity and access
Repository = website source folder
Markdown file = page content
_config.yml = site settings
GitHub Pages = publishing service
```

Professional analogy:

```text
GitHub account = team identity
Repository = project workspace
Markdown file = documentation
Code file = implementation
GitHub = collaboration platform
```

---

## 5. Step 2: Copy the Course Website Template

The website should begin from the instructor-provided repository template, not from a blank repository.

Procedure:
1. Open the instructor-provided website repository
2. Click `Use this template`
3. Select `Create a new repository`

![Create a new repository from template](week14/images/create_repos.png)

---

## 6. Step 3: Name the New Repository Correctly

When GitHub asks for the repository name, use this format:

```text
yourusername.github.io
```

Example:

```text
lijingzhu1.github.io
```

**The repository name must follow this exact pattern: `yourusername.github.io`.**

**This name directly determines the website address, so it must match the GitHub username.**

Procedure:
1. Select the correct GitHub account as the owner
2. Enter `yourusername.github.io` as the new repository name
3. Choose `Public`
4. Create the repository from the template

GitHub interface example:

![GitHub Repository Name Field](https://docs.github.com/assets/cb-89988/images/help/repository/create-repository-name.png)

---

## 7. Step 4: Configure GitHub Pages Settings

After the new repository is created, open the repository settings and confirm the Pages configuration.

Procedure:
1. Open `Settings`
2. Click `Pages`
3. Under `Build and deployment`, choose `Deploy from a branch`
4. Select the main branch, usually `main` or `master`
5. Select the root folder `/ (root)`
6. Save the settings

GitHub interface example:

![GitHub Repository Settings Tab](https://docs.github.com/assets/cb-28260/images/help/repository/repo-actions-settings.png)

![GitHub Pages Branch Selection](https://docs.github.com/assets/cb-47265/images/help/pages/publishing-source-drop-down.png)

![GitHub Pages Root Folder Selection](https://docs.github.com/assets/cb-24510/images/help/pages/publishing-source-folder-drop-down.png)

---

## 8. Step 5: Update the Site Configuration and Personal Content

After the repository is created, open `_config.yml` and edit the fields in the same order they appear in the file.

Edit these fields first:

1. Site title and description

```yaml
title: "Lijing Zhu | Data Science & ML Research"   # Text shown in browser tab and SEO metadata
title_separator: "-"                               # Separator used in page titles
name: "Lijing Zhu"                                 # Main name shown across the site
description: "Professional portfolio and research in data science and machine learning"  # Short site description for search engines
```

2. Website URL and repository path

```yaml
# For a user site, url should match:
# https://yourusername.github.io
url: "https://lijingzhu1.github.io"

# Must match the GitHub repository path exactly:
# username/repository-name
repository: "lijingzhu1/lijingzhu1.github.io"
```

3. Author profile information

```yaml
# Author profile information
author:
  avatar: "profile.JPG"    # Profile image file shown in the sidebar/profile area
  name: "Lijing Zhu"
  bio: "Assistant professor at University of Houston-Clear Lake. Ph.D. in Data Science from Bowling Green State University. Research focus on machine learning and graph-based deep learning."
  location: "TX"
  employer: "University of Houston-Clear Lake"
  email: "zhul@uhcl.edu"

  # Professional / academic links
  # If a link is not available, deleting that field is usually cleaner than leaving it empty.
  googlescholar: "https://scholar.google.com/citations?user=_c1ydPQAAAAJ&hl=en"
  github: "lijingzhu1"
  linkedin: "www.linkedin.com/in/lijingz-19970620"
  orcid: "https://orcid.org/0009-0002-7107-2880"
```


4. Profile photo setup

First upload the profile photo to the `images/` folder. Then update the avatar file name in `_config.yml`.

Recommended file:

```text
images/profile.png
```

Example:

```yaml
author:
  avatar: "profile.png"
```

To add or replace the profile photo:
1. Open the `images/` folder in the repository
2. Upload a new photo file such as `profile.png`
3. If a photo already exists, replace it or upload a new file with a different name
4. Update `author.avatar` in `_config.yml` so the file name matches exactly
5. Commit the change

Recommended photo guidelines:
- use a clear headshot or professional portrait
- use a square or near-square image if possible
- keep the file name simple, such as `profile.png` or `myphoto.jpg`
- keep the image in the `images/` folder for consistency

After updating `_config.yml`, save and commit the changes.

Important notes:
- `url` and `repository` must be correct or the site may not build or link properly
- if a field is not used, deleting it is usually cleaner than leaving it empty
- `googlescholar` and `orcid` may be kept as optional fields, but they may also be deleted if the student does not have them

After saving the configuration changes, open the website URL and check whether the site loads correctly before moving on to the next step.

Example:

```text
https://yourusername.github.io/
```

GitHub interface example:

![GitHub Edit File Button](https://docs.github.com/assets/cb-47646/images/help/repository/edit-file-edit-button.png)

![GitHub Preview Changes Tab](https://docs.github.com/assets/cb-35434/images/help/repository/edit-readme-preview-changes.png)

---

## 9. Main Website Content

After the configuration is updated, the next step is to replace the template content with personal content.

Before editing individual pages, decide which pages the website should keep.

You do not need to keep every page included in the original template.

Recommended starter structure:
- `About`
- `Projects` or `Portfolio`
- `CV`

Optional pages:
- `Contact`
- `Research`
- `Publications`
- `Teaching`
- `Courses` or `Coursework`

Keep a page only if there is real content to put on it.

The instructor website may keep pages such as:
- `Publications`
- `Projects`
- `Teaching`
- `CV`

Students do not need to match that exact structure.

Choose pages based on the content you actually have. For example:
- keep `Projects` if you want to show coursework, portfolio items, or technical work
- keep `Teaching` only if you have tutoring, teaching assistant, instructor, or mentoring content
- keep `Publications` only if you have papers, posters, or research outputs to list
- keep `Courses` if you want to show relevant classes you completed, especially when building an early professional portfolio
- always keep `About`
- usually keep `CV`

If a template includes pages such as `Talks`, `Blog`, and those sections are not needed, the safest approach is:
1. remove them from `_data/navigation.yml` first
2. focus on updating the core pages
3. delete unused page files later if they are clearly unnecessary

This is usually better than deleting many files at the beginning.

### How to create a new page

If you want to add a new page such as `Projects`, `Contact`, `Research`, or `Publications`, create a new Markdown file in the `_pages/` folder.

Example file:

```text
_pages/projects.md
```

Basic page template:

```md
---
permalink: /projects/
title: "Projects"
author_profile: true
---

Write the page content here.
```

Procedure:
1. Open the repository on GitHub
2. Open the `_pages` folder
3. Click `Add file` and choose `Create new file`
4. Enter a file name such as `_pages/projects.md`
5. Paste the page template
6. Replace the title, permalink, and page content
7. Commit the file

After creating the page, add it to `_data/navigation.yml` if it should appear in the top menu.

Example:

```yaml
main:
  - title: "Projects"
    url: /projects/
```

Important note:
- creating a page file does not automatically add it to the navigation bar
- removing a page from `navigation.yml` hides it from the header, but the file may still exist in the site

### Summary: how to add or remove a page

To add a new page:
1. create a new Markdown file in `_pages/`
2. add front matter with `permalink`, `title`, and `author_profile`
3. write the page content
4. commit the file
5. add the page to `_data/navigation.yml` if it should appear in the top menu

To hide a page without deleting it:
1. open `_data/navigation.yml`
2. remove that page from the navigation list
3. commit the change

To fully delete a page:
1. remove the page from `_data/navigation.yml`
2. delete the corresponding file from `_pages/`
3. commit the change

Recommended approach:
- if you are unsure, hide the page first by removing it from `navigation.yml`
- delete the file later only when you are sure it is no longer needed

### Optional exercise: create a Courses page

For many students, a `Courses` or `Coursework` page can be useful. It helps visitors understand academic preparation, technical background, and areas of training.

Students may create a page that lists:
- course number and title
- semester
- grade
- a short 1 to 2 sentence description of the course content

Suggested exercise:
1. choose 3 to 6 courses most relevant to your goals
2. list the semester and grade for each course
3. add 1 to 2 sentences explaining what each course covered
4. keep the descriptions short, clear, and specific

Example:

```md
### DASC 5231: Data Visualization

**Semester:** Spring 2026  
**Grade:** A  

This course focused on principles of effective data visualization, visual communication, and practical visualization workflows.
```

Students who do not want to display grades may remove the grade line and keep the course descriptions.

Edit the following files:

#### `_pages/about.md`
This page is usually the first page visitors see, so the most important information should appear here first.

Use this file for:
- full name
- short biography
- current position and institution
- professional or research interests
- important links
- recent highlights or updates

Typical structure:

```md
---
permalink: /
title: "About Your Name"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I am ...
```

How to update it:
- keep the front matter at the top of the file
- replace the old template title with something clear such as `About Your Name`
- keep `permalink: /` if this page is the homepage
- replace the template text below the front matter with personal content
- if the page already shows the title automatically, the extra Markdown heading `# About` may be omitted

Recommended order for the homepage:
1. short professional introduction
2. collaboration or contact note
3. research interests
4. `News` section

Strong recommendation:
- add a `News` section to the About page
- this section helps visitors quickly see recent milestones such as graduation, a new position, publications, awards, invited talks, or ongoing projects
- a short reverse-chronological list is usually enough

Example:

```md
## News

- **2025**: Joined the University of Houston-Clear Lake as Assistant Professor of Data Science.
- **2025**: Earned a Ph.D. in Data Science from Bowling Green State University.
- **2025**: Paper accepted at ECML PKDD 2025.
```

#### `_pages/cv.md`
Use this file for:
- education
- experience
- skills
- a resume or CV summary

For most students, `Education` should be one of the first sections in the CV page.

Simple example:

```md
## Education

### University Name

**Degree:** M.S. in Data Science  
**Location:** Houston, Texas  
**Dates:** 2024-2026  
**Notes:** Expected graduation: May 2026

- Relevant coursework: Machine Learning, Data Visualization, Database Systems
- Optional achievement: GPA, scholarship, capstone project, or thesis topic
```

Suggested items to include:
- school name
- degree name
- location
- dates
- expected graduation if applicable
- relevant coursework
- optional honors, awards, thesis, or capstone information

Students may copy and edit the education template directly.

#### `_data/navigation.yml`
Use this file to control:
- the top navigation menu
- which pages appear in the header
- the order of menu items

#### `images/`
Use this folder for:
- profile photo
- other website images

#### `files/`
Use this folder for downloadable materials such as:
- CV PDF
- reports
- slides
- ZIP files

#### Portfolio or project content
Depending on the template version, project items are usually stored in:

```text
_portfolio/
```

If that folder is included in the template, each project is usually a separate Markdown file.

Additional files such as PDFs or ZIP files may be uploaded to the `files/` directory.

Example:

```text
https://yourusername.github.io/files/example.pdf
```

Important note:
- after each update, GitHub Pages may take about 1 to 5 minutes to rebuild and publish the latest version of the site
- changes may not appear immediately after a commit

---

## 10. Step 6: Check GitHub Pages Status

After the first changes are committed, check the GitHub Pages status in the repository settings.

Procedure:
1. Open `Settings`
2. Click `Pages`
3. Confirm that the site is building or already published

Important note:
- after each update, wait about 1 to 5 minutes for GitHub Pages to rebuild the site
- if the page does not update immediately, refresh again after a short delay

GitHub interface example:

![GitHub Repository Settings Tab](https://docs.github.com/assets/cb-28260/images/help/repository/repo-actions-settings.png)

---

## 11. Step 7: Optional Local Workflow

The repository may also be edited locally.

Basic commands:

```bash
git clone https://github.com/yourusername/yourusername.github.io.git
cd yourusername.github.io
```

After local edits:

```bash
git add .
git commit -m "Update website content"
git push
```

Image to add:
- Terminal screenshot after `git clone`

---

## 12. Step 8: Wait for Deployment

Each update triggers a GitHub Pages build.

Procedure:
1. Open the repository `Actions` tab or `Pages` settings
2. Wait for the build to complete
3. Open the site URL

Example:

```text
https://yourusername.github.io/
```

Image to add:
- Successful deployment screenshot

---

## 13. Optional: Markdown Generators

Some website templates include notebooks or scripts in a `markdown_generator` directory.

These tools can be used to generate Markdown files for items such as:
- publications
- talks
- presentations

This step is optional and is not required for the basic website setup.

---

## 14. Current Project Status

At the current stage:
- the GitHub account exists
- the template repository has been copied into a personal repository
- the site configuration has been updated
- the website is live

---

## 15. Next Phase

The next phase focuses on simplifying the existing website for long-term maintenance.

Planned structure:
- `About`
- `Projects`
- `CV`

Planned cleanup:
- remove unnecessary sections
- simplify the navigation bar
- clean `_config.yml`
- reduce the number of files that require routine editing

---

## 16. Key Takeaways

A basic professional portfolio website can be built with a small set of tools:
- a GitHub account
- an instructor-provided repository template
- a correctly named personal repository
- Markdown files for content
- GitHub Pages for publishing

The overall workflow centers on repository management, Markdown editing, and automated deployment rather than advanced frontend programming.
