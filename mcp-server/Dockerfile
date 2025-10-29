FROM python:3.13-slim

# Upgrade pip and install uv + dependencies
RUN python -m pip install --no-cache-dir --upgrade pip setuptools wheel \
    && pip install --no-cache-dir uv fastmcp httpx yfinance

# Copy your application into the container
WORKDIR /app
COPY . /app

# Optional: sync dependencies
RUN uv sync --frozen --no-cache || true

# Expose the port your app listens on
EXPOSE 8001

# Start the server
CMD ["python", "-m", "uv", "run", "/app/mcpserver.py"]
