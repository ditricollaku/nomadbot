# NomadBot

A Telegram assistant built with n8n that acts as an autonomous travel and weekend concierge. It fetches live forecasts, air quality, currencies, and nearby attractions, then uses an LLM to write a day-by-day itinerary.

## What it does
* **/weather [city]**: Fast path for a 3-day weather forecast.
* **/places [city]**: Fast path for nearby notable places via Wikipedia.
* **Free text**: AI pipeline that identifies up to 3 cities, fetches live API data, and generates a custom day-by-day itinerary.

## Architecture
Three workflows, one job each (exported in `workflows/`):
* `n8n NomadBot.json`: Main router, memory handler (via Google Sheets), and AI pipeline.
* `city_info_subworkflow.json`: Fast path for quick, non-AI weather and places lookups.
* `city_data_subworkflow.json`: Data aggregator fetching from Open-Meteo, RestCountries, Frankfurter, and OpenTripMap.

*No-Code Software Development project, Ditri ÇOLLAKU, ESSEC.*
