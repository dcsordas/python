FROM python:3

# copy resources
ADD data/ /data/
COPY /requirements.txt .

# add service
ADD lib/ /lib/
ADD api_view/ /api_view/

# install
WORKDIR /
RUN apt-get update
RUN pip install -r requirements.txt

# set up SQLite database
ADD data/ /data/
RUN python -m api_view.setup_db

# run
CMD python -m api_view run
EXPOSE 8001
