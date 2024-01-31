# Description of Template
The template is served for private math homework writing, and I upgraded some existed environments so that it is specialized and suits my own writing habit better.

I don't really like vaious colorful fancy `tcolorbox`es, so propositions, theorems, lemmas and corollaries are just plain text without highlighted using various colors, though I did use some not-that-fancy colorboxes for `extension` and `remark` environments.

# Strongpoints
The template includes some improved environments.
- Solution environments (differed by whether the line is skipped after `Solution.`, before the content.)
  - `soln` serves for problems that have different parts, so it would be better and looks like
   ```
  Solution.
  (a) ...
  (b) ...
   ```
  - `solution` serves for problems that only have one part, which would be like
    ```
    Solution. I claimed that ...
    ```
  These two environments are done with the following code:
  ```
  %%% Reference: https://tex.stackexchange.com/questions/85059/proof-environment-line-break-after-the-proof
  \newenvironment{myproof}[1][\proofname]{\par
    \pushQED{\qed}%
    \normalfont \topsep6\p@\@plus6\p@\relax
    \trivlist
    \item[\hskip\labelsep
        \itshape
        #1\@addpunct{.} ]\mbox{}\par\nobreak}
    {\popQED\endtrivlist\@endpefalse}
  \makeatother

  \newenvironment{soln}[1][Solution]{%
  \begin{myproof}[#1] }%
  {\end{myproof}}
  \makeatother


  \newenvironment{solution}[1][Solution]{
  \begin{proof}[Solution][#1]}{\end{proof}}
  ```
- `subproof`, `subsubproof` for proof inside solution and lemmas, differed by different qed symbols, including `\clubsuit` and `\blacksquare`, done by the following code:
```
\newenvironment{subsubproof}[1][Proof]{%
\begin{proof}[#1] \renewcommand{\qedsymbol}{$\clubsuit$}}%
{\end{proof}}
\newenvironment{subproof}[1][Proof]{%
\begin{proof}[#1] \renewcommand{\qedsymbol}{$\blacksquare$}}%
{\end{proof}}
\makeatletter
```
- Directly using `\section{}` to show Problem #1, 2, 3, ... (can be directly shown in the table of content, as an advantage comparing to `\section*{Problem \#1}`)
```
\titleformat{\section}
    {\normalfont\Large\scshape}
    {Problem \#\thetitle}
    {0em}
    {}

\titlecontents
    {section}                       % which level does it apply to, e.g. chapter, section, ...
    [1in]                           % left margin
    {}                              % code executed before the tocline
    {Problem \#\thecontentslabel}  % format for numbered entries
    {Problem \#\thecontentslabel}  % format for unnumbered entries
    {\titlerule*[0.5pc]{$\cdot$}\contentspage\hspace*{1in}}                              % format for filler page
    []
```

- Using `tcolorbox` for `remark` and `extension` environment (though if a pagebreak exists in the middle, it seems to work not quite well, feel free to report issues and improvement method!)
```
\newenvironment{remark}[1][\textbf{Remark}]{\begin{tcolorbox}[enhanced, coltitle=black, frame code={\path[draw=black, line width=2pt]
  ([yshift=-4.5pt]frame.north west) -- ([yshift=10pt]frame.south west);}, colback=white, adjusted title=#1, left=8pt, right=8pt, breakable=true]}{\end{tcolorbox}}

\newenvironment{extension}[1][\textcolor{blue}{\textbf{Extension}}]{\begin{tcolorbox}[enhanced, coltitle=black, frame code={\path[draw=blue, line width=2pt]
    ([yshift=-4.5pt]frame.north west) -- ([yshift=10pt]frame.south west);}, colback=white, adjusted title=#1, left=8pt, right=8pt, breakable=true]}{\end{tcolorbox}}
```
- Add `claim` and `conclusion` environments
```
\newenvironment{conclusion}{{\medskip}
\noindent
\textbf{Conclusion.}}{{\medskip}}

\newenvironment{claim}{{\medskip}
\noindent
\textbf{Claim.}}{{\medskip}}
```

# Example Compiled Result
![image](https://github.com/PLASTA0728/Math-Homework-Problem-Set-Template/assets/121154397/a2963b8c-cbf6-4261-9658-84beb7345bed)
