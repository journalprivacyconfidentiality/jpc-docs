# LaTeX submissions
LaTeX submissions should be using the `jpc.cls` class from
downloaded from [https://github.com/journalprivacyconfidentiality/jpc-style/releases](https://github.com/journalprivacyconfidentiality/jpc-style/releases) or as a template on [Overleaf.com](https://www.overleaf.com).

This means that the top of the document will contain the following lines:

https://github.com/journalprivacyconfidentiality/jpc-style/blob/7a97f43817b14df602172f03e435a94f7edbf790/instructions.tex#L1-L12

```
\documentclass{jpc} %%% last changed 2014-08-20


% JPC Layouting Macros
% THESE ARE ADDED BY THE EDITORIAL TEAM - NO NEED TO SET HERE
%\newcommand{\doisuffix}{999}
% \jpcheading{vol}{issue}{year}{notused}{subm}{publ}{rev}{spec_iss}{title}
%\jpcheading{0}{0}{2000}{}{Mar.~20, 2017}{Jun.~22, 2018}{}{Special issue}
%%% last changed 2014-08-20


%% mandatory lists of keywords
\keywords{MANDATORY list of keywords}
```

## Step 1
Create a Git repository private repository in the JPC Github https://github.com/journalprivacyconfidentiality for the manuscript, and add ALL the author's files to it (regardless of revision date).

- [Click here to create the repository](https://github.com/organizations/journalprivacyconfidentiality/repositories/new)
  - Use the `jpc-style` template
  - name of repository: `jpc-manuscript-###` where ### is the manuscript number. 
    - the manuscript number will be in the URL and nowhere else - e.g. `https://journalprivacyconfidentiality.org/index.php/jpc/workflow/index/666/3` would be 666, for instance. 
  - Check the "Private" option
  - <strike>Check the field "Initialize with a README"</strike>
  - Click "Create Repository"
- go into settings, "Collaborators & Teams" and add the "Copyediting team" to the repository, and give it write permissions.
- Create an issue in the Git repo "Copyedit manuscript" (which should always be issue 1), and reference it in all commits (from command line, from Overleaf etc, by using `Re #1` in the message)

## Step 2
Download the files from the Copyediting step in the journal system (exceptionally, this might be the Review stage).
- Add ALL FILES to the repository (drag and drop) - remember to use the `re #1 ` in the commit message!
- if the author has not uploaded a zip file: request it; when it is received, upload to OJS as well as to GitHub as below.
- rename the files to their original names! (consult the journal system - should no longer be necessary if coming as ZIP files)
  - Exception: the manuscript itself (e.g. `655-Manuscript (PDF)-712-1-6-20180308.pdf`) should remain unchanged

## Step 3
Add the editorial supplementary files ([v091.4jpc-editorial](https://github.com/journalprivacyconfidentiality/jpc-style/releases/tag/v091.4jpc-editorial) or later **editorial** files) to the repository.

- Caution: you need to retain the directory structure! 
- Adding files can be done through drag-and-drop on Github.
- Do not drag-and-drop the ZIP file, only its contents.

From the ZIP file, unzip and move only the following: 
- the `tmpl-images`  folder
- `jpc.cls` (if not already present)
- `jpsfinal.cls`

## Step 4
Create a  linked Overleaf v2 document

- https://www.overleaf.com/project
- New Project -> Import from GitHub
- You should see the linked JPC Github repositories. Pick the one you created in Step 1.
- Share it with the Managing Editor ( lars.vilhuber@cornell.edu )



## Step 6
Add to the README not just the manuscript number, but once you've pulled it into Overleaf, add 
```
(URL) On Overleaf
```
where `(URL)` is the complete URL of the linked Overleaf document.


## Step 7: Copy-editing

### Preparing
- after the lines `\begin{document}`,add `\linenumbers`
  
### Comparison to submitted file
1) Check Visuals
  - Check that all images and tables are formatted as in the submitted PDF
  - Check that all references resolve (no `(?)` in the generated PDF)
  - check for right-margin overflows (tricky!)
  - Check that the line `\title[]{This is a title}` does not have an empty `[]` - it should either have a short title (`\title[Shorter]{This is a title}`) or should be removed (`\title{This is a title}`)
  - Check the logs for errors
2) Check Functionality
  - Check the URLs for validity - Check that all clickable links lead to a valid web page that seems reasonable for the paper. 
  - flag URLs that are not properly layoutted, and any other layout problems (fix, or make a Github issue)
3) Metadata
  - Check the article metadata for **funding** information, and cross-check with the manuscript (acknowledgements, title page, footnote) - fill in if necessary. All grant acknowledgements should be entered into the metadata (not all funders are in CrossRef, but those that are, should be entered in the "Funding" field with grant numbers)
  - Cross-check **Keywords** with any keywords given in the manuscript
  - all authors have an **affiliation**, at least one author should have an email address
    - Check that the affiliation is consistent with the affiliation on the PDF
  - do a cursory check if the authors are in **ORCID**, and enter the ORCID ID
  - Ensure that the **abstract** in the metadata is the same as in the article. If different, use the one from the article.

### Resolving issues
- Flag any issues with a "Github issue" for the Github repo
- If the generated PDF does NOT look like the submitted PDF (significant page changes, etc.), the manuscript should be returned to the authors. However, check with the Managing Editor first.
- If the generated PDF has issues/ corrections/ etc. that require feedback from the author
  - contact the author (through OJS), providing both the PDF with line numbers, and the option to edit on Overleaf
  - upload the PDF as part of the "Copyediting discussions"
- If the generated PDF looks like the submitted PDF (or as authorized by the author), 
  - make a sync from Overleaf to Github
  - create a **pre-release** on Github (Release tab), with tag name "manuscript", title of the repository, and note "This should match the user's manuscript"

### Final layouting
 In the Overleaf interface, Change the top of the AUTHOR's primary file by ensuring it contains the following lines (note the comments):

(the copyedited version should be draft (the default for jpcfinal.cls), the production version should be feasibly enabled, no further mods, by just setting [final].)

```
\documentclass[final]{jpcfinal} %%% last changed 2014-08-20
\usepackage{lineno}
% JPC Layouting Macros =========================================
% THESE ARE ADDED BY THE EDITORIAL TEAM - NO NEED TO SET HERE
\newcommand{\doisuffix}{999}
% \jpcheading{vol}{issue}{year}{notused}{subm}{publ}{rev}{spec_iss}{title}
\jpcheading{0}{0}{2000}{}{Mar.~20, 2017}{Jun.~22, 2018}{}{Special issue}
%%% last changed 2018-06-29 =====================================
```
The DOI suffix is the manuscript number. The `{subm}` entry should be determined from the editorial history. `{publ}` (published) will be determined once the article is assigned to an issue by the Managing Editor. 

The document should compile cleanly. 

## Wrap-up

Once everything looks clean, 
- make a sync from Overleaf to Github
- download the PDF from Overleaf
- Upload the PDF to Github with a commit or upload message that says, for example, "This is the copy-edited file uploaded to OJS on March 5, 2019".
- create a **release** on Github, calling it 'copyedited'
- upload the PDF as the final copyedited file back into OJS (under "Copyedited"). Note: anytime you upload/update the document on OJS, create a related release on Github.


## Finish this step
Go to [02 SOP Latex Galley](02_SOP_latex_galley.md).
