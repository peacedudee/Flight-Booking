# Flight Booking Conversational Agent – Google Cloud AI

## Project Overview

This project demonstrates a fully functional conversational agent developed using Google Cloud’s Conversational Agents Console. Designed to simulate a flight booking assistant, the agent facilitates natural, multi-turn dialogue to collect travel details and guide users through a booking flow.

The agent incorporates key conversational AI concepts such as intent recognition, parameter extraction, routing logic, and fulfillment messaging. It has been implemented using the visual, no-code interface provided by Google Cloud and tested in a real cloud environment.

---

## Key Features

- Built using Google Cloud's no-code Conversational Agents Console
- Multi-turn dialogue flow with context-aware transitions
- Intent-based routing and conditional page transitions
- Parameter extraction using system entities
- Dynamic fulfillment messages and user confirmation handling
- Reset and re-entry logic for incorrect user input
- Exportable for use in other environments or future enhancements

---

## Technology Stack

- Google Cloud Platform (GCP)
- Conversational Agents Console
- Dialogflow API
- AI Applications API
- System Entity Library for Natural Language Understanding (NLU)
- Cloud Logging and Session Parameter Handling

---

## Use Case

The conversational agent functions as a flight booking assistant, enabling users to:

- Enter departure and destination cities
- Specify travel dates (departure and return)
- Provide passenger names
- Confirm or modify the submitted booking details

---

## Implementation Details

### Agent Setup

- Created via the Conversational Agents Console under the "AI Applications" section
- Agent Name: `Flight booker`
- Location: Global
- Logging features enabled for both Cloud Logging and Conversation History

### Intent Structure

- Core intent: `main.book_a_flight`
- Confirmation intents: `confirmation.yes`, `confirmation.no`
- Training phrases include a mix of simple and complex booking-related queries to enhance model accuracy

### Flow and Page Design

- Initial entry point: `Default Start Flow`
- Routes user from the Start Page to `Ticket information` page upon intent match
- After collecting all required parameters, transitions to `Confirm trip` page

### Parameter Extraction

Collected parameters include:

| Parameter         | Entity Type       | Prompt                                      |
|-------------------|-------------------|----------------------------------------------|
| `departure_city`  | `@sys.geo-city`   | "What city would you like the flight to depart from?" |
| `departure_date`  | `@sys.date`       | "What is the month and day of the departure?" |
| `destination_city`| `@sys.geo-city`   | "What is your destination city?"            |
| `return_date`     | `@sys.date`       | "What is the month and day for the return?" |
| `passenger_name`  | `@sys.any`        | "What is the passenger's name?"             |

### Fulfillment and Confirmation

Once all parameters are collected, the agent confirms the details using session parameters and responds as follows:
