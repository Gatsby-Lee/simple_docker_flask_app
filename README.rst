Simple Docker Flask APP
=======================

How to Run
----------

.. code-block:: bash

    # Buid image
    docker build -t simple_docker_flask_app:latest .
    # Run container as daemon with port 5000
    docker run -d -p 5000:5000 simple_docker_flask_app

    # open browser with 127.0.0.0:5000


Flask APP code
----------------

.. code-block:: python

    from flask import Flask
    app = Flask(__name__)

    @app.route('/')
    def hello_world():
        return 'Flask Dockerized'

    if __name__ == '__main__':
        app.run(debug=True,host='0.0.0.0')


Dockerfile
-----------

.. code-block:: cfg

    FROM python:3.6-alpine
    COPY . /app
    WORKDIR /app
    RUN pip install -r requirements.txt
    ENTRYPOINT ["python"]
    CMD ["app.py"]
