# Meadmaking Wiki

A modern Wiki.js instance hosting the meadmaking community knowledge base, migrated from [meadmaking.wiki](https://meadmaking.wiki) and originally from the [r/mead](https://reddit.com/r/mead) wiki.

## About

This wiki covers the basics of making mead and serves as a comprehensive resource for the meadmaking community. The content was migrated on December 11, 2025, and continues to be maintained and expanded by the community.

## Local Development Setup

### Prerequisites

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)
- Git

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/meadmaking-wiki.git
   cd meadmaking-wiki
   ```

2. **Create environment file**
   ```bash
   cp .env.example .env
   ```

3. **Configure environment variables**
   Edit `.env` file with your preferred database credentials:
   ```env
   DB_PORT=5432
   DB_USER=wikiuser
   DB_PASS=your_secure_password
   DB_NAME=wikidb
   ```

4. **Start the services**
   ```bash
   docker-compose up -d
   ```

5. **Access the wiki**
   Open your browser and navigate to `http://localhost:3000`

6. **Initial setup**
   Follow the Wiki.js setup wizard to:
   - Create an administrator account
   - Configure your wiki settings
   - Set up content synchronization (optional)

### Importing Content

The wiki content is stored in the `/content` directory and can be imported using Wiki.js's file system sync feature:

1. Navigate to **Administration > Storage**
2. Add a new **Local File System** storage target:
   - **Path**: `/content`
   - **Apply To**: `pages`
   - **Read-only**: Enable if you don't want Wiki.js to modify source files
3. Configure sync schedule in **Administration > Jobs**

### Project Structure

```
├── content/           # Wiki content (Markdown files)
│   └── en/           # English content
│       ├── faq/      # Frequently asked questions
│       ├── guides/   # How-to guides
│       ├── ingredients/ # Ingredient information
│       ├── process/  # Process documentation
│       ├── protocol/ # Protocol documentation
│       ├── recipes/  # Recipe collection
│       ├── resources/ # Additional resources
│       └── userrecipes/ # Community recipes
├── scripts/          # Migration and utility scripts
├── docker-compose.yml # Docker services configuration
├── .env.example      # Environment variables template
└── README.md         # This file
```

### Stopping the Services

```bash
docker-compose down
```

To remove all data (including database):
```bash
docker-compose down -v
rm -rf pgdata/
```

## Contributing

Please read the [Wiki Editing Guidelines](content/en/wiki_editing_guidelines.md) before making contributions.

### Content Guidelines

- Use lowercase file names with underscores for spaces
- Remove punctuation from file names
- Provide sources when possible
- Follow the established content structure

## Deployment

### Free Hosting Options

This wiki can be deployed on several free hosting platforms:

- **Render**: Supports Docker deployments with free PostgreSQL
- **Railway**: Simple deployment with one-click database setup
- **Fly.io**: Global deployment with managed databases

See the deployment documentation for platform-specific instructions.

## Support

For technical issues with the wiki platform, please create an issue on GitHub.

For content-related questions or discussions, visit the [r/mead community](https://reddit.com/r/mead).

## License

### Wiki Content
All wiki content in the `/content` directory is licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/).

This means you are free to:
- **Share** — copy and redistribute the material in any medium or format
- **Adapt** — remix, transform, and build upon the material

Under the following terms:
- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made
- **NonCommercial** — You may not use the material for commercial purposes
- **ShareAlike** — If you remix, transform, or build upon the material, you must distribute your contributions under the same license

### Wiki Platform
The Wiki.js platform and deployment configuration files are subject to their respective licenses.

---

**Note**: This wiki instance is currently being established and migrated. Content originally sourced from [meadmaking.wiki](https://meadmaking.wiki) and the [r/mead](https://reddit.com/r/mead) community wiki.