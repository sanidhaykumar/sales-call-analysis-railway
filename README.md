# sales-call-analysis-railway

# Sales Call Analysis

An AI-powered sales call analysis tool that helps analyze and improve sales conversations.

## Quick Start with Docker

1. Create a `.env` file:
```bash
# Required Environment Variables
AUTH_PASSWORD=your-secure-password
JWT_SECRET=your-jwt-secret-min-32-chars-long
OPENAI_API_KEY=your-openai-api-key

# Optional Environment Variables (with defaults)
AUTH_USERNAME=admin
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_DB=sales_call_analysis
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

2. Download the docker-compose file:
```bash
curl -O https://raw.githubusercontent.com/yourusername/sales-call-analysis/main/docker-compose.prod.yml
mv docker-compose.prod.yml docker-compose.yml
```

3. Run the application:
```bash
docker-compose up -d
```

4. Access the application at http://localhost:3000

## Features

- 🎯 Real-time sales call analysis
- 📊 Performance metrics and insights
- 🔒 Secure authentication system
- 🔄 Automatic version updates
- 📝 Detailed call transcriptions
- 🎨 Modern, responsive UI

## Configuration

### Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| AUTH_PASSWORD | Yes | - | Admin password |
| JWT_SECRET | Yes | - | JWT secret (min 32 chars) |
| OPENAI_API_KEY | Yes | - | OpenAI API key |
| AUTH_USERNAME | No | admin | Admin username |
| POSTGRES_USER | No | postgres | Database user |
| POSTGRES_PASSWORD | No | postgres | Database password |
| POSTGRES_DB | No | sales_call_analysis | Database name |
| NEXT_PUBLIC_APP_URL | No | http://localhost:3000 | Public URL |

### Data Persistence

The application uses two Docker volumes:
- `postgres_data`: For database persistence
- `uploads`: For uploaded audio files

## Updating

The application will automatically check for updates. When available:

1. Pull the latest image:
```bash
docker-compose pull
```

2. Restart the services:
```bash
docker-compose down
docker-compose up -d
```

## Security Considerations

- Use strong passwords for both `AUTH_PASSWORD` and `POSTGRES_PASSWORD`
- Keep your `JWT_SECRET` secure and unique
- Protect your `OPENAI_API_KEY`
- Use HTTPS in production (configure `NEXT_PUBLIC_APP_URL` accordingly)

## Troubleshooting

### Common Issues

1. Database Connection
```
Error: Could not connect to database
Solution: Check POSTGRES_* environment variables
```

2. License Validation
```
Error: Invalid license
Solution: Complete the license validation process at first run
```

3. Container Access
```
Error: Cannot access container
Solution: Check if containers are running with 'docker-compose ps'
```

### Health Check

Monitor the application health:
```bash
curl http://localhost:3000/api/health
```

## Support

For issues and support:
1. Check the [Issues](https://github.com/yourusername/sales-call-analysis/issues) section
2. Create a new issue if needed

## License

This project is licensed under the terms of our commercial license. See [LICENSE](LICENSE) for details.
