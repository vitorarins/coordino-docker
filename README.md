coordino-docker
===============

Dockerized Coordino website

Usage
-----

To create the image `vitorarins/coordino`, execute the following command on the coordino-docker folder:

	docker build -t vitorarins/coordino .

You can now push your new image to the registry:

	docker push vitorarins/coordino


Running your Coordino docker image
------------------------------

Start your image binding the external ports 80 and 3306 in all interfaces to your container:

	docker run -d -p 80:80 -p 3306:3306 vitorarins/coordino

If you want to persist the data from your MySQL DB inside the docker run it like this:
  
	docker run -d -p 80:80 -p 3306:3306 -v <your-local-dir>:/var/lib/mysql vitorarins/coordino

Test your deployment by going to [localhost](http://localhost/)


Correctly installing your Coordino application
---------------------------------------------

After you run the docker, go to [localhost](http://localhost/) and start to install your application. When you are asked for the database configuration, put `root` as the `username` and leave `coordino` as the `database`. If you need to change that, just modify the `database.php` file for your needs.

If you have further questions about the docker image or the Coordino app that I used, go to [Tutum-LAMP](https://github.com/tutumcloud/tutum-docker-lamp) or [Coordino](https://github.com/Datawalke/Coordino) 
