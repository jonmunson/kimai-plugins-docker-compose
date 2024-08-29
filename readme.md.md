# Kimai Docker Setup with Plugin Support

By @jonmunson

This repository contains the setup for running Kimai using Docker with support for easy plugin management.

## Files included:
- `docker-compose.yml`: Docker Compose file to set up Kimai with MySQL and plugin support.
- `.env`: Environment variables file to store sensitive information.
- `README.md`: This README file.

## How to use:
1. **Clone the repository**:
   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```

2. **Configure Environment Variables**:
   - Edit the `.env` file to set your MySQL and Kimai configurations.

3. **Create the plugins directory**:
   ```bash
   mkdir plugins
   ```

4. **Download and extract plugins**:
   - Download the desired plugin (e.g., `ImporterBundle`) and extract it into the `plugins` directory:
     ```bash
     unzip ImporterBundle.zip -d ./plugins/
     ```

5. **Start the containers**:
   ```bash
   docker-compose up -d
   ```

6. **Clear cache**:
   - After placing the plugin, clear the cache to ensure Kimai recognizes the new plugin:
     ```bash
     docker-compose exec kimai /opt/kimai/bin/console cache:clear
     ```

7. **Verify the plugin**:
   - Log in to your Kimai instance and check the settings to confirm that the plugin is installed and active.

## Notes:
- The `plugins` directory is mounted into the Kimai container, making it easy to manage plugins without rebuilding the Docker image.
- Ensure that all plugins are compatible with your version of Kimai.

This setup should streamline the process of managing plugins in your Dockerized Kimai installation.
