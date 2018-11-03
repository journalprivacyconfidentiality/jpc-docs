## Upload to copyediting
- upload the copyedited file from the previous step to JPC website
- Contact author through the JPC system ("add discussion") and attach the copyedited file (with linenumbers) for review:
```
we've done the final version of the manuscript. There were some minor edits. 
Could you check that it looks good to you? Should you need to make any changes, please let us know 
with reference to line numbers, or we can share the Overleaf document with you.
```
- Don't forget to attach the manuscript

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

## Creating the final galleys
`Galley` is the term used for the PDF that will show up in the final, published form. It differs from the copy-edited form only in minor details:
- ensure that `jpcfinal.cls` is being used
- add the DOI suffix - it is simply `jpc.` followed by the manuscript number, e.g. `jpc.999`. So the top of the LaTeX should now read
```
% THESE ARE ADDED BY THE EDITORIAL TEAM - NO NEED TO SET HERE
\newcommand{\doisuffix}{jpc.661}
% \jpcheading{vol}{issue}{year}{notused}{subm}{publ}{rev}{spec_iss}{title}
\jpcheading{8}{1}{2018}{}{Mar.~20, 2017}{Nov, 2018}{}{Special Halloween Issue}
```
- compile the PDF in Overleaf
- commit to Github
- Download the manuscript (which should be called `jpc-manuscript-NNN.pdf`) from Overleaf, and upload it as galley in the JPC manuscript system.
- Notify the Managing Editor
