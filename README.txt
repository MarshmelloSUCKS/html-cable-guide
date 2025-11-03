           _   _         _            _   _                _   _     
          | |_| |_ _____| |   ___ ___| |_| |___    ___ _ _|_|_| |___ 
          |   |  _|     | |  |  _| .'| . | | -_|  | . | | | | . | -_|
          |_|_|_| |_|_|_|_|  |___|__,|___|_|___|  |_  |___|_|___|___|
                         by msx.gay               |___|              
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
    html-cable-guide - a cable guide made using HTML and CSS. the "classic"
theme replicates 80's EPGs (think *very* early Prevue), and the "modern" theme
is inspired by 2000's cable guides (think TV Guide). this guide is intended for
720x480 NTSC, either through a Raspberry Pi or HDMI to composite/RF adapter.

    while automation of this guide should be possible, as of now, the only way
to get data into the guide is to manually edit the index.html file.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
                        e d i t i n g   t h e   i n d e x
    this section tells you how to edit the index.html, and should serve as a
reference for those who wish to automate this guide. the guide is set with TV
listings for the Sioux City, IA TV market as a demo.

    to start, change the name of your cable system. this is set by the
<p id="SystemName"> element.

    this guide is meant to show 1 hour and 30 minutes of programming, starting
at either the top (:00) or bottom (:30) of the hour. the times at the top of
the page are set in the <tr id="ProgramTimes"> element. change your times, with
each time advancing by 30 minutes.

    channels are set by tables with channel information. to add a new channel,
copy the channel bar below and edit it with your own information.
<table class="channel-bar">
    <tr>
        <td class="label">02<br>Name</td>
        <td class="program-30">30 Minute program</td>
        <td class="program-60">60 Minute program</td>
        <td class="program-90">90 Minute program</td>
    </tr>
</table>
    keep in mind that each channel row should have 90 minutes of programming.
you may add 3 30 minute programs, 1 60 minute program and 1 30 minute program,
or 1 90 minute program. if a program extends into the future or the past beyond
the guide, use the program block that fits into the guide. 

    the label should have the channel on line 1, and the name on line 2.

    if you wish, you may insert a notice using the commented <div class="ad">
element. uncomment this element, and edit the text with your own information.

    finally, edit the footer text with your own information. the November 2nd,
2025 forecast for Sioux City serves as a demo.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
                                    t o - d o
- import guide data from a data.json file
