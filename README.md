# Docker PHPMyAdmin Project

This repository provides a simple way to run phpMyAdmin using Docker and Docker Compose, allowing you to easily connect to local or remote MySQL databases. Configuration is handled through a `.env` file, making it straightforward to switch between different database instances.

## Project Structure

The project contains the following files:

- **docker-compose.yml**: Defines the Docker services to be used, including phpMyAdmin.
- **.env**: Contains environment variables for configuring phpMyAdmin.
- **README.md**: Project documentation.

## Requirements

- Docker
- Docker Compose

## Setup Instructions

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/docker-phpmyadmin-env.git
   cd docker-phpmyadmin-env
   ```

2. Create a `.env` file in the root of the project with the following content:
   ```dotenv
   # .env file
   PMA_HOST=localhost        # The hostname or IP address of your MySQL server
   PMA_USER=root             # The MySQL user to connect with
   PMA_PASSWORD=your_password # The password for the MySQL user
   ```

3. Start the phpMyAdmin container:
   ```sh
   docker-compose up
   ```

4. Access phpMyAdmin in your browser at [http://localhost:8080](http://localhost:8080).

## Connecting to Local or Remote Databases

To connect to different MySQL databases (local or remote), simply edit the `.env` file with the appropriate values:

- **PMA_HOST**: Set to the IP address or hostname of your MySQL server.
- **PMA_USER**: The MySQL username to use.
- **PMA_PASSWORD**: The password for the specified user.

After modifying the `.env` file, restart the service:
```sh
docker-compose down
```
```sh
docker-compose up
```

## Stopping the Container

To stop the container, use:
```sh
docker-compose down
```

## Notes

- Ensure that the MySQL server is accessible from the machine running Docker.
- The phpMyAdmin instance listens on port 8080 by default. You can change this in the `docker-compose.yml` file if needed.

## License

This project is licensed under the MIT License.