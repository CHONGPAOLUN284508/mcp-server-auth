# Use official Python slim image
FROM python:3.13-slim

# Set working directory
WORKDIR /app

# Copy everything from current folder into the container
COPY . .

# Upgrade pip and install dependencies
RUN python -m pip install --no-cache-dir --upgrade pip setuptools wheel \
    && python -m pip install --no-cache-dir \
       uv \
       fastmcp \
       httpx \
       yfinance \
       python-dotenv \
       requests

# Set working directory to where the main script is
WORKDIR /app

# Expose port
EXPOSE 8001

# Run the Python script
CMD ["python", "mcpserver.py"]
