---
title: Projects
date: 2017-08-21 02:49:42
tags:
---

## Open Source

### 1. [Caching in pack CLI](https://github.com/buildpacks/pack)
☀️This was a large sized project for [Google Summer of Code 2022](https://summerofcode.withgoogle.com/programs/2022/projects/69nLAdPo) at [CNCF](https://www.cncf.io)

[pack](https://github.com/buildpacks/pack) is a [CNCF](https://www.cncf.io) project used to build OCI images from your apps source code automatically without the need to write any docker config files.

I was responsible for implementing new cache flags and a new cache type: bind cache to speed up the build process during subsequent builds.
{% codeblock "Converting the source code of a node server to docker image runnable on any cloud" lang:bash %}
pack build test-app --path="/OSS/pack-test/node-server" --buildpack="/OSS/pack-test/node-server" --cache="type=build;format=bind;name=./bindcache"
{% endcodeblock %}
Building a simple node server's app image from source code for the first time
![pack without command](/images/pack_wo_cache.png)
Build time improvement while building same app image **using bind caches**
![pack with cache](/images/pack_w_cache.png)
👨‍💻[Here's all of the work done for the same](https://github.com/buildpacks/pack/commits?author=imnitishng)


### 2. [Offline Khan Academy](https://github.com/openzim/zim-requests/issues/327)
[Kiwix](https://www.kiwix.org/en/) is on a mission to download the internet and serve it offline to the underprivileged, Kiwix is already the largest offline distributor of Wikipedia to date, you can download the entirety of Wikipedia [from here](https://wiki.kiwix.org/wiki/Content_in_all_languages) and [carry it offline](https://www.vice.com/en/article/dyzxgm/you-can-download-the-entirely-of-english-wikipedia-to-browse-offline-using-kiwix) anywhere as `.zim` files that run on [Kiwix Browser](https://www.kiwix.org/en/download/).

I worked with the organization to bring the entire [Khan Acacdemy](https://www.khanacademy.org) offline, the [project](https://github.com/openzim/zim-requests/issues/327) was split into many parts
1. [Improvements to the python scraper](https://github.com/openzim/kolibri/commits?author=imnitishng)
2. Bringing [interactive exercises](https://www.khanacademy.org/math/cc-2nd-grade-math/cc-2nd-place-value/cc-2nd-skip-counting/e/skip-counting-by-10s) from Khan Academy offline to [standalone HTML files](https://github.com/imnitishng/standalone-perseus)
    - Live sample of the work done here to bring [this Khan academy interactive exercise and article content](https://www.khanacademy.org/math/cc-fourth-grade-math/imp-measurement-and-data-2/imp-converting-units-of-mass/a/us-customary-units-of-mass-review) offine, running as [standalone HTML content on the browser](/misc/standalone_perseus/index)✨
3. Integrating the scraper with pipelines that serve `.zim` files for download

🌈 Fun fact: This project was supposed to be in GSoC 2021, but it didn't make the cut in final shortlisted projects, but I decided to complete it anyway outside of the program.


### 3. [Add backend support to Grimoirelab toolchain](https://github.com/chaoss/grimoirelab-elk/commits?author=imnitishng)
Grimoirelab toolchain consists of tools that [fetch data](https://github.com/chaoss/grimoirelab-perceval) from various sources (github, slack, twitter, etc.), [enrich it](https://github.com/chaoss/grimoirelab-elk) and [display insights](https://github.com/chaoss/grimoirelab-sigils) as dashboards using the [ELK stack](https://www.elastic.co/what-is/elk-stack).

I contributed to various GrimoireLab toolchain projects under [CHAOSS](https://chaoss.community) organization
- [Create data enricher](https://github.com/chaoss/grimoirelab-elk/commits?author=imnitishng) for Elasticsearch indexes from raw data fetched by [Gitter](https://gitter.im) and [Launchpad](https://launchpad.net).
- Add support for fetching data into the toolchain from Gitter and Bitbucket APIs
- [Add data visualization panels](https://github.com/chaoss/grimoirelab-sigils/pull/443) for Gitter backend

![The Grimoirelab Toolchain](https://chaoss.github.io/grimoirelab-tutorial/assets/grimoirelab-all.png)
<center>The Grimoirelab Toolchain</center>

### 4.  Other OSS work
#### Mattermost
Explore [mattermost server](https://github.com/mattermost/mattermost-server) written in GO to learn more about SQL to GO struct mappings, alongwith modern scalable software observability measures like standard logging, caching and metrics.
#### Zulip
[Zulip server](https://github.com/zulip/zulip) is a Django application that powers all of Zulip, implemented a job runner using Django that dispatches scheduled and instant mails inspired by the [job management commands](https://github.com/zulip/zulip/tree/main/zerver/management/commands) from Zulip server. 


## Projects


### 1. Muse
[Muse](https://github.com/imnitishng/muse) is responsible to generate intelligent music recommendations based on song lyrics, the web app is powered by modern web technologies and deep learning algorithms that embed text and generating recommendations.
- Write web scrapers to scrape and save song lyrics from different websites to avoid relying on paid third party APIs for lyrics.
- Supports custom and state of the art NLP models to generate similarity embeddings that fuel the recommendations engine.
- Project follows modern CI/CD pipelines measures and test driven development alongwith fully documented components.

### 2. hkrnws
[hkrnws](https://github.com/imnitishng/hkrnws) is a [hackernews](news.ycombinator.com) client for fetching top posts and serve them chronologically with user management features specific features.
- Secure login signup and data serialization
- Management commands for fetching and updating data periodically

### 3. Self Driving Car
[Self Driving Car](https://github.com/imnitishng/SelfDrivingCar) was a college project which revolved around building a Car that would self drive around an arbitrary path provided the path boundaries were kept standard. 
 For our project the path was decided to be anything between two sheets of paper (or anything between two white edges in computer vision terms), a here is a brief summary of the project 
 - Interfacing hardware and building the Car (Raspberry Pi 3 + Arduino Uno + Motor Drivers + General hardware for car)
 - Training the Convolutional Neural Network by running the car through our custom track to collect image data
 - Run the car automatically any arbitrary shaped track based on the steering predictions made by the model, moreover have additional features like object detection for stopping the car
 [![Self Driving Car in action](https://img.youtube.com/vi/CA3_f0qclTU/0.jpg)](https://www.youtube.com/watch?v=CA3_f0qclTU)

 