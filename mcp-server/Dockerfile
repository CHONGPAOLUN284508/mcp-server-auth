# Use official Python image
FROM python:3.13-slim

# Set working directory
WORKDIR /app

# Copy only the mcp-server folder into the container
COPY mcp-server/ ./mcp-server/

# Install dependencies (if you have a requirements.txt)
# Uncomment if you have one
# COPY requirements.txt .
# RUN pip install --no-cache-dir -r requirements.txt

# Set working directory to where the script is
WORKDIR /app/mcp-server

# Expose the port your app will listen on
EXPOSE 8001

# Run the Python script
CMD ["python", "mcpserver.py"]
