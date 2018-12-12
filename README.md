# RADICAL page

[![Build Status](https://travis-ci.org/radical-group/radical-group.github.io.svg?branch=master)](https://travis-ci.org/radical-group/radical-group.github.io)

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
sudo gem install jekyll-redirect-from
sudo gem install bundler
sudo gem install html-proofer
jekyll serve
```


## Add publications

All the publications are located in `_publications` folder. Its arrangement is 
based on type and they are sorted by date. Each publication can be written in 
markdown format. You have to state headers before writing. These are: `title`, 
`type`, `date`, `author` and `venue`. `type` can be `pub` for a published paper,
and `standard` for standards, white papers and technical reports. The file name 
should follow the format: Last name of the first author, year of the publication,
and first word of the title.

Papers that have been uploaded to Arxiv are considered publications. It is the 
first authors responsibility to update hers/his papers entries with the most
current information.

For reference see the following paper header.

```
---
title: "Task-parallel Analysis of Molecular Dynamics Trajectories"
collection: publications
permalink: /publications/paraskevakos2018task
date: 2018-08-15
type: pub
author: "Ioannis Paraskevakos, Andre Luckow, Mahzad Khoshlessan, George Chantzialexiou, Thomas E. Cheatham, Oliver Beckstein, Geoffrey C. Fox and Shantenu Jha"
venue: "47th International Conference on Parallel Processing (ICPP 2018)"
paperurl: http://somethingsomething
abstract: "Copy and paste the paper's abstract"
---
```

This paper's filename is: `paraskevakos2018task.md`

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
status: active
grant:
    funder: NSF
    number: 0000000
    url: <points to NSF's project page>
---
```

You can add additional information in you project such as:
```
repository: <repo url>
logo: < a small jpg under images/projects>
figure:
    name: similar to the loge, but larger
    width: how large to be in the webpage. Try to select a number that will make the image the same size as the ones already there
website: The project's actual site
```

As status selecte either `active` or `past` and the project will be placed to the correct entry.
In order to add a project to the webpage, create a branch named `project/<proj-filename>` 
and create a pull request towards master. As 
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
avatar: ioannis_par.jpg
joined: 2014
title: "PhD Candidate"
permalink: /people/iparask
contacts:
  email: "i.paraskev@rutgers.edu"
  office: "CoRE 707"
---
```

Additional information can be add by including the following in the header:
```
contacts:
  scholar: Your Google scholar page
  github: Github profile URL
  linkedin: Linkedin Profile URL
publications:
  - id: The filename of your publication, it should be lastname_year_word
    cofirst: true if you are the second name but have the same contribution.
  - id: mahzad2017parallel
projects:
  - id: as the filename of the project
    role: Your role to the project
```

If you don't have some of the information, just leave it blank. The avatar will 
bring your photo from `images/people` folder and display it on the people page.
As lab position, you can choose: `'researcher'`, `'phd'`, `'ms'`, `'undergrad'`.

To add yourself, create a branch named `people/<first-lastname>` and create a pull 
request towards master. As soon as the request is merged GitHub will render the page.

## Add blog posts

It's very easy to add a Blog post. All the posts are located in `_blog` folder.
Create a file `<date>_<newsname>.md`, e.g. `2018_10_8_webpage.md` in the folder.
The posts automatically get arranged by date. Each post can be written in markdown
format. The following headers are required: `title`, `categories`, and `date`.
An example is shown below:

```
---
title: New webpage
categories: blog
date: 2018-10-08
---
```
To add news, create a branch named `blog/<date>_<blogsname>` and create a pull 
request towards master. As soon as the request is merged GitHub will render the page.
