---
title: "Paper Writing and Mathematical Notation"
date: 2024-08-24
---

Paper writing is one of the most important skills for graduate students. You need to convey all of the important ideas to readers and reviewers who, more likely than not, don't have much time. Mathematical notation is one of the most important ways of getting your ideas across precisely, but if you don't plan it carefully, you run the risk of violating the Geneva Convention. These are some tips to minimize the suffering of the readers.

### When possible, use LaTeX instead of Word.

LaTeX is a type-setting system that is particularly useful for papers that include math. It has a learning curve but in my experience it is superior to Word documents.
- It is much easier to write math equations using LaTeX.
- You don't have to worry about your document formatting getting messed up when you open a file on a different computer.
- You can control almost anything in the layout. There is a lower chance of mysterious surprises with LaTeX than with Word.

  My preference (and that of many academics) is to use [Overleaf](https://www.overleaf.com/), an online LaTeX editor that allows you to collaborate with multiple people and no additional software is required beyond a web browser.

### A table of notation.

Papers introduce notation all over the place. It is very easy to forget what a symbol means, and when you do, it very difficult to go back to find where the symbols was defined. Many times, when I review papers, I dream of quitting and taking up easier jobs, like searching for needles in haystacks. You, as a writer, can help the readers out by creating a table of notation and either putting it in the main paper or in the supplementary material. An example of LaTeX code:
```
\begin{table}[h]
\begin{center}
\caption{Table of Notation}\label{tab:notation}
\begin{tabular}{|cp{0.73\linewidth}|}\hline
$N$: & Population size\\
$n$: & Sample size\\
$\mathbf{W}_i$: & Parameters for Neural Network layer i\\
$K$: & A compact subset of a metric space\\
$\mathcal{A}$: & A randomized algorithm.\\
\hline
\end{tabular}
\end{center}
\end{table}
```
and then the reader gets a handy reference like this:
![Screenshot of a table of notation produced by LaTeX code](https://dkifer.github.io/blog/docs/assets/images/tableofnotation.png)


### Useful strategies in LaTeX.

### Reminders.

### Tips for slides and presentations.
