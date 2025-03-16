# CrixWix
Text Summarization of Cricket Match Videos Using Neural Networks

Workflow:

1.Video Frame Conversion Module
Uses OpenCV to extract frames from the video.
Filters redundant frames to keep only the key moments.

2.Scoreboard Detection & Data Extraction Module
Uses YOLOv8 to detect scoreboards.
Extracts text (player names, team scores, stats) using PaddleOCR.

3.Data Structuring Module
Parses extracted text using Regex.
Structures data into CSV format for processing.

4.Transcript Generation Module
Uses VGG16 for feature extraction from frames.
Employs an LSTM-based encoder-decoder for generating textual descriptions.

5.Line Templating & Summarization Module
Applies predefined templates for cricket commentary.
Uses BART (Transformer) for summarizing match highlights.


