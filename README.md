# AI Smart Travel Planner

## Project Overview

The **AI Smart Travel Planner** is a Python-based application that generates personalized travel plans based on a user's destination, trip duration, budget, number of travellers, interests, and travel type.

The application uses Google's Gemini API (`gemini-2.5-flash`) to generate a detailed travel itinerary. If the Gemini API is not configured or an API error occurs, the application switches to a basic planning mode that creates a sample itinerary and suggested budget breakdown.

## Features

- Collects travel preferences from the user:
  - Destination
  - Number of travel days
  - Total budget (INR)
  - Number of travellers
  - Interests such as nature, adventure, food, shopping, and history
  - Travel type: family, friends, solo, or couple
- Generates an AI-powered travel plan with:
  - Travel overview
  - Day-wise itinerary
  - Popular tourist attractions
  - Food and restaurant suggestions
  - Accommodation suggestions
  - Estimated budget breakdown
  - Important travel tips
  - Best time to visit
- Provides a basic fallback plan if Gemini is unavailable.
- Saves the generated travel plan as a text file and downloads it in Google Colab.

## Technologies Used

- **Python** – application logic and user input
- **Google Gemini API** – AI-generated travel recommendations
- **google-genai** – Python SDK for Gemini
- **Google Colab** – notebook execution environment

## Project File

- `AI_Smart_Travel_Planner.ipynb` – main Jupyter/Google Colab notebook.

## Requirements

- Python 3
- Internet connection (for installing the SDK and using Gemini)
- A Google Gemini API key (optional; required for AI-powered plan generation)
- Google Colab is recommended because the notebook's final cell uses `google.colab.files` to download the output.

## Installation and Setup

### 1. Open the notebook

Upload `AI_Smart_Travel_Planner.ipynb` to [Google Colab](https://colab.research.google.com/) or open it in a compatible Jupyter environment.

### 2. Install the Gemini SDK

Run the first notebook cell:

```bash
pip install -q google-genai
```

### 3. Configure the Gemini API key

Create or obtain a Gemini API key through [Google AI Studio](https://aistudio.google.com/app/apikey).

When prompted by the notebook, enter your API key. The key is read using `getpass`, so it is not displayed in the notebook output.

If you press Enter without entering a key, the application uses its basic travel-planning mode.

**Security:** Do not hard-code, publish, or commit your API key to a public repository.

## How to Run

1. Open the notebook in Google Colab.
2. Run the notebook cells in order, from top to bottom.
3. Enter your Gemini API key when prompted, or press Enter to skip it.
4. Provide the requested travel details:
   - Destination
   - Number of days
   - Total budget in INR
   - Number of travellers
   - Interests
   - Travel type
5. The application generates and displays the travel plan.
6. The final cell saves the plan as `AI_Smart_Travel_Plan.txt` and downloads it in Google Colab.

## How It Works

1. **Input collection:** The notebook asks the user for travel details and preferences.
2. **Prompt generation:** The application prepares a prompt containing the supplied details and requested sections of the itinerary.
3. **AI plan generation:** If a Gemini client is configured, the application calls the `gemini-2.5-flash` model to generate the travel plan.
4. **Fallback handling:** If no API key is supplied or the API call fails, the application generates a basic sample plan with a day-wise outline and percentage-based budget allocation.
5. **Output:** The generated plan is displayed and saved to a text file.

## Basic Fallback Budget Allocation

When the basic planning mode is used, the total budget is divided as follows:

| Expense Category | Suggested Allocation |
|---|---:|
| Accommodation | 30% |
| Food | 20% |
| Transportation | 20% |
| Sightseeing | 20% |
| Other expenses | 10% |
| **Total** | **100%** |

This is a suggested allocation, not a live quotation.

## Output

The notebook generates:

- A travel plan displayed in the notebook.
- `AI_Smart_Travel_Plan.txt` – a downloadable text file containing the generated plan.

## Important Notes and Limitations

- AI-generated attractions, restaurants, accommodation suggestions, costs, and schedules should be independently verified.
- Prices, opening hours, transport schedules, ticket availability, and accommodation availability may change.
- The application does not make confirmed hotel bookings or ticket reservations.
- The basic fallback mode provides a generic sample itinerary. It does not retrieve verified local attractions, hotel availability, or live prices.
- The current fallback budget calculation divides the total budget by the number of days and uses fixed expense percentages. It does not dynamically validate actual travel costs.
- The notebook expects positive, valid numeric inputs for the number of days, budget, and travellers.
- The final download cell uses Google Colab's `google.colab.files` module. In a local Jupyter environment, that download step may need to be adapted.

## Future Enhancements

Possible improvements include:

- Integrating live maps, routes, and distance estimates.
- Adding real-time weather information.
- Retrieving verified hotel and restaurant information.
- Adding transport cost estimates and travel-time calculations.
- Providing currency conversion for international trips.
- Exporting itineraries to PDF.
- Adding input validation and a graphical user interface.

## Author

Add your name, department, institution, and contact details here if required.

## License

Add the applicable project license before distributing or publishing this project.
