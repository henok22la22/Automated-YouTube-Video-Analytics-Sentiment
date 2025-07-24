# Automated-YouTube-Video-Analytics-Sentiment
This n8n workflow automatically collects YouTube video statistics, analyzes comment sentiment using an LLM, stores the data, generates performance reports with charts, and sends them via Telegram, email, or WhatsApp. It's triggered on a scheduled basis (daily or weekly).

This system is an automated YouTube channel performance tracker built using n8n. Its primary function is to collect video metrics and audience sentiment, analyze them, and send structured performance reports to stakeholders or creators.
The workflow is designed to run daily or weekly, making it ideal for content creators, marketing teams, agencies, or analytics departments that want regular insights into how their content is performing — both quantitatively (views, likes, comments) and qualitatively (public sentiment in comments).
The pipeline is fully automated, requiring no manual data pulling or reporting. The entire process — from fetching video data to analyzing sentiment, generating charts, and sending reports — is handled by n8n workflows integrated with APIs and LLMs.

# Flow Details:
1.	Scheduled Trigger
    o	The workflow runs daily or weekly based on requirements.
2.	Get Videos List (HTTP Node)
    o	Uses the YouTube API to fetch a list of videos from a channel within a specific timeframe.
3.	For Each Video (HTTP Node)
    o	Retrieves stats (likes, views, comments) and collects comments for sentiment analysis.
4.	Statistics Saved (Database)
    o	Stores video-level metrics in a database.
5.	Sentiment Analysis (LLM)
    o	Analyzes a set number of comments per video using a language model to label them as Positive, Negative, or Neutral.
6.	Store Sentiment (Database)
    o	Stores sentiment data alongside video IDs for deeper analysis.
7.	Further Analysis (Custom Code Node)
    o	Runs Python or JavaScript to calculate engagement/sentiment percentages.
8.	Chart Report (HTTP)
    o	Generates a visual report with video performance and sentiment stats.
9.	Send Report (Telegram/Email/WhatsApp)
    o	Sends the final report to selected channels (based on business needs).

# Technologies/Tools Used:
•	n8n – Workflow automation platform
•	YouTube Data API – Fetches video data and comments
•	LLM (e.g., OpenAI or local model) – For sentiment analysis
•	PostgreSQL or MySQL – To store statistics and sentiment data
•	Python/JavaScript – For custom calculations and chart generation
•	Telegram/Email/WhatsApp – For delivering final reports
