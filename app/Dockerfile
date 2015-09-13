FROM python:2.7
ENV PYTHONUNBUFFERED 1

# Install Python dependencies
RUN mkdir -p /src/app/
COPY requirements.txt /src/app/
RUN pip install -r /src/app/requirements.txt

# Create run/ directory inside /opt/app/ for uwsgi to communicate via socket.
# And ensure we have django user which owns /opt/app/ directory.
# RUN test -d /opt/app/run/ || mkdir -p /opt/app/run/
RUN useradd -ms /bin/bash django
# RUN chown -R django:django /opt/app/

# CMD ["uwsgi", "--ini", "/src/app/uwsgi.ini"]
# WORKDIR /src/app/app/
# VOLUME ["/opt/app/"]
CMD uwsgi --ini /src/app/uwsgi.ini
