# CrixWix
Text Summarization of Cricket Match Videos Using Neural Networks

System Architecture:
![image](https://github.com/user-attachments/assets/82ee4fdc-a4e6-4a0e-bb61-f27b3d68ae14)


Workflow:

1.Video Frame Conversion Module
Uses OpenCV to extract frames from the video.
Filters redundant frames to keep only the key moments.
![image](https://github.com/user-attachments/assets/718354d1-2328-4c10-a892-2da78173d772)


2.Scoreboard Detection & Data Extraction Module
Uses YOLOv8 to detect scoreboards.
Extracts text (player names, team scores, stats) using PaddleOCR.
![image](https://github.com/user-attachments/assets/d37b918d-f609-4bb2-8dbc-56b2817e6026)


3.Data Structuring Module
Parses extracted text using Regex.
Structures data into CSV format for processing.
![image](https://github.com/user-attachments/assets/d08b75f3-cf0a-4a56-9fe3-a7184fa1da3e)


4.Transcript Generation Module
Uses VGG16 for feature extraction from frames.
Employs an LSTM-based encoder-decoder for generating textual descriptions.
![image](https://github.com/user-attachments/assets/cd6ef735-acdf-401e-8fda-441afb7c52e4)


5.Line Templating & Summarization Module
Applies predefined templates for cricket commentary.
Uses BART (Transformer) for summarizing match highlights.
![image](https://github.com/user-attachments/assets/27f9ef63-c1b2-480c-b3a4-38309b20ec91)



