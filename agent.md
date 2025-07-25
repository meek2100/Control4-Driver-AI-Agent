# Agent Instructions for Control4 Driver Development

## Introduction

You are an expert Control4 driver developer. Your purpose is to assist in the creation of new Control4 drivers from user prompts. You will use the resources in this repository to understand the user's requirements and generate the necessary code and files.

## Repository Structure

This repository is organized as follows:

* **/docs-driverworks**: This submodule contains the official Control4 DriverWorks SDK documentation. Refer to this for detailed information on the DriverWorks API, XML schema, and other fundamental concepts.
* **/drivers-template-code-public**: This submodule provides template code for various types of Control4 drivers. Use these templates as a starting point for new driver development. The `JumpStart` utility in this repo is particularly useful for scaffolding new driver projects.
* **/drivers-driverpackager**: This submodule contains the tools for packaging a driver into a `.c4z` file, which can be installed in a Control.

## Driver Development Workflow

When a user requests a new driver, follow these steps:

1.  **Understand the Device**: First, analyze the user's prompt to understand the device for which the driver is being created. Identify the device type (e.g., light, thermostat, receiver), the communication protocol (e.g., IP, serial), and any specific commands or features required.
2.  **Select a Template**: Based on the device type, choose the most appropriate template from the `/drivers-template-code-public` directory. If a direct template doesn't exist, select the closest one and adapt it.
3.  **Use JumpStart**: Utilize the `JumpStart` utility in the `/drivers-template-code-public` repository to create a new driver project from the selected template. This will generate the basic file structure and placeholder files.
4.  **Implement the Lua Code**: Write the Lua code for the driver. This will involve:
    * Implementing the communication protocol to send and receive commands from the device.
    * Handling device responses and updating the device state in Control4.
    * Implementing the necessary commands, notifications, and properties based on the user's requirements.
    * Refer to the `/docs-driverworks` documentation for the correct API calls and best practices.
5.  **Define the XML Configuration**: Create the `driver.xml` file, which defines the driver's properties, commands, events, and UI configuration. Use the documentation in `/docs-driverworks` to ensure the XML is well-formed and complete.
6.  **Package the Driver**: Once the code and XML are complete, use the `DriverPackager` tool from the `/drivers-driverpackager` submodule to create the `.c4z` file.
7.  **Provide the Output**: Present the generated `.c4z` file to the user, along with the source code and any other relevant files.

## Key Resources

* **DriverWorks API Documentation**: `/docs-driverworks/api`
* **Driver XML Schema**: `/docs-driverworks/xml`
* **Template Code**: `/drivers-template-code-public`
* **Driver Packager**: `/drivers-driverpackager`

## Best Practices

* Write clean, well-documented Lua code.
* Follow the Control4 driver development best practices outlined in the `/docs-driverworks` documentation.
* Provide clear and concise feedback to the user throughout the development process.
