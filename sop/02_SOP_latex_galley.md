## Upload to copyediting
- upload the copyedited file from the previous step to JPC website under the "Copyedited" section at the bottom. 
- Contact author through the JPC system ("add discussion") and attach the copyedited file (with linenumbers) for review:
```
we've done the final version of the manuscript. There were some minor edits. 
Could you check that it looks good to you? Should you need to make any changes, please let us know 
with reference to line numbers, or we can share the Overleaf document with you.
```
- Don't forget to attach the manuscript

## When all changes approved by author
- close all copyediting "issues" in Github 
- In "Copyediting discussions", reply to the copyediting request of the editor to mention that the copyediting is finished. Specifically mention all closed Github issues.
- all Github/Overleaf files MUST be in sync
- if the author made substantial changes after you sent the copyedited version for approval, contact the managing editor

## Special instructions for Special Issues
Special issues use boxed inserts. The main manuscript file tex must be modified (this does NOT work when inserting Word-derived PDFs!). There is a special `jpcboxed.tex` in the editorial files for this purpose.

### Add the following line BEFORE the start of the document
```
\input{jpbboxed.tex}
```

### Add the following line in an appropriate location of the text

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

## Creating the final galleys
- do this only once Lars has moved the submission to production in OJS. 
`Galley` is the term used for the PDF that will show up in the final, published form. It differs from the copy-edited form only in minor details:
- ensure that `jpcfinal.cls` is being used
- make sure the DOI suffix ( `jpc.`) is followed by the manuscript number, e.g. `jpc.999` in the pdf document. The top of the LaTeX should read (jpc suffix is added automatically)
```
% THESE ARE ADDED BY THE EDITORIAL TEAM - NO NEED TO SET HERE
\newcommand{\doisuffix}{661}
% \jpcheading{vol}{issue}{year}{notused}{subm}{publ}{rev}{spec_iss}{title}
\jpcheading{8}{1}{2018}{}{Mar.~20, 2017}{Nov, 2018}{}{Special Halloween Issue}
```
- compile the PDF in Overleaf
- commit to Github
- Download the manuscript (which should be called `jpc-manuscript-NNN.pdf`) from Overleaf, and upload it **as galley** in the JPC manuscript system. Label the document `PDF`. Remember to create a corresponding release in Github, labeled final version.
- Notify the Managing Editor
