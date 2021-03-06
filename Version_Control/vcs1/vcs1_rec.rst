---------------------------------
Version Control using Hg Part I 
---------------------------------

.. Prerequisites
.. -------------

.. None

.. Author : Primal Pappachan
   Internal Reviewer : Kiran Isukapatla
   Date: Jan 27, 2012

----------------------
Spoken Tutorial Script
----------------------



+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{ Show the first slide containing title, name of the production team along    | Hello friends and welcome to the first part of tutorial on 'Version Control      |
| with the logo of MHRD}}}*                                                        | using Hg'                                                                        |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the slide containing the objectives}}}*                                 | At the end of this tutorial you will be able to                                  |
|                                                                                  |                                                                                  |
|                                                                                  |  1. Understand what is Version Control                                           |
|                                                                                  |  #. Identify the need for using Version Control                                  |
|                                                                                  |  #. Install Mercurial and intialize a repository                                 |
|                                                                                  |                                                                                  |
|                                                                                  |                                                                                  |
|                                                                                  | First, let's understand what 'Version Control' is.                               |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the slide 'what is version control'}}*}                                 | 'Version control' is a way to track files over time and share them. This allows  |
|                                                                                  | access to earlier versions of a file(s) if and when required. It therefore       |
|                                                                                  | enables us to make changes to the content of a file, view it's change log and    |
|                                                                                  | collaborate on a single piece of work with a team of people.                     |
|                                                                                  |                                                                                  |
|                                                                                  | As the quote from the famous blog post 'Version Control for masses' says         |
|                                                                                  |                                                                                  |
|                                                                                  | "Version control is one of those weird, geeky things that never really gained    |
|                                                                                  |   much ground in non-geek fields, despite the fact that it’s blindingly useful." |
|                                                                                  |                                                                                  |
|                                                                                  | Over the course of these 3 spoken tutorials, we are going to see a handful of    |
|                                                                                  | such things, which are widely used in the programmer world, but not so much in   |
|                                                                                  | the scientific computing world, even when if they would be very useful.          |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the slide 'Home-brewed'}}}*                                             | Let's look at an example of home-brewed Version Control system                   |
|                                                                                  |                                                                                  |
|                                                                                  | Version control is a way of backing up files, before making changes. Most        |
|                                                                                  | people would have cooked up their own version control system, without            |
|                                                                                  | realizing, there were tools built by others, that performs the task in a more    |
|                                                                                  | organized and systematic way.                                                    |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the slide 'Problems'}}}*                                                | Let's look at the various problems associated with this set-up.                  |
|                                                                                  |                                                                                  |
|                                                                                  |  1. Name and changes made are not related or linked.                             |
|                                                                                  |  #. Can't track sequence of changes made to a file                               |
|                                                                                  |  #. Does not scale                                                               |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the slide 'The need for Version Control'}}}*                            | Having seen the problems of a home brewed setup, let's now move onto             |
|                                                                                  | identifying the needs for a 'Version Control System'.                            |
|                                                                                  |                                                                                  |
|                                                                                  |  1. To err is Human . . .                                                        |
|                                                                                  |  #. Tracking the history and evolution of a project                              |
|                                                                                  |  #. To collaborate effectively on a project                                      |
|                                                                                  |  #. To efficiently track down bugs and pin-point the                             |
|                                                                                  |  #. changes that caused it                                                       |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the slide 'The need for Version Control'}}}*                            | We have seen that one of the main motivations to use a Version Control system    |
|                                                                                  | is the ability to go back to a working version of a file, when something goes    |
|                                                                                  | wrong. Below are a few more advantages of using an automated version control     |
|                                                                                  | system.                                                                          |
|                                                                                  |                                                                                  |
|                                                                                  | 1. By tracking the history of a project, any person may see the evolution of a p |
|                                                                                  | 2. Allows for effective collaboration on a project, as everything is shared.     |
|                                                                                  | 3. Helps to identify which additions have broken down a project and thus aids in |
|                                                                                  | 4. It is good for a one man show as it is for a big group of people working on a |
|                                                                                  |                                                                                  |
|                                                                                  | Keeping your stuff version controlled will help avoid accidental deletion of     |
|                                                                                  | individual files etc. Hosting it on a remote server will protect your sanity     |
|                                                                                  | from a hard disk crash.                                                          |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the slide 'How does it work? - Analogy}}}*                              | It is, in some ways, similar to playing a video game. We generally play games    |
|                                                                                  | in stages. While playing, we save the game at some instances as per our choice.  |
|                                                                                  | We continue playing, but we could, if necessary, choose to go back to one of     |
|                                                                                  | the saved states and start over. In this manner, we could change the course of   |
|                                                                                  | the game.                                                                        |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the slide 'Mercurial or hg'}}}*                                         | Some of the Version Control tools available and used widely are:                 |
|                                                                                  |                                                                                  |
|                                                                                  |  1. cvs(Concurrent Version Systems)                                              |
|                                                                                  |  #. svn(subversion)                                                              |
|                                                                                  |  #. hg(mercurial)                                                                |
|                                                                                  |  #. git                                                                          |
|                                                                                  |                                                                                  |
|                                                                                  |                                                                                  |
|                                                                                  | Each of these tools have their own merits and demerits. In this tutorial we      |
|                                                                                  | shall learn how to use mercurial or hg which is easy to learn and use and        |
|                                                                                  | comparatively light weight. Once you learn how to use hg, you can easily try     |
|                                                                                  | other tools and switch to one that you feel most comfortable with.               |
|                                                                                  |                                                                                  |
|                                                                                  | Let's now get into Installation. For Linux distributions, Ubuntu and Debian      |
|                                                                                  | type the following in command line terminal                                      |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| ``sudo apt-get install mercurial``                                               | For Windows,                                                                     |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| ``http://mercurial.selenic.com/downloads/``                                      |                                                                                  |
|                                                                                  |                                                                                  |
| ``http://hgbook.red-bean.com/read/a-tour-of-mercurial-the-basics.html``          |                                                                                  |
|                                                                                  |                                                                                  |
| .. R 11                                                                          |                                                                                  |
|                                                                                  |                                                                                  |
| For any other Operating system, please refer the hg book for installation        |                                                                                  |
| instruction -                                                                    |                                                                                  |
|                                                                                  |                                                                                  |
| Type 'hg' which lists out all the commands                                       |                                                                                  |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| ``$hg``                                                                          | and 'hg version' which gives the version number.                                 |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| ``$hg version``                                                                  | This brings us to the end of the tutorial. In this tutorial, we have             |
|                                                                                  | seen,                                                                            |
|                                                                                  |                                                                                  |
| *{{{Show the 'summary' slide'}}}*                                                | 1. the motivation to use version control                                         |
|                                                                                  | #. an analogy of version control with playing a video game                       |
|                                                                                  | #. how to check if mercurial is installed, and it's version using hg version     |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show self assessment questions slide}}}*                                     | Here are some self assessment questions for you to solve                         |
|                                                                                  |                                                                                  |
|                                                                                  |  1. Is Mercurial a Centralized VCS or Distributed VCS? Justify your reasoning.   |
|                                                                                  |  #. How can you verify whether Mercurial has been installed properly?            |
|                                                                                  |  #. What is the command for accessing built-in help system of Mercurial?         |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the solutions slide to self assessment questions }}}*                   | And the answers,                                                                 |
|                                                                                  |                                                                                  |
|                                                                                  |  1. Mercurial is a Centralized Version Control system. To read more go here, htt |
|                                                                                  |  #. $hg version                                                                  |
|                                                                                  |  #. $hg help command                                                             |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
| *{{{Show the thank you slide}}}*                                                 | Hope you have enjoyed this tutorial and found it useful. Feel free to play       |
|                                                                                  | around with Mercurial and read the documentation given by hg help command. When  |
|                                                                                  | you are ready to move on, please proceed to the second tutorial on 'Version      |
|                                                                                  | Control using Hg'                                                                |
|                                                                                  |                                                                                  |
|                                                                                  | Thank you                                                                        |
+----------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
