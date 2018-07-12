# Word submissions
Word submission should comply with the layout instructions at https://journalprivacyconfidentiality.org/index.php/jpc/about/submissions. For publishing at JPC, the Word document, properly formatted, will be printed to PDF, and then included in a LaTeX "wrapper".

# Preparing the Word document

The key elements that the Word document need to satisfy are
- font type and size
- border size (very important)
- no page numbers, footers, or headers

Finally, remove any title page and abstract. The document should start with the first section. Save as "manuscript-###-copyedit.docx". Then print the document to a PDF, with the same name.

# Preparing the final manuscript

## Step 1
Create a Git repository private repository in the JPC Github for the manuscript, and add to it the author's original Word document(s), the modified Word document, and the PDF created from the Word document.

- https://github.com/journalprivacyconfidentiality
- name of repository: `jpc-manuscript-###`

where ### is the manuscript number.

Adding files can be done through drag-and-drop on Github.

## Step 2
Add the editorial supplementary files ([source](https://github.com/journalprivacyconfidentiality/jpc-style/releases/tag/v091jpc-editorial)) to the repository.

Adding files can be done through drag-and-drop on Github.

Caution: you need to retain the directory structure! Do not drag-and-drop the ZIP file, only its contents.

## Step 3
Create a  linked Overleaf v2 document

- https://v2.overleaf.com/project
- New Project -> Import from GitHub
- You should see the linked JPC Github repositories. Pick the one you created in Step 1.

## Step 4
In the Overleaf interface, change the top of the `template-word.tex` file by ensuring it contains the following lines (note the comments):

```
\documentclass{jpcfinal} %%% last changed 2014-08-20

% JPC Layouting Macros =========================================
% THESE ARE ADDED BY THE EDITORIAL TEAM - NO NEED TO SET HERE
\newcommand{\doisuffix}{v0.i0.999}
% \jpcheading{vol}{issue}{year}{notused}{subm}{publ}{rev}{spec_iss}{title}
\jpcheading{0}{0}{2000}{}{Mar.~20, 2017}{Jun.~22, 2018}{}{Special issue}
%%% last changed 2018-06-29 =====================================
```
The DOI will be determined once the article is assigned to an issue by the Managing Editor. For now, this should simply be checked for clean compilation.

Next, find the section about keywords, and add keywords:
```
%% mandatory lists of keywords
\keywords{MANDATORY list of keywords}
```

Next, find the title and author information:

```
\begin{document}

\title[Instructions]{Instructions for Authors:\\How to prepare papers
  for JPC using \MakeLowercase{\texttt{jpc.cls}}\rsuper*\\
  2018-06-20}
\titlecomment{{\lsuper*}OPTIONAL comment concerning the title, \eg,
  if a variant or an extended abstract of the paper has appeared elsewhere.}

\author[A.~Name1]{Alice Name1}	%required
\address{address 1}	%required
\email{name1@email1}  %optional
%\thanks{thanks 1, optional.}	%optional

\author[B.~Name2]{Bob Name2}	%optional
\address{address2; addresses should initially be duplicated, even if
  authors share an affiliation}	%optional
\email{name2@email2; ditto for email addresses}  %optional
\thanks{thanks 2, optional.}	%optional

\author[C.~Name3]{Carla Name3}	%optional
\address{address 3}	%optional
\urladdr{name3@url3\quad\rm{(optionally, a web-page can be specified)}}  %optional
\thanks{thanks 3, optional.}	%optional
```
and adjust to match the Word document.

Next, find the line
```
\includepdf[pages=-,offset=0 0.7in,pagecommand={}]{sample-word.pdf}
```
and change `sample-word.pdf` to `manuscript-###-copyedit.pdf` (which you created at the very top).

The document should now be compiled, and verified.
