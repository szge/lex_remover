## Lex Remover
#### (generate a podcast with the highest listening efficiency)

- create or find a tool to mark the timestamps where Lex Fridman is speaking, in order to isolate his voice
- train a model to identify his voice and automatically timestamp the parts of the video where he's speaking for an extended length of time
  - generates a JSON file with start and end timestamps of Lex talking;
  - accuracy measurement based on labeled video ground truth
- download the YouTube video using a script, given a URL
- edit the video to focus on the parts where the guest is speaking

### How to use this

#### Prerequisites
1. Install yt-dlp (`pip install yt-dlp`)
2. Download the video(s) to the videos_raw directory in the base project directory
```bash
yt-dlp -f "bestvideo[height<=480][vcodec^=avc1]+bestaudio[acodec^=mp4a]/best[height<=480]" --merge-output-format mp4 -o "%(title)s.%(ext)s" "https://www.youtube.com/watch?v=tNZnLkRBYA8"
```

#### Labeling the data

#### Training the model