# HMS MQTT Publisher with Docker Compose

This repository houses a ready-to-use Docker Compose setup for [`hms-mqtt-publisher`](https://github.com/DennisOSRM/hms-mqtt-publisher/), a specialized tool for fetching telemetry data from HMS-XXXXW-2T series micro-inverters and publishing this information to an MQTT broker. This setup is designed to simplify the deployment process significantly, allowing users to get the system up and running without the need for manual compilation or detailed Docker knowledge. For more detailed information about the original project, please visit the [hms-mqtt-publisher GitHub repository](https://github.com/DennisOSRM/hms-mqtt-publisher).

## Details

You can find more details about this solution and alternatives here:

[https://www.worldhack.de/introducing-a-simple-docker-compose-setup-for-hms-mqtt-publisher/](https://www.worldhack.de/introducing-a-simple-docker-compose-setup-for-hms-mqtt-publisher/)

## Overview

The [`hms-mqtt-publisher`](https://github.com/DennisOSRM/hms-mqtt-publisher/) tool, by leveraging the internal DTU (Data Transfer Unit) of the HMS-XXXXW-2T micro-inverters, enables the retrieval of current telemetry information. It supports output to a standard MQTT channel as well as a Home Assistant-friendly channel that includes device auto-discovery.

## Prerequisites

To utilize this Docker Compose setup, ensure you have Docker and Docker Compose installed on your system.

## Configuration and Usage

1. **Clone this repository to get the Docker Compose file:**
   ```shell
   git clone <this-repo-url>
   cd <cloned-repo-directory>
   ```

2. **Environment Configuration**
   Before running the service, configure the provided `config.toml` file. The latest version of `config.toml` can be found [here](https://github.com/DennisOSRM/hms-mqtt-publisher/blob/main/config.toml).

3. **Launch with Docker Compose:**
   Execute the following command to start the service:
   ```shell
   docker-compose up -d
   ```

This command deploys the [`hms-mqtt-publisher`](https://github.com/DennisOSRM/hms-mqtt-publisher/) within a Docker container, using the settings provided through the environment variables and the `config.toml` file. The Docker Compose setup ensures that the tool is compatible with `amd64`, `arm/v7`, and `arm64` architectures.

## Home Assistant

For Home Assistant users, the tool supports auto-discovery of devices, making integration into your Home Assistant setup seamless. Ensure to review the `config.toml` file for Home Assistant-specific configurations.

## Important Considerations (As of 2024/03)

- Use this tool at your own risk. While it is designed with safety in mind, incorrect usage could potentially harm your inverter.
- The inverter's firmware limits data update frequency to approximately every 30 seconds. Attempting updates more frequently might result in duplicate data readings.
- Although primarily developed for HMS-800W-2T, this tool has not been extensively tested across the entire HMS-XXXXW-2T series.

## Acknowledgments

This Docker Compose setup is based on the original [`hms-mqtt-publisher`](https://github.com/DennisOSRM/hms-mqtt-publisher/) project. We extend our gratitude to the creators and contributors of the original tool for their innovative work.