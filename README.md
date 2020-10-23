# BK's Portfolio

This repo contains an easy-to-customize personal dev portfolio template that was created with Sass and JavaScript. It is lightweight and fully responsive, as well as comes with the Bootstrap grid system and loaded with Font Awesome. The site is static and comes production ready if you just want to add your information and go. Alternatively, you can edit styles, colours, and scripts fairly easily. The site was built as modular as possible to make it easy to shift around styles and content.

To view a live demo, [click here](https://balkrishnabk.github.io/).

Looking for a blog template? Checkout [DevBlog](https://balkrishnabk.github.io/).

## Features

* Gulp ready (compiles Sass and minifies JS)
* Sass ready with lots of commenting
* Fully responsive
* Comes with Bootstrap grid system
* Easy colour changes can be done through simple variable edits

## Contents

- [Setup and Configuration](#setup-and-configuration)
    - [Making Edits / Customizing the Template](#making-edits--customizing-the-template)
    - [Using the Template As Is](#using-the-template-as-is)
- [Customization and Editing](#customization-and-editing)
    - [General](#general)
    - [Images](#images)
    - [Header Section](#header-section)
    - [Lead Section](#lead-section)
    - [About Section](#about-section)
    - [Experience Section](#experience-section)
    - [Responsibilities Section](#responsibilities-section)
    - [Honors & Awards Section](#honors--awards-section)
    - [Skills Section](#skills-section)
    - [Certifications and Key Courses Section](#certifications-and-key-courses-section)    
    - [Education Section](#education-section)
    - [Publications Section](#publications-section)
    - [Contact Section](#contact-section)
    - [Footer Section](#footer-section)
    - [Optional Sections](#optional-sections)
- [License](#license)

## Setup and Configuration

The setup required can be broken into two types:
1. If you want to make edits or customize the template
2. If you just want to add your information as use as is

### Making Edits / Customizing the Template

To setup, simply fork the repo and run `npm install` in order to get all the Gulp dev dependencies. Next, run `Gulp watch` to compile the Sass and minify the JavaScript. Alternatively, if you don't have Gulp installed globally, you can run the npm script `npm run watch`. Any changes done to the JavaScript (js/scripts.js) or Sass (sass/styles.scss) will be autocompiled and ready to go.

All scripts are within `js/scripts.js` and get minified to `js/scripts.min.js`. All styles are in `sass/styles.scss` and get compiled to `css/styles.css`. Both the minified scripts file and compiled CSS file are what is loaded on the page by default.

At this point, the page is ready to go and you can begin to add your own information and make any needed changes. The sections below  contains a quick breakdown of each of the default sections and how they work.

### Using The Template As Is

If you wish to use the template as is (i.e. how it's seen in the demo), then all that's required is the `css`, `images`, `js`, `libs` folders and the `index.html` file. You would then add your content to `index.html` as needed and you're good to go!

## Customization and Editing

### General

In general, most styles on the page are based off the definitions of variables in the variable section of the style sheet:

```SCSS
$base-color: #FFA500;
$base-color-hover: darken($base-color, 10%);

// Define background colors
$background: #fff;
$background-alt: #f2f2f5;

// Define border colors
$border: #201e1e;

// Define text colors
$heading: #333c50;
$text: #74808a;
```

If you wish to change the general colour scheme of the page for example, simply change the value of `$base-color`.

There is also a number of default CSS classes that can be applied such as `.shadow`, `.shadow-large`, `.btn-rounded-white`, and various others. These can be found under the General Styles section in the style sheet.

### Images

By default, the template comes with a number of images, some of which can be kept and others which act simply as placeholders and should be switched. The template contains the following:

* Main background (images/lead-bg.jpg) - this is the main background image provided via [Unsplash](https://unsplash.com/). This can be kept or changed easily by replacing `images/lead-bg.jpg` with your new background (recommended size of at least 1920x1080).
* Favicon (/favicon.ico) - this is the favicon used for the page. Similar to the main bg, this can be kept or changed easily by replacing the `favicon.ico` with your new one.
* Project image - these are the images associated with the projects under the project section. These are simply placeholders and should either be replaced or removed.

### Header Section

The header section can be found within the `<header>` tag and simply contains an unordered list of anchors to different sections of the page. If you add a new section and want to be able to quickly navigate to it from the top, simply add another list element with an anchor that has the href of the ID of the section. Conversely, if you remove a section, don't forget to remove the associated navigation element.

If you wish to add a header link to an external page, simply add the class `no-scroll` to the anchor. For example:

```HTML
<li>
    <a href="https://google.com" class="no-scroll">Google</a>
</li>
```

If you wish to have a sticky (fixed) header, you simply need to add a class of `sticky` to the main header. For example, that would be accomplished as follows:

```HTML
<header class="sticky">
    <!-- Header content -->
</header>
```

### Lead Section

The Lead section is pretty straightforward, it contains an h1 for your name and an h2 for your title. It also contains a link that can be used to link to your resume should you wish to add it as well.

If you want your resume to automatically download when the button is clicked instead of opening up in another tab (the default behaviour), add the following code (Thanks to jkfran for the suggestion) in the lead:

```HTML
<a href="path/to/resume.pdf" download="resume.pdf" class="btn-rounded-white">Download Resume</a>
```

The href attribute points to where your resume is stored and the download attribute is what triggers the download / provides the name the file will be downloaded as when the user clicks the button (In this case, it will download as resume.pdf).

### About Section

The about section contains a quick about blurb that can be edited by changing the text within the paragraph tags.

### Experience Section

The experience section creates a vertical timeline with all your relevant experience. The code for the timeline creation can be found within `js/scripts.js` and is an adaptation of [BalkrishnaBK/vertical-timeline](https://github.com/BalkrishnaBK/vertical-timeline).

The default format is as follows:

```HTML
        <div id="experience-timeline">
            <div data-date="April 2018 – till date">
                <h3>IBM India Private Limited</h3>
                <h4>DevOps Engineer</h4>
                <p>
                    As an DevOps Engineer, I worked on the automation of CI/CD scripts using dev tools. I am working with multiple clients. Responsible for design and implementation of end to end automated delivery for multiple applications. Also, I am a part of the open banking, Digital Platform, and DevOps team in the Bendigo project. I am responsible for managing Dev tools and managing deployments. I worked on different tools. I worked on multiple Deployment and Integration tools. As well I worked on multiple Image repositories and Binary management tools. My primary work is to manage deployments. I am working on GitLab for Source Code Management and the same we are using as Integration and deployment tools as well but initially, we used to have GitHub as SCM and Jenkins as Integration tool and Ansible as Deployment tool. For the Image registry now we are using Jfrog but initially, we used to have IBM cloud Image Registry. In this project, I am responsible for the installation of Integration tools like Jenkins, Deployment tools like Ansible, and management of them. In this project, I deployed code on IBM Cloud Kubernetes Service platforms and now deploying on Amazon Web Services platform. I was responsible for the installation of Integration tools like Jenkins, Deployment tools like Urban Code Deploy, and Ansible. Also, the Image repository setup is done by me like JFrog and Nexus. For source code management we used Github. Even my role was to set up deployment environments like Kubernetes cluster and docker environment. Even I did deployment on single standalone VM's as well. I did the setup of ELK, Grafana, Prometheus, Zipkin, vault, and JIRA also management was with me for all this.
                </p>
            </div>
        </div>
```

The data attribute `data-date` is what is used to add a date to the associated timeline point. All that is really required is a wrapping div (i.e. `#experience-timeline`) and nested divs to build the timeline. The h3, h4, and p tags are optional and the contents of the div can be styled however you wish.

To add an additional section, simply add additional nested divs under the main wrapping div.

### Responsibilities Section

This section includes responsiblities I need to perform as DevOps Engineer. Even I am working as Deployment Manager for few weeks. [BalkrishnaBK/vertical-timeline](https://github.com/BalkrishnaBK/vertical-timeline).

The default format is as follows:

```HTML
    <div id="responsibilities">
        <h2 class="heading">Job Responsibilities</h2>
        <div class="education-block">
            <h3>Hands on expertise</h3>
            <p>
                <li>
                    Kubernetes Installation and Deployments
                </li>
                <li>
                    Helm chart creation and deployment
                </li>
                <li>
                    Dockerfiles and Docker-compose files
                </li>
                <li>
                    IBM Kubernetes Service                    
                </li>
                <li>
                    Docker Container Registry
                </li>
                <li>
                    Setting simple rules to deny sites & downloads                    
                </li>
                <li>
                    Monitoring users’ activities & reporting to superiors
                </li>
                <li>
                    IBM Cloud Private
                </li>
            </p>
        </div>
```

The data attribute `data-date` is what is used to add a date to the associated timeline point. All that is really required is a wrapping div (i.e. `#responsiblities-timeline`) and nested divs to build the timeline. The h3, h4, and p tags are optional and the contents of the div can be styled however you wish.

To add an additional section, simply add additional nested divs under the main wrapping div.

### Honors & Awards Section

This section shows up my achievements and awards. An example is as follows:

```HTML
        <div class="education-block">
            <h3>BEN's SUPERSTAR</h3>
            <span class="education-date">August 2020</span>
            <h4></h4>
            <p>
                Balkrishna ..Your are a BEN's SUPERSTAR ... Here is a small token of appreciation for all your contribution on Bendigo... You have been leading DevOps activites for OB team from Iteration 0. During migration to Interim AWS, you played a very critical role and extended working over several weekends ensuring a successful migration. The same was often appreciated by Geo team.
            </p>
        </div> End .project-info -->
</div>
```

### Skills Section

The Skills section is simply an unordered list that spits out a "Skill Cloud" with all the skills listed. To add / remove skills, simply edit or add list elements, like so:

```HTML
<ul>
            <li>Kubernetes</li>
            <li>Docker</li>
            <li>GitHub</li>
            <li>GitLab</li>
            <li>Jenkins</li>
            <li>IBM Urban Code Deploy</li>
            <li>Ansible</li>
            <li>Jfrog</li>
            <li>Nexus</li>
            <li>IBM Cloud Container Registry</li>
            <li>IBM Cloud Private</li>
            <li>IBM Kubernetes Service</li>
            <li>Amazon Web Services Cloud</li>
            <li>Bash Script</li>
            <li>Python</li>
            <li>Groovy Script</li>
            <li>Kafka - Zookeeper</li>
            <li>Vault</li>
            <li>JIRA</li>
            <li>jFrog Artifactory</li>
            <li>Nexus Repository</li>
            <li>Docker Trusted Registry</li>
            <li>Sonarqube</li>
            <li>ELK</li>
            <li>Grafana-Prometheus</li>
            <li>Zipkin</li>
            <li>AppDynamics</li>
            <li>C</li>
            <li>C++</li>
            <li>Spring Boot</li>
            <li>Confluence</li>
            <li>IBM API Connect</li>
            <li>Istio</li>
            <li>Postman</li>
            <li>Newman</li>
            <li>AppDynamics</li>
            <li>Apache</li>
            <li>Tomcat</li>
            <li>HashiCorp Vault and Kubernetes Secrets</li>
            <li>Helm</li>
</ul>
```


### Certifications and Key Courses Section

This section shows up the Certifications and Key Courses:

```HTML

                        <li>
                            Learn Devops The Complete Kubernetes Course
                        </li>
                        <li>
                            Hands-On Auto DevOps with GitLab CI
                        </li>
                        <li>
                            GitLab introduction
                        </li>
                        <li>
                            DevOps for DevOps Project Team Members
                        </li>
                        <li>
                            Docker Essential
                        </li>
                        <li>
                            Kubernetes Getting Started
                        </li>
                        <li>
                            DevOps Essentials
                        </li>
                        <li>
                            Get started with Kubernetes and IBM Cloud Container Service
                        </li>
                        <li>
                            Docker Essentials: A Developer Introduction
                        </li>
                        <li>
                            Containers, K8s and Istio on IBM Cloud
                        </li>
                        <li>
                            Beyond the Basics: Istio and IBM Cloud Kubernetes Service
                        </li>
                        <li>
                            Jenkins Beginner Tutorials
                        </li>
                        <li>
                            Git: Become an Expert in Git and GitHub
                        </li>
                        <li>
                            Build+Deploy+Test with Jenkins 2.0
                        </li>
                        <li>
                            Ansible Advanced-HandsOn-DevOps
                        </li>
                        <li>
                            DevOps learning path for DevOps Essentials badge
                        </li>
                        <li>
                            DevOps - The pre-Requisite
                        </li>
                        <li>
                            DevOps Crash Course: CI/CD with Jenkins Pipelines Groovy DSL
                        </li>
                        <li>
                            Getting Started with Jenkins
                        </li>
                        <li>
                            Just enough Ansible to be dangerous
                        </li>
```



### Education Section

The Education is just a series of `.education-block` classes with some details associated with them. By default, it shows school name, date, degree, and some additional details. For example:

```HTML
        <div class="education-block">
            <h3>Bachelor's of Computer Engineer</h3>
            <span class="education-date">2013-2017</span>
            <h4>Savitribai Phule Pune University</h4>
            <p>
                Completed BE in Computer Engineering with Distinction.<br>                
                ACADEMIC PROJECT<br>
                Project title: Transportation Portal (BE 2016-17)<br>
                Duration: June 2016 -April 2017<br>
                Description: The Portal will provide transportation details to user and will keep data
                stored in Centralized database. We are providing Web portal and Android application where in
                Android application notification system is provided. Further in portal we are
                implementing this by using software only so surely it will reduce coast of Project.
                <ul>
                    <li>
                        Got Mr.Academics award in Engineering, Dhole Patil Of Engineering College
                    </li>
                    <li>
                        Also was Technical Head of CESA(Computer Department Students Association) committee of Computer Department
                    </li>
                    <li>
                        Was a member of college students committee
                    </li>
                    <li>Participated into Cultural event of Kshitij 2015 ,2016 and 2017, Drama in Kshitij 2015
                        and 2016, Seed IT Idol</li>
                </ul>
            </p>
        </div>
```

To add additional section, simply add additional `.education-block` elements.



#### Publications Section

This section shows up my publications:

```HTML
        <div class="education-block">
            <h3>Transportation Porta</h3>
            <span class="education-date">2017</span>
            <h4></h4>
            <p>
                Balkrishna Londhe , Dr.Arati Dandwate , Ashwini Parab , Kajal Gavhane ,
                Tejaswini Ingale: Transportation Portal, in: INTERNATIONAL JOURNAL OF
                INTERDISCIPLINARY INNOVATIVE RESEARCH AND DEVELOPMENT Vol. 01, Issue
                03, 03, Balkrishna Londhe , Dr.Arati Dandwate, 2017, ISBN/ISSN: 2456-236X
            </p>
        </div>
```



### Contact Section

Since the page is static, I opted to use the awesome Formspree to allow for a contact form without the need for anything else. To use it, you must have the page hosted on a server (loading a basic HTML page won't work) where a referrer header is generated. Also, simply add the email to the action. An example is as follows:

```HTML
    <div id="contact">
        <h2>Get in Touch</h2>
        <div id="contact-form">
            <form method="POST" action="https://formspree.io/londhebalkrishna@gmail.com">
                <input type="hidden" name="_subject" value="Contact request from personal website" />
                <input type="email" name="_replyto" placeholder="Your email" required>
                <textarea name="message" placeholder="Your message" required></textarea>
                <button type="submit">Send</button>
            </form>
        </div>
```
For more information on configuration of the contact form or dealing with errors, check out [Formspree](https://formspree.io/).

For a quick tutorial about formspree, check out this [tutsplus tutorial](https://webdesign.tutsplus.com/tutorials/quick-tip-add-a-formspree-form-to-your-static-sites--cms-23870) that covers different aspects and features of the form tool.

### Footer Section

The Footer contains an optional copyright where you can place your name as well as an unordered list of all of your social or coding related profiles. By default it contains Github, Stack Overflow, acclaim, instagram, and Google Plus. You can add or remove them easily and simply use the Font Awesome icon associated with the social profile you wish to use. For a list of all icons, [click here](http://fontawesome.io/icons/).

### Optional Sections

The template comes with an optional section that can be added to the page markup to list things like Certifications, Hobbies, and more (Note: these are not included by default). The markup for the additional optional section is as follows:


You can copy .optional-section-block for each new item you wish you have in the optional section. Also, the background-alt class may need to be removed depending on where the optional section is placed in your layout as this adds the grey background. If you play it at the bottom after "Skills", it can be used as is. Also, by default the border is applied at the top, but this can also be adjusted as needed.

The optional section blocks have styling for h3 (the block title), h4, p, and ul tags by default.

## License

Completely free (MIT)! See [LICENSE.md](LICENSE.md) for more.
