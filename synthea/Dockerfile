FROM openjdk:11-jdk-slim

# Install git, curl, unzip
RUN apt-get update && apt-get install -y git curl unzip && rm -rf /var/lib/apt/lists/*

COPY ./test/ /
# Clone the Synthea repository
#RUN git clone https://github.com/synthetichealth/synthea.git /synthea

# Set working directory
WORKDIR /synthea

# Build the project
RUN ./gradlew build check test

# Set the command to generate data
CMD ["./run_synthea"]
