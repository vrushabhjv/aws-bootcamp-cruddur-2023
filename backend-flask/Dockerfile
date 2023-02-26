FROM python:3.10-slim-buster
# Inside container
# Make a new folder inside container
WORKDIR /backend-flask

# outside container -> Inside container
# This contains the libraries to install to run the app
COPY requirements.txt requirements.txt

# Inside container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside container to inside container
# . . means everything in the current directory
# first period . means /backend-flask (outside container)
# second period . means /backend-flask (inside container)
COPY . .

# Set environment variables
# Inside container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]