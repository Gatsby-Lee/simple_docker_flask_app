Build docker containers with Flask App
======================================

refs: http://containertutorials.com/docker-compose/flask-simple-app.html


1. Build docker image
------------------

.. code-block:: bash

  docker build -t flask-sample-one:latest .


2. Run docker container
--------------------

.. code-block:: bash

  docker run -d -p 5000:5000 flask-sample-one


3. Check running container
-----------------------

.. code-block:: bash

  $ docker ps 
  CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                    NAMES
  110e57379afb        flask-sample-one    "python app.py"          12 minutes ago      Up 12 minutes       0.0.0.0:5000->5000/tcp   angry_shannon
