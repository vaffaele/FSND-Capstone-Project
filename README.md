FSND Casting Agency Capstone project
capstone project for the udacity full stack nanodegree program.

Heroku link: (https://casting-agency-vaffaele.herokuapp.com/)
Getting Started
Installing Dependencies
Python 3.7

Follow instructions to install the latest version of python for your platform in the python docs
PIP Dependencies

Once you have your virtual environment setup and running, install dependencies by naviging to the /backend directory and running:

pip install -r requirements.txt

This will install all of the required packages we selected within the requirements.txt file.
Key Dependencies

    Flask is a lightweight backend microservices framework. Flask is required to handle requests and responses.

    SQLAlchemy is the Python SQL toolkit and ORM we'll use handle the lightweight sqlite database. You'll primarily work in api.py and can reference models.py.

    Flask-CORS is the extension we'll use to handle cross origin requests from our frontend server.

Running the server

To run the server, execute:

export FLASK_APP=app.py
export FLASK_ENV=debug
flask run --reload

Casting Agency Specifications

The Casting Agency models a company that is responsible for creating movies and managing and assigning actors to those movies. You are an Executive Producer within the company and are creating a system to simplify and streamline your process.
Models

Movies with attributes contain title, year, director and genre Actors with attributes name, role and gender
Environment Variables

In the .env file, the JWT token for each User Role

    CASTING_ASSISTANT
    CASTING_DIRECTOR
    EXECUTIVE_PRODUCER

Roles

Casting Assistant

    get:actor
    get:movie

Casting Director
All permissions a Casting Assistant has

    post:actor
    delete:actor
    patch:actor
    patch:movie

Executive Producer
All permissions a Casting Director has

    post:movie
    delete:movie

Endpoints

GET '/actors'

reponse = {
success: True,
actors: [
          {
            first_name: "Jhonny",
            last_name: "Depp",
            gender: "Male",
	    age: 53,
	    image_link:"link-to-image"
          },
          {
            first_name: "Tom",
            last_name: "Hanks",
            gender: "Male",
	    age: 64,
	    image_link:"link-to-other-image"
          }
        ]
  }


POST '/actors'

payload = {
         first_name: "Jhonny",
         last_name: "Depp",
         gender: "Male",
	 age: 53,
	 image_link:"link-to-image"
  }
response = {
  success: True,
  actor:actor.id
}

PATCH '/actors/<int:actor_id>'

params = <int:actor_id>

response = {
  success: True,
  actor:actor.id
}

DELETE '/actors/<int:actor_id>'

params = <int:actor_id>

response = {
  success: True,
  delete: actor_id
}

GET '/movies'

response = {
success: True,
movies: [
          {
            title: "Fury",
            release_date: 2019-01-01,
            image_link: "image-link",
          },
          {   
            title: "Fight Club",
            year: 1999-02-20,
            image_link: "image-link",
          }
        ]
  }


POST '/movies'

payload = {
         title: "Fury",
         release_date: 2019-01-01,
         image_link: "image-link",
  }
response = {
  success: True,
  movie: movie.id
}

PATCH '/movies/<int:movie_id>'

params = <int:movie_id>

response = {
success: True,
movies: movie.id
        
  }


DELETE '/movies/<int:movie_id>'


params = <int:movie_id>

response = {
  success: True,
  delete: movie_id
} 

Testing

To run the tests

python test_app.py
