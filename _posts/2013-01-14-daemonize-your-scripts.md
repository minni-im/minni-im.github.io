---
layout: post
title: Daemonize your nodejs scripts
categories: code
---

<!-- excerpt start -->
The one that ever needed to run a [Nodejs][nodejs] application in a production environment,
perfectly know what I am talking about:

> Welcome to the Jungle

You have so many different choices. Especially on Linux. Let's try to detail the most 2 relevant to me: Forever and Upstart

<!-- excerpt end -->
## Forever

[Forever][forever] is a solution provided by [Nodejitsu][nodejitsu] written itself in JavaScript for Nodejs. It's been describe as

> A simple CLI tool for ensuring that a given script runs continuously (i.e. forever)

As a lot of Nodejs libraries, you can install it globally via [Npm][npm]

    $ npm install -g forever

Then you can start your script to run forever:

    $ forever start myscript.js

You can actually check that it has been launched with the _list_ command

    $ forever list

By default, it will used the default `stdout` and `stderr`. If you want to redirect everything to dedicated file logs, you could use these options

    $ forever -l /path/to/log/myscript.log -o /path/to/log/myscript_out.log -e /path/to/log/myscript_err.log myscript.js

## Upstart

[Upstart][upstart] is considered to be the new _/etc/init.d/\*_ service scripts on Ubuntu, or at least it is said to be its successor. It is installed by default.

We want upstart to be able to manage our nodejs application as a standard service. Which means that we want to start, stop and monitor our script.

First let's create a job script, called _node3000_ (we give it as a name the port number on which it'll start)

	$ vim /etc/init/node3000.conf

Then, we need to tell upstart what to do

	#!upstart

	description "node3000"
	author "benoit"

	start on (local-filesystems and net-device-up IFACE=eth0)
	stop on shutdown

	respawn				# restart when job dies
	respawn limit 5 60	# give up restart after 5 retries in 60 sec

	script
		exec sudo -u www-data /usr/local/bin/node /srv/nodejs/myapp/app.js >> /srv/nodejs/myapp/logs/myapp.log 2>&1
	end script

Before starting your job, make sure everything is ok on the logs side

	$ touch /srv/nodejs/myapp/logs/myapp.log
	$ chmod 755 /srv/nodejs/myapp/logs/myapp.log

Finally you can ask upstart to start your daemon

	$ start node3000

You application should now be running and available.


[npm]: http://npmjs.org
[nodejitsu]: http://nodejitsu.com
[forever]: https://github.com/nodejitsu/forever
[nodejs]: http://nodejs.org
[upstart]: http://upstart.ubuntu.com/