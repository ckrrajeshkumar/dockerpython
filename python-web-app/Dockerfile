FROM ubuntu:latest

# Set working directory
WORKDIR /app

# Install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    apt-get clean

# Copy files into the container
COPY requirement.txt /app/
COPY devops /app/devops/

# Install Python dependencies
RUN pip3 install -r requirements.txt

# Set working directory to your project (assuming manage.py is inside devops/)
WORKDIR /app/devops

# Set the default command
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]





