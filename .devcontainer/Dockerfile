# Use the official Swift image from Docker Hub
FROM swift:5.8

# Ensure apt-get is up to date and install additional tools if needed
RUN apt-get update && apt-get install -y \
    libsqlite3-dev \
    libssl-dev \
    libcurl4-openssl-dev \
    zlib1g-dev \
    git \
    && rm -r /var/lib/apt/lists/*

# Create a directory for your Swift project inside the container
WORKDIR /workspace

# Copy the current directory contents into the container
COPY . .

# Swift package dependencies are fetched and resolved here
RUN swift package resolve

# Command to run after the container is created
CMD ["swift", "run"]
