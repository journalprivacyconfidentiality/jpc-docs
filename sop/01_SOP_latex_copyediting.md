# LaTeX submissions
LaTeX submissions should be using the `jpc.cls` class 
downloaded from [https://github.com/journalprivacyconfidentiality/jpc-style/releases](https://github.com/journalprivacyconfidentiality/jpc-style/releases).

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
## Step 0


Files should be in OJS as a ZIP file. 

- If the author has not uploaded a zip file yet: request it via the OJS communication; when it is received, upload to OJS

## Step 1

Create a Git repository private repository in the JPC Github https://github.com/journalprivacyconfidentiality for the manuscript, and add ALL the author's files to it (regardless of revision date).

- [Click here to create the repository](https://github.com/organizations/journalprivacyconfidentiality/repositories/new)
  - Use the `jpc-style` template
  - name of repository: `jpc-manuscript-###` where ### is the manuscript number. 
    - the manuscript number will be in the URL and nowhere else - e.g. `https://journalprivacyconfidentiality.org/index.php/jpc/workflow/index/666/3` would be 666, for instance. 
  - Check the "Private" option
  - <strike>Check the field "Initialize with a README"</strike>
  - Click "Create Repository"
- go into settings, "Manage access" and add the "Copyediting team" to the repository, and give it write permissions.
- Create an issue in the Git repo "Copyedit manuscript" (which should always be issue 1), and reference it in all commits (from command line, from Overleaf etc, by using `Re #1` in the message)
- Delete instructions and samples files.

## Step 2

Download the files from the Copyediting step in the journal system.
- Add ALL FILES to the repository (drag and drop) - remember to use the `re #1 ` in the commit message!
- Unzip the ZIP file
- Remove the redundant directory layer that is usually created by the unzipping (i.e., if the ZIP file "manuscript.zip" created the folder "manuscript/" with all files and directories in that folder, move all contents to the root folder, and delete the (now-empty) folder "manuscript/").

## Step 4

Create a  linked Overleaf v2 document

- https://www.overleaf.com/project
- New Project -> Import from GitHub
- You should see the linked JPC Github repositories. Pick the one you created in Step 1.
- Share it with the Managing Editors ( lars.vilhuber@cornell.edu and racheladcummings@gmail.com )



## Step 6

Add to the README not just the manuscript number, but once you've pulled it into Overleaf, add 
```
(URL) On Overleaf
```
where `(URL)` is the complete URL of the linked Overleaf document.


## Step 7: Copy-editing

### Preparing

- after the lines `\begin{document}`,add `\linenumbers`
-- Note: This generates an error in most files. Remove rather than acquiesce to error.
  
### Comparison to submitted file

1) Check Visuals
  - Check that all images and tables are formatted as in the submitted PDF
  - Check that all references resolve (no `(?)` in the generated PDF)
  - check for right-margin overflows (tricky!)
  - Check that the line `\title[]{This is a title}` does not have an empty `[]` - it should either have a short title (`\title[Shorter]{This is a title}`) or should be removed (`\title{This is a title}`)
  - Check the logs for errors
  - All references should have URLs and/or DOIs, regardless of style. If there are not URL or DOI, check the bib file, some styles don't show a URL. 
    - If unclear, make a ticket and assign to Lars. 
    - If absent, request that the author provide an updatd bib file with DOI (preferred) or URL.
2) Check Functionality
  - Check the URLs for validity - Check that all clickable links lead to a valid web page that seems reasonable for the paper. 
  - flag URLs that are not properly layoutted, and any other layout problems (fix, or make a Github issue)
3) Metadata (more is checked in the production stage) - JPC-platform and LaTeX file should match.
  - Check the article metadata for **funding** information, and cross-check with the manuscript (acknowledgements, title page, footnote) - fill in if necessary. All grant acknowledgements should be entered into the metadata (not all funders are in CrossRef, but those that are, should be entered in the "Funding" field with grant numbers)
  - Cross-check **Keywords** with any keywords given in the manuscript
  - Ensure that the **abstract** in the metadata is the same as in the article. If different, use the one from the article.

### Resolving issues
- Flag any issues with a "Github issue" for the Github repo
- If the generated PDF does NOT look like the submitted PDF (significant page changes, etc.), the manuscript should be returned to the authors. However, check with the Managing Editor first.
- If the generated PDF has issues/ corrections/ etc. that require feedback from the author
  - contact the author (through OJS - "add discussion"), providing the PDF with line numbers for review (and the option to edit on Overleaf if necessary): 
```
we've done the final version of the manuscript. There were some minor edits. 
Could you check that it looks good to you? Should you need to make any changes, please let us know 
with reference to line numbers, or we can share the Overleaf document with you.
```
   - if the author made substantial changes after you sent the copyedited version for approval, contact the managing editor.
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

### Special instructions for Special Issues

Special issues may use boxed inserts. The main manuscript file tex must be modified (this does NOT work when inserting Word-derived PDFs!). There is a special `jpcboxed.tex` in the editorial files for this purpose.

#### Add the following line BEFORE the start of the document
```
\input{jpbboxed.tex}
```

#### Add the following line in an appropriate location of the text

```
%\begin{wrapfigure}{r}[0pt]{6in}
\begin{figure}[H]
\begin{cornerbox}[width=\linewidth]\small\fontfamily{qag}\selectfont

\input{Fienberg.tex}

\hfill \it Alan Karr
\end{cornerbox}
\end{figure}
%\end{wrapfigure}
```
Check the layout, and move the location around as necessary. 

- when moving from copy-editing to production, double-check that Abstract, Title, Keywords, Grant numbers are in sync between document and metadata.

## Wrap-up

Once everything looks clean and the authors have approved any changes, 
- make a sync from Overleaf to Github!
- close all copyediting "issues" in Github 
- download the PDF from Overleaf
- Upload the PDF to Github with a commit or upload message that says, for example, "This is the copy-edited file uploaded to OJS on March 5, 2019".
- create a **release** or **tag** on Github, calling it 'copyedited'
- upload the PDF as the final copyedited file back into OJS (under "Copyedited"). Note: anytime you upload/update the document on OJS, create a related release on Github.
-  Notify the Editor that all files have been prepared, and that the Production process may begin, by responding to the original copy-editing request message in the Copyediting Discussion panel. Specifically mention all closed Github issues.
-  Once moved to production, assignee should post the message "All done." in the original copyediting request and mark the discussion as "Closed."

## Production

Once the manuscript has been moved to production, check the following metadata (this requires production editor permissions). 

Move to the "Production" tab and find the list of contributors.
- Do a cursory check if the authors are in **ORCID**, and enter the ORCID ID. If not present, check the box: “Send e-mail to request ORCID authorization from contributor”
- All authors should have an **affiliation**, and at least one author should have an email address.
  - Check that the affiliation is consistent with the affiliation on the PDF.

## Finish this step
Go to [02 SOP Latex Galley](02_SOP_latex_galley.md).
