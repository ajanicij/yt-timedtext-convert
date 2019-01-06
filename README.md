# yt-timedtext-convert
Web application that converts YouTube timedtext.xml to .srt file

This project contains JavaScript code that converts YouTube timedtext.xml
to .srt file.

First, what is timedtext.xml? That is a file that contains subtitles of a YouTube
video. It is an XML file that looks like this:

    <?xml version="1.0" encoding="UTF-8"?>
    <timedtext format="3">
    <head>
    <pen id="1" fc="#E5E5E5"/>
    <pen id="2" fc="#CCCCCC"/>
    <ws id="0"/>
    <ws id="1" mh="2" ju="0" sd="3"/>
    <wp id="0"/>
    <wp id="1" ap="6" ah="20" av="100" rc="2" cc="40"/>
    </head>
    <body>
    <w t="0" id="1" wp="1" ws="1"/>
    <p t="6319" d="3721" w="1"><s p="2" ac="184">non</s><s t="1000" ac="243"> mais</s><s t="1181" ac="246"> je</s><s t="1301" ac="222"> n'ai</s><s t="1451" ac="252"> pas</s><s p="1" t="1600" ac="216"> là</s></p>
    <p t="14629" w="1" a="1">
    </p>
    <p t="14639" d="3370" w="1"><s p="1" ac="218">je</s><s t="1000" ac="241"> suis</s><s t="1271" ac="252"> pas</s><s t="1361" ac="246"> agressif</s><s p="2" t="1511" ac="161"> celle</s><s t="1810" ac="236"> qui</s><s p="1" t="1931" ac="207"> m'agresse</s></p>
    <p t="16769" d="1240" w="1" a="1">
    </p>

    ...

    <p t="679130" d="4620" w="1"><s ac="239">merci</s><s t="1000" ac="252"> à</s><s t="1030" ac="252"> vous</s><s t="1180" ac="242"> merci</s><s t="1960" ac="239"> merci</s></p>
    </body>
    </timedtext>

When we download the YouTube video, say as an MP4 file, it doesn't contain subtitles. If
we play it with VLC, we can add subtitles; but VLC expects subtitles in .srt format. For
the XML file above, a matching .srt file would look like this:

    1
    00:00:06,319 --> 00:00:15,629
    non mais je n'ai pas là

    2
    00:00:15,639 --> 00:00:17,769
    je suis pas agressif celle qui m'agresse

    ...

    309
    00:11:14,010 --> 00:11:19,120
    dans ma vie je suis plus instinctive

So, this project contains code (in JavaScript) that converts timedtext.xml to a .srt
file. But, it has a twist. I wanted to make it as easy for you to use as possible.
You don't have to install anything, just open your browser and open the GitHub Pages
page of this project:

https://ajanicij.github.io/yt-timedtext-convert/

In that page, browse for the timedtext.xml file that you want to convert, click on
button CONVERT, and when the conversion is done, click on the link beneath the button
and save the converted file.

Oh yes, I also wanted to make it as easy for me as possible, so I am not running any
server for this - it's all in that one static page.

Just in case, here's how I am getting timedtext from YouTube videos: open the page

https://www.addictivetips.com/web/3-ways-to-download-subtitles-from-a-youtube-video/

and look at the section "Your Browser". Briefly, in Firefox or Chrome open the
developer tools, click on the Network tab, then enable closed caption in the video
and open the downloaded file in a new tab. Then you can save it to a file.
