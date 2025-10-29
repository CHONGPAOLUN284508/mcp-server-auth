# Use official Python slim image
FROM python:3.13-slim

# Set working directory
WORKDIR /app

# Copy everything from current folder into the container
COPY . .

# Upgrade pip and install all required Python dependencies
RUN python -m pip install --no-cache-dir --upgrade pip setuptools wheel \
    && python -m pip install --no-cache-dir \
       uv \
       fastmcp \
       httpx \
       yfinance \
       python-dotenv \
       requests

# Set working directory to the script folder
WORKDIR /app

# Expose the port your app listens on
EXPOSE 8001

# Run the Python script
CMD ["python", "mcpserver.py"]
