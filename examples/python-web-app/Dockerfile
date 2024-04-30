FROM ubuntu

# Update package list and install Python and pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    apt-get install -y python3-venv && \
    python3 -m venv /venv

# Set the working directory
WORKDIR /app

# Copy requirements.txt and install dependencies
COPY requirements.txt /app/
RUN /venv/bin/python -m pip install --no-cache-dir -r requirements.txt

# Copy the application code
COPY devops /app/

# Set the command to run the application
CMD ["/venv/bin/python", "manage.py", "runserver", "0.0.0.0:8000"]




