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

For macOS follow these [instructions](https://jekyllrb.com/docs/installation/macos/) 
and then run `jekyll serve`.

## Add a publication

All publications are located in the `_publications` folder. Each file contains
a single publication and has a [front
matter](https://jekyllrb.com/docs/front-matter/) and no body. The front matter
contains both mandatory and optional variables: 

| Variable   | Value                    | Category  | Description              |
|------------|--------------------------|-----------|--------------------------|
| title      | string                   | mandatory | Title of the publication |
| collection | `publications`           | mandatory | Jekyll-related, has always the same value |
| permalink  | `publications/file_name` | mandatory | Jekyll-related. `file_name` must be the same given to the file with this front matter |
| type       | `pub`; `standard`        | mandatory | `pub`, for a published paper, and `standard`, for standards, white papers and technical reports |
| date       | year-month-day           | mandatory | Date of publication      |
| author     | firt last,               | mandatory | Comma-separated list of authors |
| venue      | string                   | mandatory | Proceedings, journal or archive of the publication |
| paperurl   | URL                      | mandatory | Official URL of the publication |    
| abstract   | string                   | optional  | Abstract of the publication. When added, a landing page for the publication is created with title, authors, abstract and links to the full paper |

The name of the file in `_publications` must follow the format: Last name of
the first author, year of the publication, and first word of the title. An
example of a valid file name for a publication is: paraskevakos2018task.md.

Papers that have been uploaded to Arxiv are considered publications. It is the
first author responsibility to update her/his paper with the most current
information.

For reference, see the following paper front matter:

```yaml
---
title: "Task-parallel Analysis of Molecular Dynamics Trajectories"
collection: publications
permalink: /publications/paraskevakos2018task
type: pub
date: 2018-08-15
author: "Ioannis Paraskevakos, Andre Luckow, Mahzad Khoshlessan, George Chantzialexiou, Thomas E. Cheatham, Oliver Beckstein, Geoffrey C. Fox and Shantenu Jha"
venue: "47th International Conference on Parallel Processing (ICPP 2018)"
paperurl: http://somethingsomething
abstract: "Copy and paste the paper's abstract"
---
```

This paper's filename is: `paraskevakos2018task.md`

When adding a publication to the webpage, create a branch named
`publication/<pub-filename>` and create a pull request towards master of this
repo. As soon as the request is merged, GitHub will render the page on the
official website.

## Add a project

All project pages are located in the `_projects` folder. Each file contains a
single project and has a [front
matter](https://jekyllrb.com/docs/front-matter/) and a body in the
[markdown](https://daringfireball.net/projects/markdown/) and HTML format. The
front matter contains both mandatory and optional variables:

| Variable   | Value                | Category  | Description              |
|------------|----------------------|-----------|--------------------------|
| title      | string               | mandatory | Title of the project     |
| collection | `projects`           | mandatory | Jekyll-related, has always the same value |
| permalink  | `projects/file_name` | mandatory | Jekyll-related. `file_name` must be the same given to the file with this front matter |
| abstract.  | string               | mandatory | A *single* sentence that describes the project. See current [website](http://radical.rutgers.edu/projects/) for examples |
| status     | `active`; `inactive` | mandatory | Ongoing projects are `active`, terminated projects are `inactive` |
| grant      | {`funder`: string, `number`: string, `url`: URL} | optional | An collection with three keys. The whole collection and each of its key are optional |
| repository | URL.                 | optional | URL of the code repository of the project (e.g., github, bitbucket) |
| logo       | `images/projects/file_name` | optional | Optional but almost mandatory :) 150x150px, possibly 144dpi |
| figure     | {`name`: `images/projects/file_name`, `width`: int} | optional | Optional but almost mandatory :) max 1000x1000px, possibly 144dpi in compressed jpg. `width` is used in the project landing page. Try to select a number that makes the image to take up to 1/3 of the width of the landing page. |
| website    | URL                  | optional | The official website of the project |

The name of the file in `_projects` has no mandatory formatting; just keep it
short and descriptive of the project. An example of a descriptive and short
project name is: `power-of-many.md`.

For reference, see the following project front matter:

```yaml
---
title: "Extensible Tools for Advanced Sampling and analYsis (ExTASY)"
collection: projects
permalink: /projects/extasy
abstract: A *single* sentence that describes the project
status: active
grant:
    funder: NSF
    number: 0000000
    url: <points to NSF's project page>
repository: <repo url>
logo: < a small jpg under images/projects>
figure:
    name: similar to the loge, but larger
    width: how large to be in the webpage. Try to select a number that will make the image the same size as the ones already there
website: The project's actual site
```

In order to add a project to the webpage, create a branch named `project/<proj-filename>` 
and create a pull request towards master. As 
soon as the request is merged GitHub will render the page.

When adding a project to the website, create a branch named
`publication/<proj-filename>` and add the logo and page images in
`images/projects`. You must upload three images with the following naming
convention: `proj_name_original.jpg`; `proj_name_logo.jpg`; `proj_name.jpg`.
Create a pull request towards master of this repo. As soon as the request is
merged, GitHub will render the page on the official website.


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
