# yt-dlp-example
How to use a devContainer backup your stream from YouTube to your local disk using [yt-dlp](https://github.com/yt-dlp/yt-dlp).

# Steps
1. Locate the video's URL from YouTube.  Example: [NASA EVA #80 Spacewalk (https://www.youtube.com/watch?v=82rbJlLUPCs)](https://www.youtube.com/watch?v=82rbJlLUPCs)
1. View the available streams and framerates
    ````bash
    yt-dlp --list-formats https://www.youtube.com/watch?v=82rbJlLUPCs
    ````
    Output:
    ````bash
    [youtube] 82rbJlLUPCs: Downloading webpage
    [youtube] 82rbJlLUPCs: Downloading android player API JSON
    [youtube] 82rbJlLUPCs: Downloading player 68423b67
    [info] Available formats for 82rbJlLUPCs:
    ID  EXT   RESOLUTION FPS │   FILESIZE   TBR PROTO │ VCODEC        VBR ACODEC      ABR     ASR MORE INFO
    ────────────────────────────────────────────────────────────────────────────────────────────────────────────────
    sb2 mhtml 48x27          │                  mhtml │ images                                    storyboard
    sb1 mhtml 80x45          │                  mhtml │ images                                    storyboard
    sb0 mhtml 160x90         │                  mhtml │ images                                    storyboard
    139 m4a   audio only     │  180.06MiB   48k https │ audio only        mp4a.40.5   48k 22050Hz low, m4a_dash
    249 webm  audio only     │  154.55MiB   41k https │ audio only        opus        41k 48000Hz low, webm_dash
    250 webm  audio only     │  228.62MiB   61k https │ audio only        opus        61k 48000Hz low, webm_dash
    140 m4a   audio only     │  477.89MiB  129k https │ audio only        mp4a.40.2  129k 44100Hz medium, m4a_dash
    251 webm  audio only     │  464.72MiB  125k https │ audio only        opus       125k 48000Hz medium, webm_dash
    17  3gp   176x144      8 │  264.47MiB   71k https │ mp4v.20.3     71k mp4a.40.2    0k 22050Hz 144p
    160 mp4   256x144     30 │  282.55MiB   76k https │ avc1.4d400c   76k video only              144p, mp4_dash
    278 webm  256x144     30 │  282.41MiB   76k https │ vp9           76k video only              144p, webm_dash
    133 mp4   426x240     30 │  628.40MiB  170k https │ avc1.4d4015  170k video only              240p, mp4_dash
    242 webm  426x240     30 │  504.21MiB  136k https │ vp9          136k video only              240p, webm_dash
    134 mp4   640x360     30 │    1.25GiB  347k https │ avc1.4d401e  347k video only              360p, mp4_dash
    18  mp4   640x360     30 │    1.60GiB  444k https │ avc1.42001E  444k mp4a.40.2    0k 44100Hz 360p
    243 webm  640x360     30 │  846.38MiB  229k https │ vp9          229k video only              360p, webm_dash
    135 mp4   854x480     30 │    2.32GiB  643k https │ avc1.4d401f  643k video only              480p, mp4_dash
    244 webm  854x480     30 │    1.32GiB  364k https │ vp9          364k video only              480p, webm_dash
    136 mp4   1280x720    30 │    4.45GiB 1233k https │ avc1.64001f 1233k video only              720p, mp4_dash
    22  mp4   1280x720    30 │ ~  5.03GiB 1361k https │ avc1.64001F 1361k mp4a.40.2    0k 44100Hz 720p
    247 webm  1280x720    30 │    2.34GiB  649k https │ vp9          649k video only              720p, webm_dash
    298 mp4   1280x720    60 │    5.87GiB 1628k https │ avc1.640020 1628k video only              720p60, mp4_dash
    302 webm  1280x720    60 │    3.27GiB  907k https │ vp9          907k video only              720p60, webm_dash
    299 mp4   1920x1080   60 │   10.70GiB 2969k https │ avc1.64002a 2969k video only              1080p60, mp4_dash
    303 webm  1920x1080   60 │    4.51GiB 1251k https │ vp9         1251k video only              1080p60, webm_dash
    ````
1. Choose your preferred video and format.  We'll pick #299 since we just want to see the video
````bash
yt-dlp --format 299 https://www.youtube.com/watch?v=82rbJlLUPCs --concurrent-fragments 5
````
1. Wait for video to finish downloading


# yt-dlp
yt-dlp is a [youtube-dl](https://github.com/ytdl-org/youtube-dl) fork based on the now inactive [youtube-dlc](https://github.com/blackjack4494/yt-dlc). The main focus of this project is adding new features and patches while also keeping up to date with the original project.