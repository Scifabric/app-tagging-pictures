PyBossa demo project tagging pictures
=====================================

The project has four main files:

* **project.json**: a JSON file that describes the project.
* **long_description.md**: a Markdown file with a long description of the
  project.
* **template.html**: the task presenter where the user/volunteer will do the image
  tagging.
* **tutorial.html**: a simple tutorial for the volunteers.

![alt screenshot](http://i.imgur.com/RFfU4uT.png)

Testing the project
===================

You need to install the pybossa-pbs. If you don't have a virtual environment,
we recommend you to create one, and activate it:

```bash
    $ virtualenv env
    $ source env/bin/activate
```

Then, you can install pybossa-pbs:

```bash
    $ pip install pybossa-pbs
```

## Creating an account in a PyBossa server
Now that you've all the requirements installed in your system, you need
a PyBossa account:

*  Create an account in your PyBossa server (use [Crowdcrafting](http://crowdcrafting.org) if you want).
*  Copy your API-KEY (you can find it in your profile page).

## Configure pybossa-pbs command line

PyBossa-pbs command line tool can be configured with a config file in order to
avoid typing the API-KEY and the server every time you want to take an action
on your project. For this reason, we recommend you to actually create the
config file. For creating the file, follow the next steps:

```bash
    $ cd ~
    $ editorofyourchoice .pybossa.cfg
```

That will create a file. Now paste the following:

```python
[default]
server: http://yourpybossaserver.com
apikey: yourapikey
```

Save the file, and you are done! From now on, pybossa-pbs will always use the
default section to run your commands.

## Create the project

Now that we've everything in place, creating the project is as simple as
running this command:

```bash
    $ pbs create_project
```

## Adding some tasks

Now we can add some tasks. The project comes with a set of sample tasks that you
can use:

 * taggingpictures_task.json: a JSON file with some tasks

### Using a JSON or CSV file for adding tasks

This is very simple too, thanks to pbs:

```bash
    $ pbs add_tasks --tasks-file taggingpictures_task.json
```
Or, alternatively, use a CSV file:

```bash
    $ pbs add_tasks --tasks-file taggingpictures_task.csv
```
You'll get a progress bar with the tasks being uploaded. Now your project has
some tasks in the server to be processed by the volunteers.

## Finally, add the task presenter, tutorial and long description

Now that we've some data to process, let's add to our project the required
templates to show a better description of our project, to present the tasks to
our users, and a small tutorial for the volunteers:

```bash
    $ pbs update_project
```

Done! Now you can do image pattern recognition problems in the PyBossa server.

**NOTE**: we provide templates also for Bootstrap v2 in case your PyBossa
server is using Bootstrap2 instead of Bootstrap3. See the rest of the files.

Documentation
=============

We recommend that you read the section: [Build with PyBossa](http://docs.pybossa.com/en/latest/build_with_pybossa.html) and follow the [step by step tutorial](http://docs.pybossa.com/en/latest/user/tutorial.html).

**NOTE**: This application uses the [pybossa-client](https://pypi.python.org/pypi/pybossa-client) in order to simplify the development of the application and its usage. Check the [documentation](http://pythonhosted.org/pybossa-client/).

LICENSE
=======

Please, see the COPYING file.

Acknowledgments
===============
The thumbnail has been created using a [photo](http://www.flickr.com/photos/cambodia4kidsorg/260004685/in/photostream/) from cambodia4kidsorg (license CC BY 2.0). 
