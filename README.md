# CrixWix
Text Summarization of Cricket Match Videos Using Neural Networks

Workflow:
Workflow Overview:
Convert video to frames (filter out redundant ones).
Detect the scoreboard and extract information like team scores, wickets, and overs.
Structure the extracted data into an organized format.
Generate text descriptions for key frames using deep learning.
Apply NLP-based summarization to produce a final match summary.
🟢 Module 1: Video Frame Conversion
📌 Objective: Convert the input cricket video into frames and filter out redundant ones.

🔹 Steps:

Read video using OpenCV.
Extract frames at regular intervals (e.g., every second).
Filter out redundant frames using a similarity-checking technique:
Compute structural similarity (SSIM) or use a CNN-based feature extractor (e.g., VGG16).
Retain only representative frames to reduce processing time.
🔹 Output: A set of key frames representing important moments in the match.

🟢 Module 2: Scoreboard Detection & Data Extraction
📌 Objective: Identify and extract scoreboard information from key frames.

🔹 Steps:

Use YOLOv8 (object detection model) to detect the scoreboard region.
Crop the scoreboard and pass it through PaddleOCR for text extraction.
Extract details like:
Team names & scores (e.g., IND: 250/4)
Overs (e.g., 45.3 overs)
Player statistics (e.g., Virat Kohli - 102* off 85)
🔹 Output: Structured scoreboard data in text format.

🟢 Module 3: Data Structuring
📌 Objective: Convert extracted text into a well-structured format for processing.

🔹 Steps:

Use regex and NLP parsing to extract meaningful information.
Store data in CSV format or a structured JSON file.
Ensure correct mapping of players, teams, and stats.
🔹 Output: A clean structured dataset containing match details.

🟢 Module 4: Transcript Generation (Video-to-Text)
📌 Objective: Generate textual descriptions for key frames.

🔹 Steps:

Feature Extraction using VGG16

Use a pretrained VGG16 model to extract feature vectors from frames.
Text Generation using LSTM Encoder-Decoder

Pass extracted features to an LSTM-based sequence model.
Generate textual descriptions like:
"Virat Kohli hits a cover drive for four!"
"Rohit Sharma is caught out at deep midwicket."
🔹 Output: Frame-wise descriptions of key match events.

🟢 Module 5: Line Templating & Summarization
📌 Objective: Structure and summarize extracted information into a match summary.

🔹 Steps:

Apply predefined cricket commentary templates
Example:
arduino
Copy
Edit
"{Player} scored {runs} off {balls}, hitting {boundaries} fours and {sixes} sixes."
"{Bowler} took {wickets} wickets for {runs} runs."
"{Team} won the match by {margin}."
Use BART (Transformer model) for summarization
Apply sequence-to-sequence NLP techniques to generate a concise match report.
🔹 Output: A final match summary like:

"India posted a strong total of 320/5, with Kohli scoring an unbeaten 102 off 85 balls. Bumrah took 3 wickets, restricting Australia to 285/9. India won by 35 runs."

🔵 Final System Flow:
🎥 Input: Cricket match video →
🖼️ Extract key frames →
🔍 Detect scoreboard & extract data →
📊 Structure & store match details →
📝 Generate frame-wise descriptions →
📖 Apply templates & summarization →
📄 Final Output: A well-structured match summary

💡 Key Highlights:
✅ Uses YOLOv8 for object detection and PaddleOCR for text extraction.
✅ Implements CNN-LSTM for video-to-text generation.
✅ Utilizes BART for text summarization.
✅ Provides an automated, structured match summary from raw video footage.


