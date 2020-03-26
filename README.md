# Oxford code reviews network
Want to get  your code reviewed?
Interested in reviewing some other researcher's code ?

This repository acts as a central place for organising code reviews in the University of Oxford.
If you'd like your code to be reviewed by someone else, simply open an issue with a brief description of your code (language and context).
If you'd like to volunteer in reviewing some research code, you can just comment on the corresponding issue and register your interest!

If you'd like to participate but are not familiar with GitHub or/and its issue tracking system, see the [getting started section](#gettingstarted).

the next two section describe what are code reviews and why they're valuable.
If you are already familiar with the concept of a code review, feel free to jump to the [guidelines](#guidelines).
## What is a code review

A code review is simply the action of having a deep and critical look into somebody else's code.
This is common practice in the software industry, and more generally in the open source software development community, but still very
rarely happen in academia.
Typically, the author of the code sits down with one or several colleagues and walks them through the code, explaining design choices and implementation details.
the role of reviewers is to try to identify potential issues, but also highlight and encourage the use of software good practices.

## Why code reviews?

A common saying in the software world is that the average number of bugs introduced per 1000 lines of code is around 15.
Although such metric isn't probably reliable, it illustrates the fact that **software almost never comes out perfect**, and that fixing bugs and issues is part of the software development process.
This is true in industry, and this is true in academia.

By allowing your code to be reviewed, your make possible for a fresh pair of eyes to have a look around and detect potential flaws that you would never have imagined.
Having someone external to the project is also a great way of fixing bugs or understanding errors, as it forces the author to **explain the problem to someone that is unfamiliar with the code**.
Furthermore, several people can often come up with different solutions to a given problem, and may have widely different use of the same programming language
As a reviewer, you also have a lot to gain from this process, as it is likely that you will come across programming concepts and practices that are completely new to you.
Whether you are a seasoned programmer or a beginner, reviewing code is a great way of developing, sharpening and widening your programming skills!

## <a name="guidelines"></a> Code review guidelines

**Covid-19 pandemic: All code reviews must be executed remotely until further notice.**
**See [remote code reviews](remote.md) for advice about carrying out remote code reviews**

### Format
Ideally, the code review is carried out face to face, the developer and reviewer sitting together.
If not possible, you can [do code reviews remotely](remote.md).

### Location
The location of the code review (or the tool used for the remote meeting) is left to the author and reviewer to decide upon.

### Duration
It is recommended to keep the code review sessions relatively short (two hours maximum), as it can be a tiring exercise for both parties!
For most projects, this means only proposing a **part of you code** for review.

## <a name="gettingstarted"></a> Getting started
Make sure you're logged into your GitHub account. If you don't have a GitHub account, you can [create one](https://github.com/join?source=login) for free.
> The term _issue_ comes from the word _issue tracker_ (the functionality that you are about to use), use by software developpers to report and discuss bugs and problems. However, the issue tracker can be used for any thing, such as 
> proposing you code review.

### Propose a code review
1. If you want to propose a code review, you must first _open an issue_.
At the top of this page, under "**OxfordCodeReviewNet**/**forum**", click on _Issues_.
Here's an illustration from another repository "octo-repo".
![open issue illustration](https://help.github.com/assets/images/help/repository/repo-tabs-issues.png "Logo Title Text 1")
2. You can then create a new issue by clicking the green button _New issue_ on the top right of the screen.
The issue comes pre-filled with some place-holder content, feel free to replace it by a description that corresponds to your code.

### Find a code to review
The browse current review opportunities, simply browse the issues by clicking on the _Issues_ tab (see previous section).
If you're interested in reviewing a particular code, simply click on the corresponding issue and write a comment!
