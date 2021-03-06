# ๐ง Mbtify
Spotify Track์ ํ์ฉํ MBTI ๋ถ๋ฅ ์๋น์ค

<img src="https://user-images.githubusercontent.com/55238671/145755750-c8454f29-a6cd-4ca6-8711-225c83e36277.png" width="500">

## About Mbtify
> Find MBTI using track

Spotify ์์ ํ๋ซํผ์์ ์ ๊ณตํ๋ MBTI ๋ณ ํ๋ ์ด๋ฆฌ์คํธ์ ๊ณก๋ค์ ์ถ์ถํ์ฌ ๋น์ทํ ์ฑํฅ์ ๊ฐ์ง ์์์  ํน์ง์ ํ์ฉํ์ฌ ์ฌ์ฉ์๊ฐ ์ข์ํ๋ ์์์ MBTI๋ฅผ ์ฑํฅ์ ์์ธกํ  ์ ์๋ ์๋น์ค์ด๋ค.

## Data Pipeline
<img src="https://user-images.githubusercontent.com/55238671/145755773-34f3ebdb-45bf-435a-830c-7f255d043e2f.png" width="500">

1. [์คํฌํฐํ์ด ๊ฐ๋ฐ์ ํํ์ด์ง](https://developer.spotify.com/) ์์ ์ ์ ๋ค์ด ๋ง๋ค์ด๋ธ ํ๋ ์ด๋ฆฌ์คํธ์ ํธ๋๋ฐ์ดํฐ๋ฅผ ์์งํฉ๋๋ค.
2. ์์งํ ๋ฐ์ดํฐ๋ค์ `MongoDB`์ ์ ์ฌ๋ฅผ ํ๊ฒ ๋ฉ๋๋ค.
3. ์๊ฐํ๋ฅผ ์ํด ์ ์ฌํ ๋ฐ์ดํฐ๋ฅผ LocalDB๋ก ์ฎ๊ธฐ๊ฒ ๋ฉ๋๋ค.
4. ์ดํ `Docker`๋ฅผ ์ด์ฉํด `Metabase`์์ ๋ฐ์ดํฐ๋ฅผ ์๊ฐํํฉ๋๋ค.
5. `Scikit-Learn`์ ํตํด XGBoost๋ก ๋ชจ๋ธ๋ง์ ์งํํฉ๋๋ค.
6. ๋ง์ง๋ง์ผ๋ก `Flask`๋ก Web ์๋น์ค๋ฅผ ๊ตฌ์ถํ๊ณ  `Heroku`๋ก ๋ฐฐํฌ ํ์์ต๋๋ค.

> ์์ธํ [Keynote ๋ด์ฉ](https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/blob/main/keynote/Keynote.zip)๊ณผ [๋ฐํ ์์](https://www.youtube.com/watch?v=gowY7fZMITE&feature=youtu.be)์ ๋งํฌ๋ฅผ ํตํด ํ์ธํ์ค ์ ์์ต๋๋ค.

## Process
|์๋ฒ|๊ณผ์ |๋๋ ํ ๋ฆฌ|ํด|
|---|---|---|---|
|1|Spotify API๋ฅผ ์ด์ฉํ ๋ฐ์ดํฐ ์คํฌ๋ ์ดํ|[Scraping](https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/tree/main/collect/scraping)|Spotify API|
|2|ํธ๋ ๋ฐ์ดํฐ ์ ์ฌ๋ฐ ๊ด๋ฆฌ|[Collecting](https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/tree/main/collect)|MongoDB, SQLite|
|3|๋จธ์ ๋ฌ๋ ๋ชจ๋ธ๋ง|[Modeling](https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/blob/main/mbtify/modeling.py)|Scikit-Learn|
|4|๋ฐ์ดํฐ ๋ถ์ ๋ฐ ์๊ฐํ |[Visualization](https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/blob/main/keynote/Proj3_keynote/Proj3_keynote.009.png)|Docker, Metabase|
|5|์น ์๋น์ค ๊ตฌํ|[Web Service](https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/tree/main/mbtify)|Flask, Heroku|

## Data Schema, flow
<img src="https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/blob/main/keynote/Proj3_keynote/Proj3_keynote.011.png?raw=true" width="300"> <img src="https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/blob/main/keynote/Proj3_keynote/Proj3_keynote.012.png?raw=true" width="300">


## Feed Back
 **๋ฐ์ดํฐ ์์ง๋ถํฐ ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ ์ฌ, ๋จธ์ ๋ฌ๋ ํ์ฉ, ์น์๋น์ค ๊ฐ๋ฐ ๋ฐ ๋ฐฐํฌ ๊ณผ์  ๋ฑ ๋ฐ์ดํฐ ๋ถ์ผ ์ ๊ณผ์ ์ ํ๋ฆ์ ๊ฐ๋ตํ๊ฒ ์งํํ๋ ํ๋ก์ ํธ** ์๋ค.

## [โถ๏ธ ๊ฒฐ๊ณผ ์ฌ์ดํธ Mbtify](https://mbtify.herokuapp.com/)

<img src="https://github.com/dustin-kang/Proj3_MusicMBTIClassfication/blob/main/keynote/site_gif.gif?raw=true">
