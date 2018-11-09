---
title: Tracking Changes
teaching: 20
exercises: 0
questions:
- "How do I record changes in Git?"
- "How do I check the status of my version control repository?"
- "How do I record notes about what changes I made and why?"
objectives:
- "Go through the modify-add-commit cycle for one or more files."
- "Explain where information is stored at each stage of Git commit workflow."
keypoints:
- "Files can be stored in a project's working directory (which users see), the staging area (where the next commit is being built up) and the local repository (where commits are permanently recorded)."
- "Always write a log message when committing changes."
---

You should now have a `survey_data` repository on your desktop.

Drag `survey_data_cleaned.csv`, which was the end result of the Data Organization lesson.

You can also download this file [here](https://raw.githubusercontent.com/caltechlibrary/git-desktop/gh-pages/data/survey_data_cleaned.csv)

You'll see that GitHub Desktop has changed to signify that a new file has been added. The left hand panel, which shows changes that have occurred in the repository, lists the new file.  It knows this is a new file that it will have to add to the repository, as indicated by the green plus sign.  In addition, contents of the file applear in green in the right hand panel, which provides details about the changes.  

![new file](../fig/GitDesktopChanges1.png)

In order to save this version of the file, we need to commit our changes. To do this we need to write a commit message that describes our changes.  You can provide both a short summary of the changes and a longer description by typing in the lower left hand corner of GitHub Desktop. Then click Commit to master.   

![commit](../fig/GitDesktopChanges2.png)

When we commit our changes,
Git takes everything we have told it to save 
and stores a copy permanently inside the special `.git` directory.
This permanent copy is called a [commit]({{ page.root }}/reference/#commit)
(or [revision]({{ page.root }}/reference/#revision)) and is assigned a identifier.  

If you click the History tab you'll see a record of the changes you have made.  The "Initial commit' was generated automatically when you requested a README file to be added to the repository, and at the top you'll see the commit we made with the summary "Initial file".  More details are listed on the right hand side, including the description and a short version identifier for the commit (7118513 in the example - yours will be different). 

![history](../fig/GitDesktopChanges3.png)

> ## Where Are My Changes?
> If we look in our directory at this point, we will still see just one file called `survey_data_cleaned.csv`.
> That's because Git saves information about files' history
> in the special `.git` directory mentioned earlier
> so that our filesystem doesn't become cluttered
> (and so that we can't accidentally edit or delete an old version).
{: .callout}

Now let's open up our data file in a spreadsheet program.  In reality you'll want to make most changes to data files using code (we'll talk about this tomorrow), but for now we're going to manually make changes to see how things work.  Some of the fields in the data file don't have weights.  Let's add a some text in the first note field that the scale was broken.  Save the file (Because you're working with a csv file Excel may complain.  Make sure that your data file is still saved as a csv).

When we switch back to GitHub Desktop, we see that something has happened in Changes tab.  Our data file appears in the left hand panel with a yellow star, which signifies that this file has been changed.  In the right hand panel we can see that one line in our .csv file, shown in green, has been added (it includes the "scale broken" note).  It also shows that the line without the note has been removed, shown in red.  If we write a commit message these changes will be saved in our history.

![new_change](../fig/GitDesktopChanges4.png)

When we look at the history tab, we can see our new commit in the list.  It's got a completely different identifier.  Note that git only saves the history of changes, as opposed to multiple copies of files.  This is why git works well for text files and code, but not so well for images and binary files.

> ## Directories
>
> Two important facts you should know about directories in Git.
>
> 1. Git does not track directories on their own, only files within them.
> Try adding a folder to survey_data.
> 
> Note, our newly created empty directory `directory` does not appear in
> the changes tab of Git Desktop. This is the reason why you will sometimes see `.gitkeep` files
> in otherwise empty directories. Unlike `.gitignore`, these files are not special
> and their sole purpose is to populate a directory so that Git adds it to
> the repository. In fact, you can name such files anything you like.
>
>
{: .callout}

> ## Choosing a Commit Message
>
> In this moment you have the opportunity to communicate with the future ;-)
> The commit messages does need to repeat the obvious like "add", "remove",
> "change", and what exactly it was.
> 
> What would you say to a colleague who is looking over your shoulder to
> explain what you did? Come up with other commit messages that _explain_ why!
>
> > ## Solution
> > For example:
> > - "Explain missing data"
> > - "Avoid overlooking missing data in calculations"
> {: .solution}
{: .challenge}

> ## Version-controlling images
>
> All Git tools are optimised for text files and show changes line-by-line.
> GitHub Desktop and a few others can additionally show changes in image files
> like `.jpg`, `.png`, etc. Let's try it with the two screenshot in this episode!
>
> 1. Right-click the 1st screenshot (`new file`)
> 2. Download/save it into your repository folder, and commit it.
> 3. How do you now need to treat the 2nd screenshot (`commit`) to make GitHub
>    Desktop compare it to the former?
>
> > ## Solution
> > Either save the 2nd image under the same name as the 1st, overwriting
> > it, or download the 2nd, copy the name of the 1st, delete that and paste
> > the name for the 2nd.
> {: .solution}
{: .challenge}

[commit-messages]: https://chris.beams.io/posts/git-commit/
