# Customer Sentiment Analysis Report Generator

## Overview

This Python application automates the process of generating a comprehensive customer sentiment analysis report. It leverages the Webz.io eCommerce API and ChatGPT to create detailed reports by analyzing customer reviews of a specified product.

## Features

- **Automated Report Generation:** Generates reports by summarizing up to 50 reviews into positive and negative categories using ChatGPT.
- **Customer Review Analysis:** Splits product reviews into positive and negative feedback for a detailed analysis.
- **Image Generation:** Utilizes DALL-E 3 to create professional cover images for the reports.
- **Sentiment-Based Summarization:** Summarizes feedback based on sentiment (positive/negative) and includes this in the report.
- **Document Formatting:** Creates Word documents with formatted text, hyperlinks, and images.
- **Report Sections:** Includes sections like Analysis of Feedback, Recommendations, and Conclusions, differentiated by sentiment.

## Installation

1. Install required Python packages:
    - `json`
    - `glob`
    - `docx`
    - `requests`
    - `openai`
    - `bs4`

2. Set up an environment variable `OPENAI_API_KEY` with your OpenAI API key.

## Usage

1. Place the product reviews in the `reviews` folder, following the ndjson format.
2. Run the `main()` function to start the report generation process.
3. The application will process the reviews, generate summaries, and compile them into a Word document titled `customer sentiment analysis report.docx`.

## Functions

- `add_image_from_base64(doc, image_url)`: Adds an image to the Word document from a base64 encoded string.
- `html_to_word(doc, html_content)`: Converts HTML content to formatted text in a Word document.
- `add_hyperlink(paragraph, url, text)`: Adds a hyperlink to a Word paragraph.
- `generate_article_image(name)`: Generates an image for the report using DALL-E 3.
- `call_gpt_completion(prompt)`: Calls GPT-4 to generate text based on a given prompt.
- `extract_points(reviews, sentiment)`: Extracts key points from reviews based on sentiment.
- `generate_intro(product_name, product_description)`: Generates an introduction for the report.
- `generate_title(product_name)`: Generates a title for the report.
- `create_negative_report(feedback, product_name)`: Creates a negative sentiment analysis report.
- `create_positive_report(feedback, product_name)`: Creates a positive sentiment analysis report.
- `create_word_doc(...)`: Compiles the entire report into a Word document.
- `read_ndjson_file(file_path)`: Reads ndjson files and returns their content.

## Example

```python
if __name__ == "__main__":
    main()
