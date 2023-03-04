FROM python:3.10-slim-buster

# Inside container
# make a new folder inside the container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# this contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

# Inside container
# intall the python images used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# '.' everything in the current directories
# first period '.' backend-flask (outside container)
# second period '.' backend-flask (inside container)
COPY . .

# Set Enviroment Variables(Env Vars)
# Inside Container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD(command)
# python3 -mflask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]