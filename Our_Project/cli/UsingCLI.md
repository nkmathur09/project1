[Note that our project runs on 2 ports]
[The application (registry) server runs on port 5060 and the repository runs on port 5050]

Using the CLI

- Open Terminal and type below command:-
  
  pcr help

It will show up all the possible commands that can be used with pcr command tool.

Set the Repository

For the first time you need to set the Conda Repo with the help of below command:-

pcr registry set <url of citi_project/pcr-server>:5060

For example: pcr registry set http://localhost:5060

Creating a Channel/Login to existing Channel

# if creating Channel
pcr registry register -c <Channel Name> -p <password> -e <email>  [Note password should be minimum of 4 characters]

# if logging in
pcr registry login 

Uploading package:

Assuming you went through all the steps to build your pacakge via conda build ..., you can upload your package by

pcr upload path/to/pkg

# example
pcr upload dist/noarch/numpy-0.1.1-py_0.tar.bz


Installing package:

For searching or Installing a package you need to use conda command. You need to give full url with channel name you have created.

# example

Assuming that we have created a channel named as "citi-pcr", then we will use the url with port number 5050.

conda search -c http://localhost:5050/citi-pcr  --override-channel
conda install numpy -c http://localhost:5050/citi-pcr  --override-channel


