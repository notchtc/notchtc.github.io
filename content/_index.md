+++
title = "Home"
description = "This is my site where I write something."
date = 2021-12-21T08:21:31+01:00
tags = ["chtc","notchtc","cha0t1c","bawialnia","sexiarz","poland"]
+++

I am chtc and I'm a dumbass from Poland.

I like to listen to "normal" stuff and stuff that makes your ears bleed.

I rarely play games and for some reason I want to CBT be done on me by the games.

Go to other pages for more interesting stuff.

<div style="overflow: auto;">
<span id="cover" style="float: left; margin-right: 1rem;"></span>
<div style="float: left;">
<p id="nowplaying">Connecting to last.fm</p>
<p id="artist"></p>
<p id="song"></p>
</div>
</div>

## World Wide Web
- [Email](mailto:notnotcha0t1c@protonmail.com)
- [GitHub](https://github.com/notchtc)
- [YouTube](https://www.youtube.com/channel/UC-5mLU2LQZQAjWQTCloslBw)
- [Twitter](https://twitter.com/notchtc)
- [Discord](https://discord.com/users/703166258748588073)
- [Telegram](https://t.me/seksiarz)
- [Bandcamp](https://ligmamalegrindset.bandcamp.com)
- [Last.fm](https://last.fm/user/chujtas)
- [AniList](https://anilist.co/user/chtc)
- [Kalkulator Stanisław Jelnicki](https://jelnislaw.ml/kalkulator)
- [PGP Key](/chtc.asc) (AB80 87BF 8782 B459 ECF8  A1E4 D65C E53E 8710 1757)

[<--](https://hotlinewebring.club/chtc/previous) [Webring's site](https://hotlinewebring.club) [-->](https://hotlinewebring.club/chtc/next)

<script type="text/javascript">
    async function get_lastfm() {
        const requestURL = 'https://ws.audioscrobbler.com/2.0/?method=user.getrecenttracks&limit=1&user=chujtas&api_key=c51be531f29d46cd52c65c82aa9eca31&format=json';
        const request = new Request(requestURL);

        const response = await fetch(request);
        const info = await response.json();
        const track = info.recenttracks.track[0];

        var text = '';
        if (Object.values(info).includes('nowplaying')) {
            text = 'Now playing';
        } else {
            text = 'Last played (' + track.date['#text'] + ')';
        }
        document.querySelector('#cover').innerHTML = '<img width="174" src="' + track.image[2]['#text'] + '">';
        document.querySelector('#nowplaying').innerHTML = text;
        document.querySelector('#artist').innerHTML = track.artist['#text'];
        document.querySelector('#song').innerHTML = '<a href=' + track.url + '" target="_blank">' + track.name + '</a>';
    }

    get_lastfm();
</script>
