# step 1
FROM python:2.7-slim

# step 2
RUN pip install Flask
RUN mkdir /web

# step 3
COPY myapp.py /web/

#step 4
CMD python /web/myapp.py
