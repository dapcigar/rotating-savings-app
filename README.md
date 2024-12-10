# ROSCA (Rotating Savings Groups) Application

A modern platform for managing rotating savings and credit associations (ROSCAs). Create and manage savings groups with secure, transparent financial transactions.

## Quick Start Guide

1. **Install Required Software**
   ```bash
   # Install Node.js and npm
   curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
   sudo apt-get install -y nodejs

   # Install Docker
   curl -fsSL https://get.docker.com -o get-docker.sh
   sudo sh get-docker.sh

   # Install Docker Compose
   sudo curl -L "https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   sudo chmod +x /usr/local/bin/docker-compose
   ```

2. **Get the Code**
   ```bash
   # Clone repository
   git clone https://github.com/your-org/rosca-app.git
   cd rosca-app
   ```

3. **One-Command Setup**
   ```bash
   # This will set up everything you need
   ./setup.sh
   ```
   Or follow these manual steps:

   ```bash
   # Copy example environment file
   cp .env.example .env

   # Start all services with Docker
   docker-compose up -d

   # Install dependencies
   npm install

   # Run database setup
   npm run db:setup
   ```

4. **Start the App**
   ```bash
   # Start everything
   npm run dev
   ```

   The app will be running at:
   - Frontend: http://localhost:3000
   - API: http://localhost:8000

## Common Issues

1. **Port Already in Use**
   ```bash
   # Check what's using the port
   sudo lsof -i :3000
   # Stop the process
   sudo kill -9 <PID>
   ```

2. **Database Connection Failed**
   ```bash
   # Restart database container
   docker-compose restart postgres
   ```

3. **Node Modules Issues**
   ```bash
   # Clean install
   rm -rf node_modules
   npm cache clean --force
   npm install
   ```

## Need Help?

- Create an issue on GitHub
- Join our Discord: [link]
- Email: support@roscaapp.com

## Development

```bash
# Start in development mode
npm run dev

# Run tests
npm test

# Build for production
npm run build
```

## Docker Commands

```bash
# Start all services
docker-compose up -d

# Stop everything
docker-compose down

# View logs
docker-compose logs -f

# Rebuild containers
docker-compose up -d --build
```

## Environment Setup

Edit `.env` file:
```bash
PORT=3000
DB_URL=postgresql://user:pass@localhost:5432/rosca
REDIS_URL=redis://localhost:6379
```

## That's it!

The app should now be running. Create an account at http://localhost:3000/signup to get started.

Need more help? Check the full documentation in `/docs` or create an issue on GitHub.