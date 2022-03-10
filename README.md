# The MTG-valence-arousal-Annotator

## Installation with Docker

Install [Docker desktop](https://docs.docker.com/install/) (Mac, Windows) or Docker server and Docker-compose (Linux)

### Configuration

The application is configured by editing the `docker-compose.yml` file.

In the section `environment`, set `CHUNK_NUMBER` to the chunk that you are editing (use three-digit format: `000`, `001`, ..., `010`, ...)

    environment:
      - SOUNDS_PER_PAGE=6
      - CHUNK_NUMBER=099
      
In the section `volumes`, add the full path to the location of your audio 

    volumes:
      - .:/app
      - <path to your audio chunk folder here>:/app/static/tracks


### Startup

Run

    docker-compose up
    
and go to http://localhost:5000


## Manual installation

If you prefer to not use Docker, you can set up the application manually

### macOS and Linux

#### Install dependencies

    virtualenv venv
    source venv/bin/activate
    pip install -r requirements.txt


#### Configure

Export environment variables for settings:

    export SOUNDS_PER_PAGE=6
    export CHUNK_NUMBER=099

Copy your audio files to `static/tracks/`
You can use `CHUNK_NUMBER=example` for development purposes.

#### Start server
Run

    flask run

and go to: http://localhost:5000/

Choose a task and start annotating!

### Windows

#### Install Anaconda and dependencies

Install Anaconda, following the instructions in [here](https://docs.anaconda.com/anaconda/install/windows/)

Open Anaconda prompt and run:

    conda create --name mtg-emotion
    conda activate mtg-emotion
    conda install flask


#### Configure

Export environment variables for settings:

    SET SOUNDS_PER_PAGE=6
    SET CHUNK_NUMBER=099

Copy your audio files to `static/tracks/`
You can use `CHUNK_NUMBER=example` for development purposes.

#### Start server
Run 

    flask run

and go to: http://localhost:5000/

Choose a task and start annotating!

## License
This application has been made available under the Apache-2.0 license.
See the LICENSE file for more information
