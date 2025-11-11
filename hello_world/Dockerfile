# Use an official Python base image
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy dependencies first (for better caching)
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY app/ ./app

# Expose port for Gunicorn
EXPOSE 5000

# Command to start Gunicorn with 4 workers
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:5000", "app.main:app"]
