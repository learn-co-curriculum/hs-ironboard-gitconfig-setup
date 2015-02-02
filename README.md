---
tags: setup, environment, bash, kids
languages: ruby
---

## A Little More Environment Set Up

### The Ironboard Gem

You may have noticed those little green circles lighting up on Ironboard. To make them all light up you'll need to download a special Ironboard.

This gem isn't open-sourced, so we won't be downloading it from [RubyGems.org](https://rubygems.org/), which is where most gems are hosted. Before we download it, we will need to specify where it's coming from, which is a private server at Flatiron. Type this into your command line;

`gem sources -a http://flatiron:33west26@gems.flatironschool.com/`

Next, download the gem:

`gem install ironboard`

The ironboard gem will allow us to run the tests for challenges and labs. It's based off of [RSpec](https://www.relishapp.com/rspec), a popular testing framework in Ruby, but it does a bit more like help track your progress on labs.

Normally when we run our tests, we would type `rspec`, but to run the tests for challenges and labs, you'll type `ironboard` into your command line instead, within the root directory of the challenge/lab.

### Set Up Github SSH Keys

Right now many of you are cloning from Github using the HTTPS clone link. It's a little annoying to type in your email address and password every time though - especially since we'll be doing a lot more pushing and cloning in this class. We're going to help make your lives easier by setting up your Github SSH key. An SSH key is how github can identify you without you having to enter your username and password every single time you want to push code up to the server. 

**Follow these steps below:**

* Make sure you are in the home directory in your terminal. You should see this `~`. 

* See if you have a .ssh directory. Typing `ls -la` will show you all the hidden files. If you don't have a .ssh directory, you can make it with `mkdir .ssh`

* Now we need to generate the SSH key. Type `ssh-keygen -t rsa -C "your_email@example.com"` into your command line. (Enter the same email address that you used to set up your github account between the quotation marks.)

* You'll get prompted to type the password to your computer twice (the letters won't actually show up when you type).

* Once the SSH key generation is done, enter `ssh-add ~/.ssh/id_rsa` then `pbcopy < ~/.ssh/id_rsa.pub` (this copies your SSH key to your clipboard).

* Then you'll need to go to your github account online, and in the top right corner select account settings (the symbol that looks like a cog). 

* In the left toolbar, select "SSH Keys", then click the button "Add SSH Key".

* Enter the name "Github SSH" under "Title" and then paste your SSH key into the "Key" field. 

* Click the green Add Key button.

* Go back to terminal and verify that you successfully added the SSH key by typing `ssh -T git@github.com`. You should get back `Hi username! You've successfully authenticated, but GitHub does not provide shell access.`

### Congrats! You are all set.