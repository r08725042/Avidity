#### You can use the following function to get mp3.
reference : https://dev.to/stokry/download-youtube-video-to-mp3-with-python-26p

```python
import youtube_dl
import time
def run(video_url, folder_name):
#     video_url = input("please enter youtube video url:")
    video_info = youtube_dl.YoutubeDL().extract_info(
        url = video_url,download=False
    )
    filename = video_info['title'].replace('/', '_')
    
    filename = 'ytmp3/' + folder_name + '/' + filename + '.mp3'

    options={
        'format':'bestaudio/best',
        'keepvideo':False,
        'outtmpl':filename,
    }

    with youtube_dl.YoutubeDL(options) as ydl:
        ydl.download([video_info['webpage_url']])

    print("Download complete... {}".format(filename))
 ```
