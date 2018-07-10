# LaTeX submissions
LaTeX submissions should be using the `jpc.cls` class from
downloaded from [https://github.com/journalprivacyconfidentiality/jpc-style/releases](https://github.com/journalprivacyconfidentiality/jpc-style/releases) or as a template on [Overleaf.com](https://www.overleaf.com).

This means that the top of the document will contain the following lines:

https://github.com/journalprivacyconfidentiality/jpc-style/blob/7a97f43817b14df602172f03e435a94f7edbf790/instructions.tex#L1-L12

```
\documentclass{jpc} %%% last changed 2014-08-20


% JPC Layouting Macros
% THESE ARE ADDED BY THE EDITORIAL TEAM - NO NEED TO SET HERE
%\newcommand{\doisuffix}{v0.i0.999}
% \jpcheading{vol}{issue}{year}{notused}{subm}{publ}{rev}{spec_iss}{title}
%\jpcheading{0}{0}{2000}{}{Mar.~20, 2017}{Jun.~22, 2018}{}{Special issue}
%%% last changed 2014-08-20


%% mandatory lists of keywords
\keywords{MANDATORY list of keywords}
```

## Step 1
Create an Git repository private repository in the JPC Github for the manuscript, and add the author's files to it.

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
In the Overleaf interface, Change the top of the AUTHOR's primary file by ensuring it contains the following lines (note the comments):

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
