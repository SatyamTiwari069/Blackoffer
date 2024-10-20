---------------------------------------Solution - Approach-----------------------------------------


1. Data Extraction:

The first task was to extract article text from the URLs provided in Input.xlsx. For this:

I used Python's requests library to fetch the HTML content of each URL.
The BeautifulSoup library was used to parse the HTML and extract the article title and body.
Only the relevant content (title and paragraphs) was saved to text files in the articles/ folder, ensuring that headers, footers, and ads were excluded.
The extracted articles were saved with their corresponding URL_ID as the filename.

2. Data Analysis:

Once the article text was extracted, I performed text analysis based on the methodology described in Text Analysis.docx:

Sentiment Analysis:

I created functions to compute the positive score, negative score, polarity score, and subjectivity score using a predefined set of positive and negative words.
The positive and negative word dictionaries were loaded from dictionaries/positive-words.txt and dictionaries/negative-words.txt.
Readability Metrics:

Metrics such as Average Sentence Length, Complex Word Count, Fog Index, and Percentage of Complex Words were calculated using tokenized sentences and words.
A helper function count_syllables() was used to determine the number of syllables in a word, which is essential for identifying complex words (words with more than two syllables).
Other Text Metrics:

Word Count, Personal Pronouns, and Average Word Length were computed using simple tokenization and string operations.

The nltk.tokenize module was used to split text into words and sentences.

3. Output:
After performing the analysis on each article, the results were stored in a structured DataFrame and saved to an Excel file (output/output.xlsx), following the format provided in the Output Data Structure.xlsx.

Running the Python Script (main.py)
To run the provided main.py script and generate the output, follow these steps:

1. Install Required Dependencies:
The script depends on several Python libraries. To install all dependencies, run the following command in your terminal:
pip install requests beautifulsoup4 nltk pandas openpyxl

Here’s a breakdown of the dependencies:
requests: For sending HTTP requests to fetch web content.

beautifulsoup4: For parsing HTML content and extracting relevant sections.

nltk: Natural Language Toolkit used for text tokenization (splitting sentences and words) and stopwords handling.

pandas: For handling dataframes and exporting the final output to Excel.

openpyxl: To handle Excel file writing.

2. Running the Script: python main.py

3. Output:

After the script runs, check the following:
The output of the analysis is saved in the output/output.xlsx file.


Important Notes:

Ensure that the stopwords file (stopwords/stopwords.txt) and MasterDictionary (positive-words.txt and 
negative-words.txt) are placed in the appropriate directories.

If you encounter any issues fetching article text due to JavaScript-rendered content, consider using a tool like Selenium for more dynamic content handling.

The script uses NLTK for text tokenization and stopwords handling, which requires an internet connection to download its resources the first time you run it (e.g., punkt tokenizer data).

----------------------------------------------------------------------------------------------------------







