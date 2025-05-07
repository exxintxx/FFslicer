# FFslicer: Educational Video Segmentation Tool
FFslicer is a Bash script tool designed to automate the process of segmenting educational video content into optimally sized micromodules for enhanced learning experiences. 

## Features
- Automated segmentation of video files based on custom timestamps
- Preservation of original video quality through stream copying
- Support for custom naming of output segments
- Comment capabilities in timestamp files for better organization
- Creation of a dedicated output directory for organized storage
## Requirements
- FFmpeg is installed on your system
- Bash shell environment (macOS, Linux, or Windows with WSL)
## Installation
1. Download the ffslicer.sh script
2. Make it executable:
   ```bash
   chmod +x ffslicer.sh
   ```

3. Update the FFmpeg path in the script to match your system:
   ```bash
   export PATH=$PATH:/path/to/your/ffmpeg
## Usage
 ```bash
./ffslicer.sh [input_video_file] [timestamps_file]
```

## Timestamp File Format
 ```bash
[start_time] [end_time] [optional_clip_name]
```

Example
 ```bash
00:15:30 00:23:45 Introduction_to_topic
01:05:22 01:15:00 Key_concepts
# This is a comment
02:30:00 02:45:30 Practical_examples
```
- Each line contains a start time and end time in HH:MM format
- Optionally, include a clip name after the times
- Lines beginning with # are treated as comments
- Empty lines are ignored

Example
 ```bash
./ffslicer.sh lecture.mp4 timestamps.txt
```

## How It Works

- The script first verifies that the input file and timestamp file exist
- It creates an output directory for the clips
- It processes each line in the timestamp file:
- Extracts start time, end time, and optional clip name
- Uses FFmpeg to copy the segment from the source video
- Saves the segment with appropriate naming
- All segments preserve the original video quality through stream copying

## Advanced Usage
(Automatic Clip Numbering)

 ```bash
# Uncomment these lines for automatic clip numbering
# clip_index=0
# ...
# ((clip_index++))
```
This will automatically number clips that don't have a specified name.

## Troubleshooting
- FFmpeg Not Found: Ensure FFmpeg is installed and the PATH in the script is correctly set
- Timestamp Format Errors: Verify your timestamp file uses the correct HH:MM format
- Permission Denied: Make sure the script has execution permissions
  ```bash
  (chmod +x ffslicer.sh)
  
## License
MIT License

Copyright (c) 2025 D. Khistyeva

See the LICENSE file for details.

## Citation
If you use this tool in your research or educational materials, please cite:


Khistyeva, D. (2025). FFslicer: A Tool for Educational Video Segmentation.
GitHub Repository: https://github.com/exxintxx/FFslicer
