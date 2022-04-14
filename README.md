# The Drupal Phase

[![GitHub Issues](https://img.shields.io/github/issues/acch/ansible-boilerplate.svg)](https://github.com/acch/ansible-boilerplate/issues) [![GitHub Stars](https://img.shields.io/github/stars/acch/ansible-boilerplate.svg?label=github%20%E2%98%85)](https://github.com/acch/ansible-boilerplate/) [![License](https://img.shields.io/github/license/acch/ansible-boilerplate.svg)](LICENSE)

### The Purpose

The purpose of this project was to be able to pull a docker image of Drupal on one Virtual Machine and push it to another through the use of an Ansible script. Getting more into what Drupal is: Drupal is a free, open-source content management system (CMS) with a large, supportive community. It's used by millions of people and organizations around the globe to build and maintain their websites. Using Drupal to run a website is a very impressive help that can help anyone project content onto websites with ease and the ead goal is to pusblish drupal to a VM like so:

![image](https://user-images.githubusercontent.com/77757661/163450316-04babd47-0e96-4722-aacb-0d7caa941f23.png)

### Problem

Essentially, the problem that we face is that we need to be able to pusblish this onto another VM. this calls into use the Ansible Script that we want. We need to be able to use Drupal on the Prject VM while making the Script on the control VM. So I cloned the project from github and used the main.yml as the ansible script to check and stall all that I needed, and the site.yml to run all the tasks and the anygroup.yml to run all takss in the server in group as described below:

File | Description
---- | -----------
`site.yml` | Main playbook - runs all tasks on all servers
'main.yml' | Used playbook - runs all the tasks for docker and drupal
`anygroup.yml` | Group playbook - runs all tasks on servers in group *anygroup*

This is what we have to make the main.yml work:

![image](https://user-images.githubusercontent.com/77757661/163452713-d6c7ef92-24a1-4a2e-817a-a17b11ccdadf.png)

Overall after this we use the line 'ansible-playbook site.yml' to run the script so that it publishes on our Project2 VM.

### Software Block Diagram
![alt text](https://www.tutorialandexample.com/wp-content/uploads/2020/12/image-83.png)

## Copyright and license

Copyright 2017 Achim Christ, released under the [MIT license](LICENSE)
