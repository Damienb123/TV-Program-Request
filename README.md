# TV-Program-Request

## Table of Contents

1. [Overview](#Overview)
2. [Request Body Format](#Request-Body-Format)
3. [Setup Instructions](#Setup-Instructions)
4. [Example Usage](#Example-Usage)
5. [Reference](#Reference)
6. [Conclusion](#Conclusion)

## Overview

The TV-Program-Request API allows users to schedule a TV program recording by specifying the date, time, duration, and channel of the desired program. This documentation provides details on how to format the request and what responses to expect from the API.

## Request Body Format

The request body should be in XML format and contain the following elements:

- <recordTV>: Root element that encapsulates the recording request.
    - <when>: Specifies the date and time for the recording.
        - date: The date of the program to be recorded in YYYY-MM-DD format.
        - time: The time of the program to be recorded in HH:MM format.
        - format: The time format, which should be "24" for 24-hour format.
    - <duration>: Specifies the duration of the recording.
        - hours: The length of the recording in hours (can be a decimal).
    - <station>: Specifies the TV channel for the recording.
        - channel: The channel number.

## Setup Instructions

- Clone the Repository: Clone the project repository to your local machine.
- Install Dependencies: Run the appropriate command to install dependencies (e.g., mvn install for Maven projects).
- Start the Server: Start the server using your preferred method (e.g., mvn spring-boot:run for Spring Boot projects).

## Example Usage

To schedule a TV program recording, send a POST request to the /recordTV endpoint with the following XML body:
```
<recordTV>
    <when date="2015-06-01" time="18:00" format="24"/>
    <duration hours="1.5"/>
    <station channel="54"/>
</recordTV>
```

A successful response will confirm that the recording has been scheduled:
```
{
    "message": "Recording scheduled successfully.",
    "recordingId": 12345
}
```
            
## Reference

For needed thorough analysis of the project, please refer to the attached .pdf documenatation file.

## Conclusion

The TV-Program-Request API enables users to easily schedule TV program recordings by providing the necessary details in an XML request. This documentation outlines the required request format, expected responses, and provides examples to help users get started with the API.
