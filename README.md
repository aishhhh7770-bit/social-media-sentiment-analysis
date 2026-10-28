# Sapphire Pakistan -- YouTube Advertisement Sentiment Analysis

An interactive Streamlit dashboard for exploring audience reactions to
Sapphire Pakistan's YouTube advertisements using pre-labeled comment
data.

## Project Overview

The dashboard summarizes YouTube comments by sentiment (positive,
negative, and neutral), compares advertisement performance, and lets
users search, filter, inspect, and download comment data. It also
includes data-quality checks and a light/dark display theme.

**Important:** The current application uses sentiment labels already
present in the dataset. It does not train a machine-learning model,
predict sentiment for newly entered text, or automatically collect live
YouTube comments.

## Features

-   **Overview:** Summary metrics and charts for comment sentiment.
-   **Sentiment:** Breakdown of sentiment labels and frequently
    discussed aspects.
-   **Advertisement Performance:** Compare comment volume, sentiment,
    and engagement across advertisements.
-   **Comments:** Search and filter comments, inspect records, and
    download filtered data.
-   **Data Quality:** Review missing values, duplicate records, and
    related dataset-quality information.
-   **Filters:** Filter by advertisement, sentiment, and minimum likes.
-   **Appearance:** Switch between Light and Dark themes.
-   **CSV downloads:** Export selected or filtered results where
    available.

## Technology Stack

-   **Python** -- application logic
-   **Streamlit** -- interactive web interface
-   **pandas** -- loading, cleaning, filtering, and summarizing CSV data
-   **Plotly** -- interactive charts
-   **CSV** -- dataset storage

## Project Files

``` text
sapphire_sentiment_analysis-main/
├── app.py
├── requirements.txt
├── sapphire_youtube_comments_labeled.csv
└── scaling_results.csv
```

-   `app.py` --- main Streamlit application.
-   `requirements.txt` --- required Python packages.
-   `sapphire_youtube_comments_labeled.csv` --- main labeled YouTube
    comments dataset.
-   `scaling_results.csv` --- supporting performance/scaling results
    used by the dashboard.

Keep the CSV files in the same directory as `app.py`, because the
application loads them using paths relative to the project folder.

## Requirements

-   Python 3.10 or newer recommended
-   Internet access for the initial installation of packages
-   Windows, macOS, or Linux

## How to Run

### 1. Extract and open the project

Extract the ZIP archive. Open the extracted
`sapphire_sentiment_analysis-main` folder in VS Code, or open a terminal
in that folder. Confirm that `app.py` and `requirements.txt` are
visible.

### 2. Create a virtual environment (recommended)

**Windows (Command Prompt):**

``` bash
python -m venv .venv
.venv\\Scripts\\activate
```

**macOS / Linux:**

``` bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

``` bash
python -m pip install -r requirements.txt
```

If `python` is not recognized on Windows, try `py` in place of `python`.

### 4. Launch the dashboard

``` bash
streamlit run app.py
```

Streamlit will print a local URL in the terminal, usually:

``` text
http://localhost:8501
```

Open that address in your browser. Keep the terminal open while using
the dashboard. To stop the application, press `Ctrl+C` in the terminal.

## How to Use

1.  Choose Light or Dark mode in the sidebar.
2.  Use the available sidebar filters to narrow the comments by
    advertisement, sentiment, or minimum likes.
3.  Explore the Overview, Sentiment, Advertisement Performance,
    Comments, and Data Quality tabs.
4.  Search the comments and use the download buttons to export results
    when needed.

## Dataset and Methodology

The main CSV contains labeled comment records and fields such as comment
text, video/comment identifiers, dates, like and reply counts, sentiment
labels, and aspect labels. The app loads the data with pandas, prepares
fields for display, applies filters, calculates summary statistics, and
visualizes results with Plotly.

Interpret results in the context of the supplied dataset. Sentiment
counts reflect the labels stored in the CSV; they are not evidence that
the application independently predicted each comment's sentiment.

## Limitations and Future Improvements

-   Sentiment quality depends on the correctness and consistency of the
    supplied labels.
-   The dashboard does not currently scrape or fetch new YouTube
    comments.
-   The dashboard does not train or run a sentiment-classification
    model.
-   Possible future work includes connecting an authorized YouTube data
    source, adding a trained NLP classifier, and evaluating model
    performance on manually verified examples.

## Troubleshooting

-   **`streamlit` is not recognized:** Activate the virtual environment
    and run `python -m pip install -r requirements.txt` again. You can
    also start it with `python -m streamlit run app.py`.
-   **CSV file not found:** Make sure both CSV files are in the same
    folder as `app.py`, and run the command from that folder.
-   **`python` is not recognized:** Reinstall Python and enable "Add
    Python to PATH", or try `py`.
-   **Port 8501 is busy:** Use
    `streamlit run app.py --server.port 8502`.

## License

No license file was included in the supplied project archive. Add a
license if you intend to publish or redistribute the project publicly.
