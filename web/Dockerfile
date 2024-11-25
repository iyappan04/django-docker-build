FROM ubuntu:latest as web

WORKDIR /home/app/

ENV PYTHONDONTWRITEBYTECODE 1

ENV PYTHONUNBUFFERED 1


RUN apt-get update && \
    apt-get install -y \
    python3 \
    python3-pip \
    python3-dev \
    build-essential \
    libpq-dev \
    python3-venv \
    && rm -rf /var/lib/apt/lists/*


RUN python3 -m venv /home/app/venv


RUN /home/app/venv/bin/pip install --upgrade pip


COPY ./requirements.txt ./

RUN /home/app/venv/bin/pip install --no-cache-dir -r ./requirements.txt


RUN /home/app/venv/bin/pip install gunicorn


COPY . .


ENV PATH="/home/app/venv/bin:$PATH"

# Expose the app's port (optional)
# EXPOSE 8000
# Command to run the application (optional, if you want to run a server)
# CMD ["gunicorn", "your_app_name.wsgi:application"]
