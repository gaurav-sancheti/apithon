# Apithon Custom API Testing Framework

## Overview

The Apithon Custom API Testing Framework is a Python-based solution tailored for efficient and comprehensive testing of APIs. It emphasizes ease of integration, adaptability, and thorough testing coverage, making it ideal for ensuring the reliability and performance of your API services.

## Core Components

### `api_clients/`

This directory houses the Python modules that abstract the API endpoints being tested. These client modules are responsible for sending requests to the APIs and receiving responses. They play a crucial role in encapsulating the logic for API interaction, making the tests cleaner and more maintainable.

### `environment_data/`

Contains configuration files and data sets used to define different testing environments. This may include base URLs, authentication credentials, and any other environment-specific settings that are necessary to execute the tests across various stages (development, testing, staging, production).

### `resources/`

A repository for additional files that tests may require, such as JSON schemas for response validation, sample request payloads, and expected response data. This directory helps in organizing resources that support test assertions and data-driven testing.

### `tests/`

The core of the framework, where all test cases are defined. This directory is structured to reflect the API's structure, with subdirectories for different services or resource types. It includes:

- **`tests.api_tests/`**: Contains test modules for each API endpoint, organized by service.
- **`tests.utils/`**: Utility functions and classes that support test implementation, such as custom assertions or setup and teardown routines.

## Getting Started

### Prerequisites

Ensure you have Python 3.x installed on your system. The framework is designed to be compatible with modern Python versions.

### Setup

1. Clone or download the framework to your local environment.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Executing Tests

- **Run all tests for a service**:
  Navigate to the framework's root directory and execute:
  ```bash
  python -m unittest discover -s tests/api_tests/company_service
  ```
  This command runs all tests within the `company_service` module.

- **Run a specific test**:
  Specify the test module and test case:
  ```bash
  python -m unittest tests.api_tests.company_service.test_get_company_happy_paths.TestGetCompany
  ```
  This runs the `TestGetCompany` test case within the `test_get_company_happy_paths` module.

## Testing Strategy

The framework adopts a structured approach to API testing, encouraging clear separation of concerns and reusability:

- **Modular Design**: Organizes tests by service and functionality, allowing for targeted testing and easier maintenance.
- **Data-Driven Testing**: Leverages `environment_data` and `resources` to parameterize tests, facilitating comprehensive test coverage across different scenarios.
- **Extensibility**: Designed to easily accommodate new tests and resources as your API evolves.
