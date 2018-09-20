# RADICAL page


This is the repository for our [RADICAL page](http://radical.rutgers.edu/). We 
use Jekyll to run our Github page. We welcome other people to contribute to our 
site not just lab members. Feel free to fork and create pull-requests!

This site is based on a clone of [KordingLab.github.io](https://github.com/KordingLab/KordingLab.github.io)

## Run the page locally

To run locally, follow Jekyll's installation instructions [here](https://jekyllrb.com/). 
Then run `jekyll serve` and you will be able to see the page at `localhost:4000`. 

Here is a brief install guidelines for Ubuntu.

```bash
sudo gem install jekyll
sudo gem install rouge
jekyll serve
```


## Add publications

All the publications are located in `_publications` folder. Its arrangement is 
based on type and they are sorted by date. Each publication can be written in 
markdown format. You have to state headers before writing. These are: `title`, 
`type`, `date`, `author` and `venue`. `type` can be `pub` for a published paper, 
`draft` for a draft, and `standard` for standards, white papers and technical 
reports. The file name should follow the format: Last name of the first author, 
year of the publication, and first word of the title.

For reference see the following paper header.

```
---
title: "Task-parallel Analysis of Molecular Dynamics Trajectories"
collection: publications
permalink: /publications/Paraskevakos2018Task
date: 2018-08-15
type: pub
author: "Ioannis Paraskevakos, Andre Luckow, Mahzad Khoshlessan, George Chantzialexiou, Thomas E. Cheatham, Oliver Beckstein, Geoffrey C. Fox and Shantenu Jha"
venue: "47th International Conference on Parallel Processing (ICPP 2018)"
---
```

This paper's filename is: `Paraskevakos2018Task.md`

In order to a publication to the webpage, create a branch named `publication/<pub-filename>` 
and create a pull request towards master under the `radical-cybertools` repo. As 
soon as the request is merged GitHub will render the page.

## Add project

You can create a new project page in `_projects` folder. Create a file 
`<projectname>.md` in the folder. The following header is required before 
you start writing your own page. See the following for the header example

```
---
title: "Extensible Tools for Advanced Sampling and analYsis (ExTASY)"
collection: projects
permalink: /projects/extasy
abstract: A single sentence that makes sense
---
```

In order to include a Github link do at the end of the file:
```
<a href="https://github.com/project/repo"><i class="fa fa-github"></i> repo name</a><br>
```

In order to add a project to the webpage, create a branch named `project/<proj-filename>` 
and create a pull request towards master under the `radical-cybertools` repo. As 
soon as the request is merged GitHub will render the page.

## Add yourself

You can add yourself to the page in `_people` folder. Create a file 
`<firstname>_<lastname>.md` in the folder. We require few line of header before 
    you start writing your own page. See the following for the header

```
---
name: "Ioannis Paraskevakos"
collection: people
position: phd
avatar: giannis.png
joined: 2014
permalink: /people/iparask
---
```

If you don't have some of the information, just leave it blank. The avatar will 
bring your photo from `images/people` folder and display it on the people page.
As lab position, you can choose: `'researcher'`, `'phd'`, `'ms'`, `'undergrad'`, 
`'visiting'`.

To add yourself, create a branch named `people/<first-filename>` and create a pull 
request towards master under the `radical-cybertools` repo. As soon as the request 
is merged GitHub will render the page.
