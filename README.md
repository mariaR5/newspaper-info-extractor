# Newspaper Information Extractor

Newspaper Information Extractor is an intelligent text extraction and categorization model powered by Google Gemini 1.5 Flash.
It analyzes newspaper clippings (images) and automatically separates them into individual articles, identifying key details such as headlines, locations, and summaries — all structured into clean, machine-readable JSON format.

This project demonstrates how advanced multimodal AI models can understand complex layouts and linguistic structures in printed media, making large-scale content digitization faster and more accurate.

## Key Features

- Article Segmentation – Detects and separates multiple articles present within a single newspaper image.
- Headline Extraction – Identifies and extracts article titles using visual and linguistic cues.
- Location Recognition – Finds and labels geographical locations mentioned in the text.
- Summarization – Produces concise summaries of each extracted article.
- Structured JSON Output – Outputs data in a clean, structured JSON format for further analysis or storage.

## How It Works

- The image of a newspaper clipping is passed through the Gemini 1.5 Flash model.
- The model interprets both text and layout, identifying article boundaries.
- Using natural language processing, it extracts:
  - Headline
  - Location
  - Summarized Content

The results are returned in structured JSON form, ready for downstream applications like databases or dashboards.

## Implementation Details
- Framework: Google Colab
- Model Used: gemini-1.5-flash
- Language: Python

## Libraries:
- google-generativeai
- pathlib
- IPython.display


The code initializes Gemini with custom temperature and safety settings for consistent, factual extraction.
Each input image is processed as a byte stream and sent to the model along with a system prompt (defining behavior) and a user prompt (defining the task).

## Example Output

For an input image of a newspaper clipping, the model returns:

<pre>
  [
  {
    "headline": "Floods Ravage Northern Punjab",
    "location": "Punjab",
    "summarised_content": "Heavy rainfall caused severe flooding across multiple districts, displacing thousands and damaging infrastructure."
  },
  {
    "headline": "Local School Wins Robotics Championship",
    "location": "Ludhiana",
    "summarised_content": "Students from St. Mary's High School secured first place at the regional robotics contest, showcasing an AI-powered rover."
  }
]
</pre>

## Applications
- Digital Archiving: Transform physical newspapers into searchable digital databases.
- Media Analytics: Automate topic categorization for trend analysis.
- Information Retrieval: Quickly extract structured insights from historical archives.
- AI Research: Demonstrates multimodal prompt design and structured data extraction.

## Future Enhancements
- Integrate OCR preprocessing for improved text clarity on low-resolution scans.
- Support multilingual newspapers.
- Add automatic image segmentation for complex layouts.
- Develop a web interface for real-time uploads and results visualization.
