# ChapelBot

This project interfaces with the Bookeo API to manage bookings and customer data, with a focus on identifying and handling bookings without on-campus student matches.

## Project Setup

To get started with this project, ensure you have R installed on your system. This project relies on multiple R packages for data manipulation, web scraping, and interacting with APIs. The necessary packages are listed below and included in the initial setup script.

### Required R Packages

- dplyr
- tidyverse
- readr
- usethis
- dotenv
- here
- httr
- lubridate
- jsonlite

### Initial Setup Script

The following setup script checks for the presence of required packages and installs them if they're not already installed. It also sets up the working directory and prepares the environment for executing API requests.

```r
# Package installation and environment setup
if(!require(dplyr)) {install.packages("dplyr"); library(dplyr)}
if(!require(tidyverse)) {install.packages("tidyverse"); library(tidyverse)}
# Add additional package checks and installations here as per the project requirements

setwd(here())
dotenv::load_dot_env(".env")
```

### .env File Configuration

This project uses a `.env` file for managing sensitive information such as API keys. Ensure you have a `.env` file in your project root with the necessary API credentials.

```plaintext
# Contents of the .env file
API_KEY=your_api_key_here
SECRET_KEY=your_secret_key_here
```

### API Interaction

The script interacts with the Bookeo API to fetch booking and customer information. Ensure your API keys are correctly set up in the `.env` file.

### Execution

Run the R script to initiate the process. The script fetches data from the Bookeo API, processes it to identify bookings without on-campus student matches, and handles them accordingly.

## Data Processing

The script includes logic for processing fetched data, identifying specific booking types, and performing actions based on the booking details. It concludes with updating the local data records by appending new non-matching bookings.

### Handling Non-Matching Bookings

Bookings that do not match on-campus students are processed and, if necessary, cancelled through the Bookeo API. The script provides detailed logging for each step of the process.

## Conclusion

This README outlines the setup and operational details of the Bookeo project. Follow the instructions to ensure a smooth project execution. For further assistance, refer to the official Bookeo API documentation.
