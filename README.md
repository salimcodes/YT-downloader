# YT-downloader

Code to download YouTube video in .mp3 format with Python

For Unix/macOS
```
python3 -m venv env
```

For Windows
```
python -m venv env
```
For Unix/macOS

```
source env/bin/activate
```

For Windows
```
.\env\Scripts\activate
```

```
flask
requests
pytube
```

```
pip install -r requirements.txt
```

```
from pytube import YouTube
import os
#url input from user
yt = YouTube(str(input("Enter the URL of the video you want to download: \n>> ")))
#extract only audio
video = yt.streams.filter(only_audio = True).first()
```

```
#check for destination to save file
print("Enter the destination (leave blank for current directory)")
destination = str(input(">> ")) or '.'
```

```
#download the file
out_file = video.download(output_path = destination)

#save the file
base, ext = os.path.splitext(out_file)
new_file = base + '.mp3'
os.rename(out_file, new_file)

#result of success
print(yt.title + " has been successfully downloaded in .mp3 format.")
```


