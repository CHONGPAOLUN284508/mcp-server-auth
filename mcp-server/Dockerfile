# Use official Python slim image
FROM python:3.13-slim

# Set working directory
WORKDIR /app

# Copy the application folder
COPY mcp-server/ ./mcp-server/

# Upgrade pip and install all required Python dependencies
RUN python -m pip install --no-cache-dir --upgrade pip setuptools wheel \
    && pip install --no-cache-dir \
       uv \
       fastmcp \
       httpx \
       yfinance \
       # optional extras you might need in future:
       python-dotenv \
       requests

# Set working directory to the script folder
WORKDIR /app/mcp-server

# Expose the port your app listens on
EXPOSE 8001

# Run the Python script
CMD ["python", "mcpserver.py"]
