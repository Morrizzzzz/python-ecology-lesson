---
title: Before we start
teaching: 40
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- Present motivations for using Python.
- Organize files and directories for a set of analyses as a Python project, and understand the purpose of the working directory.
- How to work with Jupyter Notebook and Spyder.
- Know where to find help.
- Demonstrate how to provide sufficient information for troubleshooting with the Python user community.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- What is Python and why should I learn it?

::::::::::::::::::::::::::::::::::::::::::::::::::

## What is Python?

Python is a general purpose programming language that supports rapid development of data analytics
applications. In addition Python is the most widely used programming language in the Geospatial domain.
The word "Python" is used to refer to both, the programming language and the tool
that executes the scripts written in Python language.

Its main advantages are:

- Free
- Open-source
- Available on all major platforms (macOS, Linux, Windows)
- Supported by Python Software Foundation
- Supports multiple programming paradigms
- Has large community
- Rich ecosystem of third-party packages

*So, why do you need Python for data analysis?*

- **Easy to learn:**
  Python is said to be easier to learn than other programming languages. This is important because lower barriers
  mean it is easier for new members of the community to get up to speed.

- **Reproducibility:**
  Reproducibility is the ability to obtain the same results using the same dataset(s) and analysis.
  
  Data analysis written as a Python script can be reproduced on any platform.  Moreover, if you
  collect more or correct existing data, you can quickly re-run your analysis!
  
  An increasing number of academic journals and funding agencies expect analyses to be reproducible. Also when you 
  are working as a GIS expert you do not want to rerun your models over and over again by clicking on certain buttons and tools.
  In addition, once you learn the python ecosystem you will notice that you can integrate all kind of data analysis and methods
  from other domains allowing you really boost your analysis and data processing toolbox. 
  Knowing Python will give you an edge with these requirements and opens a world of opportunities.

- **Versatility:**
  Python is a versatile language that integrates with many existing applications to enable something
  completely amazing.  For example, one can use Python to generate manuscripts, so that if you need to
  update your data, analysis procedure, or change something else, you can quickly regenerate all the
  figures and your manuscript will be updated automatically.
  
  Python can read text files, connect to databases, and many other data formats, on your computer or
  on the web.

- **Interdisciplinary and extensible:**
  Python provides a framework that allows anyone to combine approaches from different research
  (but not only) disciplines to best suit your analysis needs.

- **Python has a large and welcoming community:**
  Thousands of people use Python daily. Many of them are willing to help you through mailing lists and
  websites, such as [Stack Overflow][stack-overflow]  and [Anaconda community
  portal][anaconda-community].

- **Free and Open-Source Software (FOSS)... and Cross-Platform:**
  We know we have already said that but it is worth repeating.


## Knowing your way around Anaconda

[Anaconda][anaconda] distribution of Python includes a lot of its popular packages,
such as the IPython console, Jupyter Notebook, and Spyder IDE.
Have a quick look around the Anaconda Navigator. You can launch programs from the Navigator or use the command line.

The [Jupyter Notebook](https://jupyter.org) is an open-source web application that allows you to create
and share documents that allow one to create documents that combine code, graphs, and narrative text.
[Spyder][spyder-ide] is an **Integrated Development Environment** that
allows one to write Python scripts and interact with the Python software from within a single interface.

Anaconda comes with a package manager called [conda](https://conda.io/docs/)
used to install and update additional packages.


## Research Project: Best Practices

It is a good idea to keep a set of related data, analyses, and text in a single folder.
All scripts and text files within this folder can then use relative paths to the data files.
Working this way makes it a lot easier to move around your project and share it with others.

### Organizing your working directory

Using a consistent folder structure across your projects will help you keep things organized,
and will also make it easy to find/file things in the future. This can be especially helpful
when you have multiple projects. In general, you may wish to create separate directories for
your scripts, data, and documents.

- **`data/`**: Use this folder to store your raw data. For the sake of transparency and provenance,
  you should always keep a copy of your **raw data**. If you need to cleanup data, do it
  programmatically (*i.e.* with scripts) and make sure to separate cleaned up data from the raw data.
  For example, you can store raw data in files `./data/raw/` and clean data in `./data/clean/`.

- **`documents/`**: Use this folder to store outlines, drafts, and other text.

- **`code/`**: Use this folder to store your (Python) scripts for data cleaning, analysis, and
  plotting that you use in this particular project.

You may need to create additional directories depending on your project needs, but these should form
the backbone of your project's directory. For this workshop, we will need a `data/` folder to store
our raw data, and we will later create a `data_output/` folder when we learn how to export data as
CSV files.

## What is Programming and Coding?

Programming is the process of writing *"programs"* that a computer can execute and produce some
(useful) output.
Programming is a multi-step process that involves the following steps:

1. Identifying the aspects of the real-world problem that can be solved computationally
2. Identifying (the best) computational solution
3. Implementing the solution in a specific computer language
4. Testing, validating, and adjusting the implemented solution.

While *"Programming"* refers to all of the above steps,
*"Coding"* refers to step 3 only: *"Implementing the solution in a specific computer language"*. It's
important to note that *"the best"* computational solution must consider factors beyond the computer.
Who is using the program, what resources/funds does your team have for this project, and the available
timeline all shape and mold what "best" may be.


## Software Setup

### Installing Python Using Anaconda
For this workshop we are going to use the all-in-one installer [Anaconda][anaconda]. 
If you already used python before it is fine to use another distrubution, 
but make sure to have the right packages installed.

Regardless of how you choose to install it, please make sure you install Python
version 3.x (e.g., 3.9 is fine). Also, please set up your python environment at
least a day in advance of the workshop.  If you encounter problems with the
installation procedure, ask your workshop organizers via e-mail for assistance so
you are ready to go as soon as the workshop begins.

::::::::::::::::::::::::::::::::::::::: discussion

### Installing Anaconda

:::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: solution

### Windows

[Video tutorial][video-windows]

1. Open [https://www.anaconda.com/download][anaconda-windows] with your web browser.

2. Download the Anaconda for Windows installer with Python 3.

3. Install Python 3 by running the Anaconda Installer, using all of the defaults for installation *except* make sure that:
  * **Register Anaconda as my default Python 3.x** option is checked (it should be in the latest version of Anaconda).
  * **Add Anaconda to my PATH environment variable** is selected.


:::::::::::::::::::::::::

:::::::::::::::: solution

### Mac OS

[Video tutorial][video-mac]

1. Open [https://www.anaconda.com/download][anaconda-mac] with your web browser.

2. Download the Anaconda installer with Python 3 for OS X. These instructions assume that you use the "Graphical Installer" `.pkg` file

3. Follow the Python 3 installation instructions. Make sure that the install location is set to **Install only for me** so Anaconda will install its files locally, relative to your home directory. Installing the software for all users tends to create problems in the long run and should be avoided.

:::::::::::::::::::::::::


:::::::::::::::: solution

### Linux

Note that the following installation steps require you to work from the shell.
If you run into any difficulties, please request help before the workshop begins.

1. Open [https://www.anaconda.com/download][anaconda-linux] with your web browser.

2. Download the Anaconda installer with Python 3 for Linux.

3. Open a terminal window and navigate to the directory where the executable is downloaded (e.g., `cd ~/Downloads`).

4. Type:

   ```bash
   bash Anaconda3-
   ```

   and press "Tab" to autocomplete the full file name. The name of file you just downloaded should appear.

5. Press "Enter" (or "Return" depending on your keyboard).

6. Follow the text-only prompts.  When the license agreement appears (a colon will be present at the bottom of the screen) press "Spacebar" until you see the bottom of the text. Type `yes` and press "Enter" to approve the license. Press "Enter" again to approve the default location for the files. Type `yes` and press "Enter" to prepend Anaconda to your `PATH` (this makes the Anaconda distribution your user's default Python).

7. Close the terminal window.

:::::::::::::::::::::::::


### Setting up the workshop environment

If Anaconda was properly installed, you should have access to the `conda`
command in your terminal (use the **Anaconda prompt** on **Windows**).

**Note that packages are installed which are not used in this self study material. However since this self study material is meant to prepare for [this](https://esciencecenter-digital-skills.github.io/geospatial-python/) material it 
has been decided to let learners install everything already at this stage. 



1. Test that `conda` is correctly installed by typing:

   ```bash
   conda --version
   ```

   which should print the version of conda that is currently installed, e.g. :

   ```output
   conda 22.9.0
   ```

2. Run the following command:

   ```bash
   conda install -c conda-forge mamba
   ```

   IMPORTANT: If your terminal responds to the above command with `conda: command not found` see the [Troubleshooting section](#troubleshooting-conda-command-not-found).

3. Create the Python environment for the workshop by running:

   ```bash
   mamba env create -n geospatial -f https://raw.githubusercontent.com/carpentries-incubator/geospatial-python/main/files/environment.yaml
   ```

   Note that this step can take several minutes.

4. When installation has finished you should see the following message in the terminal:

   ```output
   # To activate this environment, use
   #    $ conda activate geospatial
   #
   # To deactivate an active environment, use
   #    $ conda deactivate
   ```

5. Now Activate the `geospatial` environment by running:

   ```bash
   conda activate geospatial
   ```

If successful, the text `(base)` in your terminal prompt will now read
`(geospatial)` indicating that you are now in the Anaconda virtual environment
named `geospatial`. The command `which python` should confirm that we're using
the Python installation in the `geospatial` virtual environment. For example:

```bash
which python
```

```output
/Users/your-username/anaconda3/envs/geospatial/bin/python
```

IMPORTANT: If you close the terminal, you will need to reactivate this
environment with `conda activate geospatial` to use the Python libraries
required for the lesson and to start JupyterLab, which is also installed in the
`geospatial` environment.

### Starting JupyterLab

In order to follow the lesson, you should launch JupyterLab. After activating the
geospatial conda environment, enter the following command in your terminal (use the **Anaconda prompt** on **Windows**):

```bash
jupyter lab
```

Once you have launched JupyterLab, create a new Python 3 notebook, type the following code snippet in a cell and press the "Play" button:

```python
import rioxarray
```

If all the steps above completed successfully you are ready to follow along with the lesson!

### Troubleshooting `conda: command not found`

* **Mac OS and Linux users:**

  1. First, find out where Anaconda is installed.

     The typical install location is in your `$HOME` directory (i.e., `/Users/your-username/`) so use `ls ~` to check whether an `anaconda3` directory is present in your home directory:

     ```bash
     ls ~
     ```

     ```output
     Applications      Downloads       Pictures
     anaconda3         Library         Public
     Desktop           Movies
     Documents         Music
     ```

     If, like above, you see a directory called `anaconda3` in the output we're in good shape. If not, **contact the instructor for help**.

  2. Activate the `conda` command-line program by entering the following command:

     ```bash
     source ~/anaconda3/bin/activate
     ```
     If all goes well, nothing will print to the terminal and your prompt will now have `(base)` floating around somewhere
     on the left. This is an indication that you are in the base Anaconda environment.

     Continue from the beginning of step 3 to complete the creation of the `geospatial` virtual environment.


## How to learn more after the workshop?

The material we cover during this self study will give you an initial taste of how you can use Python
to analyze data for your own research. It will give you sufficient knowledge to start the [Introduction to Geospatial Raster and Vector data workshop of the Geographic Information Science Master program](https://esciencecenter-digital-skills.github.io/geospatial-python/). 

## Seeking help

- check under the *Help* menu
- type `help()`
- type `?object` or `help(object)` to get information about an object
- [Python documentation][python-docs]
- [Pandas documentation][pandas-docs]

Finally, a generic Google or internet search "Python task" will often either send you to the
appropriate module documentation or a helpful forum where someone else has already asked your
question. 

I am stuck... I get an error message that I don't understand.
Start by googling the error message. However, this doesn't always work very well, because often,
package developers rely on the error catching provided by Python. You end up with general error
messages that might not be very helpful to diagnose a problem (e.g. "subscript out of bounds"). If
the message is very generic, you might also include the name of the function or package you're using
in your query.

However, you should check Stack Overflow. Search using the `[python]` tag. Most questions have already
been answered, but the challenge is to use the right words in the search to find the answers:
[https://stackoverflow.com/questions/tagged/python?tab=Votes][so-python]

You can also choose to use ChatGPT, however be aware of the energy cost and a tool that
directly povides you with the answer might not be very helpfull in a learning proces. It is up to you!


### Asking for help

The key to receiving help from someone is for them to rapidly grasp your problem. You should make it
as easy as possible to pinpoint where the issue might be.

Try to use the correct words to describe your problem. For instance, a package is not the same thing
as a library. Most people will understand what you meant, but others have really strong feelings
about the difference in meaning. The key point is that it can make things confusing for people
trying to help you. Be as precise as possible when describing your problem.

If possible, try to reduce what doesn't work to a simple reproducible example. If you can reproduce
the problem using a very small data frame instead of your 50,000 rows and 10,000 columns one,
provide the small one with the description of your problem. When appropriate, try to generalize what
you are doing so even people who are not in your field can understand the question. For instance,
instead of using a subset of your real dataset, create a small (3 columns, 5 rows) generic one.

### Where to ask for help?

- The person sitting next to you during the workshop. Don't hesitate to talk to your neighbor during
  the workshop, compare your answers, and ask for help. You might also be interested in organizing
  regular meetings following the workshop to keep learning from each other.
- Your friendly colleagues: if you know someone with more experience than you, they might be able and
  willing to help you.
- [Stack Overflow][so-python]: if your question hasn't been answered before and is well crafted,
  chances are you will get an answer in less than 5 min. Remember to follow their guidelines on how to
  ask a good question.
- [Python mailing lists][python-mailing-lists]
- ChatGPT or similar generative AI models.

## More resources

- [PyPI - the Python Package Index][pypi]

- [The Hitchhiker's Guide to Python][python-guide]

- [Dive into Python 3][dive-into-python3]

- [Think python][think-python]

[stack-overflow]: https://stackoverflow.com
[anaconda-community]: https://www.anaconda.com/community
[anaconda]: https://www.anaconda.com/download
[spyder-ide]: https://www.spyder-ide.org
[python-docs]: https://www.python.org/doc
[pandas-docs]: https://pandas.pydata.org/pandas-docs/stable/
[so-python]: https://stackoverflow.com/questions/tagged/python?tab=Votes
[python-mailing-lists]: https://www.python.org/community/lists
[pypi]: https://pypi.org/
[python-guide]: https://docs.python-guide.org
[dive-into-python3]: https://diveintopython3.net/
[think-python]: https://greenteapress.com/wp/think-python-3rd-edition/
[anaconda]: https://www.anaconda.com/
[anaconda-mac]: https://www.anaconda.com/download/#macos
[anaconda-linux]: https://www.anaconda.com/download/#linux
[anaconda-windows]: https://www.anaconda.com/download/#windows
[python]: https://python.org
[video-mac]: https://www.youtube.com/watch?v=TcSAln46u9U
[video-windows]: https://www.youtube.com/watch?v=xxQ0mzZ8UvA

:::::::::::::::::::::::::::::::::::::::: keypoints

- Python is an open source and platform independent programming language.
- Jupyter Notebook and the Spyder IDE are great tools to code in and interact with Python. With the large Python community it is easy to find help on the internet.

::::::::::::::::::::::::::::::::::::::::::::::::::


