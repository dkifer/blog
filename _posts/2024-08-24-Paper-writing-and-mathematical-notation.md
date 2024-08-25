---
title: "Paper Writing and Mathematical Notation"
date: 2024-08-24
---

Paper writing is one of the most important skills for graduate students. You need to convey all of the important ideas to readers and reviewers who, more likely than not, don't have much time. Mathematical notation is one of the most important ways of getting your ideas across precisely, but if you don't plan it carefully, you run the risk of violating the Geneva Convention. These are some tips to minimize the suffering of the readers.

## When possible, use LaTeX instead of Word.

LaTeX is a type-setting system that is particularly useful for papers that include math. It has a learning curve but in my experience it is superior to Word documents.
- It is much easier to write math equations using LaTeX.
- You don't have to worry about your document formatting getting messed up when you open a file on a different computer.
- You can control almost anything in the layout. There is a lower chance of mysterious surprises with LaTeX than with Word.

  My preference (and that of many academics) is to use [Overleaf](https://www.overleaf.com/), an online LaTeX editor that allows you to collaborate with multiple people and no additional software is required beyond a web browser.

## A table of notation.

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


## Useful strategies in LaTeX.

As you write your paper, you may realize that suddenly you need to change your notation. For example, suppose you used $\alpha$ for an important algorithm parameter, but then you realize that you also need to discuss hypothesis testing, where $\alpha$ is commonly used to denote a significance level. Now you need to go back and change your $\alpha$ to some other symbol. If your notation is more complicated, or hard to search for (like you used the letter c, but then realized you also need to discuss the speed of light, which is also denoted by c), this becomes a nightmare. 

A similar problem happens when you need to change your terminology. For example, your paper may be proposing a new system that was tentatively named ALLY (**A** Rea**L**ly Coo**L** S**Y**stem) but then you realize that such acronyms are word crimes, and want to rename it to Waldo. You could either search and replace everywhere, or you could do the following.

In the pre-amble of the LaTex document (usually I put it into a separate file):
```
{% raw %}
\usepackage{xspace}
\def\notationcolor{blue}
\newcommand{\notation}[2]{\newcommand{#1}{{\textcolor
{% endraw %}
```
Then to define a new piece of notation, add code like this to the preamble (make sure to add comments in the LaTeX so that you don't forget the notation!):
```
\notation{\popsize}{N} % population size
\notation{\nnparam}{\mathbf{W}} % neural network parameters
```
and to define a term (like system name):
```
\term{sysname}{Waldo}
```

The benefit of using these macros, is that if you want to change your notation or terminology, there is just one place you need to make the change. 

These macros make your notation blue, so that you can easily spot parts of your paper where you forgot to use the macros. Before submitting the paper, you can change the color from blue to black.

## Reminders.

Even with a table of notation, it is not convenient to keep flipping back to it. So, another good practice is to add reminders whenever you use the symbols. For example:

*As we can see from Equation 342, as the second largest eigenvalue of the network parameter matrix $\nnparam$ goes to 1 and population size $\popsize$ goes to infinity, ...*

is so much more readable than:

*As we can see from Equation 342, as the second largest eigenvalue of $\nnparam$ goes to 1 and $\popsize$ goes to infinity, ...*

especially when your notation involves lots of superscripts, subscripts, and other decorations.

## Tips for slides and presentations.

When you are giving presentations, notation is an even bigger problem. The audience is **more likely** to forget the notation because someone keeps talking while they try to remember it. The audience also has no ability to flip back to a table of notation, and if they blink, they might not even see some of it.

So, whenever possible, use pictures and small examples instead of notation. You can, of course, have a slide that with notation and a theorem to prove that your results generalize beyond the small example, but the main focus of your presentation is the small example.

Here are some examples of these points. The first is a picture I used to discuss data swapping. Even though it is a crude drawing it is better than introducing variables for geographic locations, household records, etc.

<!-- ![Amateurish illustration of data swapping](https://dkifer.github.io/blog/docs/assets/images/swapping.png) -->
<img src="https://dkifer.github.io/blog/docs/assets/images/swapping.png" height="400"/>

This next example is from a JSM talk by [Kaitlyn Webb](https://sites.psu.edu/krdowden/). It uses both a small numerical example and pictures (emojis) in place of variables. Note that the emojis are not gratuitous, they have a real purpose in making information stand out visually.
![Example and emojis](https://dkifer.github.io/blog/docs/assets/images/emoji.png)
