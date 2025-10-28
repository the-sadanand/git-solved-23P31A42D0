# DevOps Simulator

A comprehensive CI/CD configuration and configuration-management toolkit focused on stable production deployments.

## Project Status
- **Version**: 1.0.0 (Production)
- **Environments**: Production & Development
- **Student**: SADANAND KUMAR
- **Student ID**: 23P31A42D0

## Features

### Core / Legacy Features
- Automated deployment scripts
- Real-time monitoring
- Configuration management
- Backup and recovery system
<<<<<<< HEAD

### Production Features
- SSL/TLS encryption
- Auto-scaling
- Load balancer integration
- Scheduled backups

### Development Features (Beta)
- Docker Compose integration
- Hot reload enabled
- Debug mode active
- Enhanced logging
- Mock external APIs

## Quick Start

### Production Mode (recommended)
On POSIX shells:
```bash
export DEPLOY_ENV=production
./scripts/deploy.sh
```
On PowerShell (Windows):
```powershell
$env:DEPLOY_ENV = 'production'
./scripts/deploy.sh
```

### Quick Start - Standard/Test Mode
1. Clone the repository
2. Configure environment variables (see `config/app-config.yaml` and `config/database-config.json`)
3. For development or local testing, set `DEPLOY_ENV=development` and run `./scripts/deploy.sh` or use `docker-compose` as documented in `/docs`.

## Experimental Features (NOT PRODUCTION-READY)

The repository contains an experimental branch of features (AI/ML integration, multi-cloud orchestration, chaos engineering) that are intentionally isolated from the production defaults. These features are kept in the repo for testing and research only.

Important rules:
- Production configuration and behavior are primary and must remain stable.
- Experimental features are disabled by default and must be explicitly enabled.
- Experimental capabilities may require extra services, credentials, or model artifacts and can be unstable.

How to enable experimental features (testing only):
1. Use a dedicated test environment—do not enable experimental features in production.
2. In `config/app-config.yaml` set `experimental.enabled: true` and review the experimental block.
3. In `config/database-config.json` set `experimental.enabled: true` if you want to test the distributed DB config.
4. Set `DEPLOY_ENV=experimental` (or use PowerShell: `$env:DEPLOY_ENV='experimental'`) and run `./scripts/deploy.sh`.
5. Monitor closely and keep rollback/backup plans ready.

### Example (experimental, testing only)
```bash
# Warning: testing only
export DEPLOY_ENV=experimental
./scripts/deploy.sh
```

## AI Integration (experimental)
The repository contains experimental AI features such as predictive scaling and anomaly detection. These are documented in `/docs` and must only be used in non-production environments.

## Documentation
See the `/docs` folder for architecture, operational runbooks, and any experimental guides (e.g., `/docs/ai-integration.md`).

## Warning
⚠️ Experimental features are not production-ready. Enable only in dedicated test environments and after reviewing configuration flags.

## License
MIT License

## FAQ
<<<<<<< HEAD
update
=======
=======
- **NEW**: Multi-cloud support (AWS, Azure, GCP)
- **NEW**: Slack/Discord notifications

## Quick Start
1. Clone the repository
2. Install dependencies: `npm install`
3. Configure environment variables
4. Run in development mode: `npm run dev`
5. Access dashboard at http://localhost:3000

## Development Setup
```bash
# Install dependencies
npm install

# Run tests
npm test

# Start development server
npm run dev
```

## Documentation
See `/docs` folder for detailed documentation.

## Contributing
Please read CONTRIBUTING.md before submitting pull requests.

## License
MIT License
>>>>>>> 02011a5 (updating dev)
>>>>>>> 07c8731 (feat: Add test feature)
