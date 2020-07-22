# RADICAL Website

[![Build Status](https://travis-ci.org/radical-group/radical-group.github.io.svg?branch=master)](https://travis-ci.org/radical-group/radical-group.github.io)

This is the repository for our [RADICAL website](http://radical.rutgers.edu/). We 
use Jekyll to run our Github page. We welcome other people to contribute to our 
site not just lab members. Feel free to fork and create pull-requests!

This site is based on a clone of [KordingLab.github.io](https://github.com/KordingLab/KordingLab.github.io)

## Run the website locally

To run locally, follow Jekyll's [installation instructions](https://jekyllrb.com/), clone this repository and `cd` in its root directory.

### Ubuntu

```bash
sudo gem install jekyll
sudo gem install rouge
sudo gem install jekyll-redirect-from
sudo gem install bundler
sudo gem install html-proofer
jekyll serve
```

### macOS

First, install [homebrew](https://brew.sh/) if not already installed, then do the following:

```
xcode-select --install
brew install ruby
echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.bash_profile
gem install --user-install bundler jekyll rouge jekyll-redirect-from html-proofer
echo 'export PATH="/Users/$USER/.gem/ruby/2.7.0/bin:$PATH"' >> ~/.bash_profile
. ~/.bash_profile
```
Note: this assumes that ruby 2.7.0 was installed. Change the last echo command if you have a different version.

Check that the installation was successful:
- `which ruby` should return `/usr/local/opt/ruby/bin/ruby` if it returns `/usr/bin/ruby` you are using the one shipped with macos and jekyll will likely not work.
- `gem env` should show `/Users/$USER/.gem/ruby/2.7.0/bin:$PATH` under SHELL PATH.

Issue:
```
jekyll serve
```

You should be able to see the website in your browser at `http://127.0.0.1:4000`. Any local change made to the website should be immediately reflected reloading the page.

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
date: 2018-08-15
type: pub
author: "Ioannis Paraskevakos, Andre Luckow, Mahzad Khoshlessan, George Chantzialexiou, Thomas E. Cheatham, Oliver Beckstein, Geoffrey C. Fox and Shantenu Jha"
venue: "47th International Conference on Parallel Processing (ICPP 2018)"
paperurl: https://dl.acm.org/citation.cfm?id=3225128
abstract: "Abstract."
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
| grant      | {`funder`: string, `number`: string, `url`: URL} | optional | A collection with three keys. The whole collection and each of its keys are optional |
| repository | URL.                 | optional | URL of the code repository of the project (e.g., github, bitbucket) |
| logo       | `file_name` | optional | Optional but almost mandatory :) 150x150px, possibly 144dpi |
| figure     | {`name`: `file_name`, `width`: int} | optional | Optional but almost mandatory :) max 1000x1000px, possibly 144dpi in compressed jpg. `width` is used in the project landing page. Try to select a number that makes the image to take up to 1/3 of the width of the landing page. |
| website    | URL                  | optional | The official website of the project |

The body of the file contains a one-paragraph description of the project.

The name of the file in `_projects` has no mandatory formatting; just keep it
short and descriptive of the project. An example of a descriptive and short
project name is: `power-of-many.md`.

For reference, see the following project front matter:

```yaml
---
title: "Extensible Tools for Advanced Sampling and analYsis (ExTASY)"
collection: projects
permalink: /projects/extasy
abstract: "Executing iterative, coupled molecular simulation and analysis kernels on high performance computing systems." 
logo: extasy_logo.jpg
status: active
figure:
  name: extasy.jpg
  width: 300
repository: https://bitbucket.org/extasy-project/extasy-workflows
grant:
  funder: NSF
  number: 1265929
  url: https://nsf.gov/awardsearch/showAward?AWD_ID=1265929
---

The Extensible Toolkit for Advanced Sampling and AnalYsis (ExTASY) is a lightweight software...
```

When adding a project to the website, create a branch named
`publication/<proj-filename>` and add the logo and page images in
`images/projects`. You must upload three images with the following naming
convention: `proj_name_original.jpg`; `proj_name_logo.jpg`; `proj_name.jpg`.
Create a pull request towards master of this repo. As soon as the request is
merged, GitHub will render the page on the official website.


## Add yourself

All RADICAL member pages are located in the `_people` folder. Each file contains a
single personal page and has a [front
matter](https://jekyllrb.com/docs/front-matter/) and a body in the
[markdown](https://daringfireball.net/projects/markdown/) and HTML format. The
front matter contains both mandatory and optional variables:

| Variable     | Value                | Category  | Description              |
|--------------|----------------------|-----------|--------------------------|
| name         | string               | mandatory | Title of the project     |
| collection   | `projects`           | mandatory | Jekyll-related, has always the same value |
| permalink    | `projects/file_name` | mandatory | Jekyll-related. `file_name` must be the same given to the file with this front matter |
| position     | `undergrad`; `ms`; `phd`; `researcher`; `pi` | mandatory | Your position in the lab |
| title        | string               | mandatory | Your title in the lab |
| joined       | year                 | mandatory | The year you joined the lab |
| avatar       | `file_name`.jpg | optional | Optional but almost mandatory :) square, possibly 144dpi, <1MB |
| contacts     | {`email`: string, `office`: string, `scholar`: URL, `github`: URL, `linkedin`: URL} | optional | A collection of contact-related information. The whole collection and each of its keys are optional |
| publications | {`id`: string, `cofirst`: true} | optional | The collection of your RADICAL publications. `id` must be the same as the name of the corresponding publication file in `_publications`; `cofirst` used only when you are a co-first author of the paper |
| projects     | {`id`: string, `role`: string} | optional | The collection of RADICAL projects in which your are involved. `id` must be the same as the name of the corresponding project file in `_projects`; `role` indicates your official role in the project |
| students     | [string] | optional | List of students name. Available if you are member of the Graduate School and advisor of one or more RADICAL students. |

The body of the page can contain your brief bio or whatever else relates to
your research and activity in the lab.

The name of the file in `_people` must follow the format: firstname_lastname. An
example of a valid file name is: `ioannis_paraskevakos.md`.

For reference, see the following project front matter:

```yaml
---
name: "Ioannis Paraskevakos"
collection: people
permalink: /people/iparask
position: phd
title: "PhD Candidate"
joined: 2014
avatar: ioannis_par.jpg
contacts:
  office: "CoRE 707"
  ...
publications:
  - id: paraskevakos2018task
  ...
projects:
  - id: iceberg
    role: Research Assistant
  ...
---

I am a fifth year PhD student at ...

```

When adding yourself to the website, create a branch named
`people/<first-lastname>` and add your photo to `images/people`. Create a pull
request towards master of this repo. As soon as the request is merged, GitHub
will render the page on the official website.

## Add a blog post

All blog posts are located in the `_blog` folder. Each file contains a single
post and has a [front matter](https://jekyllrb.com/docs/front-matter/) and a
body in the [markdown](https://daringfireball.net/projects/markdown/) and HTML
format. The front matter contains the following mandatory variables:

| Variable     | Value                | Category  | Description              |
|--------------|----------------------|-----------|--------------------------|
| title        | string               | mandatory | Title of the blog post   |
| categories   | `blog`               | mandatory | Jekyll-related, has always the same value |
| date         | year-month-day       | mandatory | The date of the post.    |

The body of file contains your blog post.

The name of the file in `_blog` must follow the format: year_month_day_title. An
example of a valid file name is: `2018_10_8_webpage.md`.

For reference, see the following project front matter:

```yaml
---
title: New Look
categories: news
date: 2018-11-06
---

Our site continues to ...
```

When adding post to website, create a branch named `people/<date-blogname>`.
Create a pull request towards master of this repository. As soon as the request is
merged, GitHub will render the page on the official website.
