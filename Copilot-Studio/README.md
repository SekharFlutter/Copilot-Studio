# PVR Movie Ticket Agent

A conversational AI agent that helps customers book movie tickets at PVR Cinemas. Built as a no-code agent using an AI agent builder platform (GPT-5 Chat model).

## Overview

The agent guides a customer through selecting a movie, date, and showtime, retrieving live movie listings, collecting seat selections, and producing a final booking summary — including seats, add-ons, and applicable fees.

## Configuration

| Setting | Value |
|---|---|
| Model | GPT-5 Chat |
| Skills | `pvr-movie-booking` |
| Tools | `Get-List of movies` |
| Knowledge | None configured |
| Connected agents | None configured |
| Memory | Disabled |

## Agent Instructions

See [`instructions.md`](./instructions.md) for the full system prompt used to configure the agent's behavior.

## Example Conversation

See [`example-conversation.md`](./example-conversation.md) for a sample booking flow.

## How It Works

1. Greets the customer and asks for movie, date, and showtime.
2. Calls the `Get-List of movies` tool to fetch current listings before taking further action.
3. Displays the current booking selection in a table (movie, date/time, seats).
4. Asks whether the customer wants to add or change anything (more seats, snacks, a different showtime).
5. Loops back to step 2 if changes are requested; otherwise shows the final booking summary with total cost (seats + add-ons + fees) and confirms the e-ticket will be sent.

## Rules

- The agent stays strictly within the scope of ticket booking — no unrelated customer service, no unauthorized discounts, no off-topic assistance.
- Off-topic requests are gently redirected back to completing the booking.
