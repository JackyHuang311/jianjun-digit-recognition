# jianjun-digit-recognition
# Introduction 

This project is constructed by two docker Containers: an Application Docker Container and a Database Docker Container.
While the user submits ports in any browser, the Flask Router will link to the HTML5 file. In the HTML5 file, there is a canvas which user can use mouse to draw. The Router then saves the handwritten image and requests the prediction from the MNIST Keras model. After the result returns, the Router forwards the result to HTML5 and show it to user via browser and submits all two data to the Cassandra Database Container through the Docker Network Bridge.

The main job of this project is to identify the user's handwritten numbers. The user can draw a number on the canvas and automatically start predicting the image in the results display area, which will return the result on the right side of the page. If the user is not satisfied or the prediction result is not accurate, you can also press the "Clear" button to clear the graph and make the next recognition. Each time, the forecast and date are recorded in the Cassandra database.

![screencast](https://github.com/JackyHuang311/jianjun-digit-recognition/raw/master/2.gif)

### Requirement ###

- Python >=2.7 or >=3.4
- TensorFlow >=1.0
- Node >=6.9


### How to run ###

    $ pip install -r requirements.txt
    $ npm install
    $ gunicorn main:app --log-file=-


### Deploy to Heroku ###

    $ heroku apps:create [NAME]
    $ heroku buildpacks:add heroku/nodejs
    $ heroku buildpacks:add heroku/python
    $ git push heroku master

or Heroku Button.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)
