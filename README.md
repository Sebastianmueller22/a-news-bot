# a-news-bot

A simple lambda expression that summarizes a given news site. Currently works for tagesschau.de

This is meant to run as an AWS lambda expression and will scrape, filter and summarize a given news page. 

# Instructions

In order for this to work, you need to deploy it as a lambda expression in AWS. 

The lambda expression needs a layer, containing the dependencies.

Dependencies: 
openai
bs4
re

This needs to be added to the lambda as a layer. For how to add layers, you can follow these steps:

on linux 

make a folder

python3 -m venv myvenv

source myvenv/bin/activate

pip install — what you want

repeat for more

create folder called python

copy the lib directory into the folder python

zip python

upload into the layer

check python version

check operating system

add to lambda via hash.


Once you have your layer added to your lambda, you need to add your sender email. 
This needs to be an email with an app password so that it can be used to send an email from your code. 
Add your recipient as well and feel free to edit the System prompts of the two bots to conform to your needs. 

If you chose to scrape a different site than the tagesschau, you need to retrieve a different classname as well to target the "preview" article summaries that most news landing pages have. 

Add your Open AI Api Key

Add an event bridge trigger to your lamda that for example runs once a day. 

And here you go, you'll receive daily emails with a summary of your favorite news site! 
