<p align="center">
    <img src="https://github.com/Zamiell/hanabi-live/raw/master/public/img/logos/2.png" height=200 alt="Hanabi Live Logo" title="Hanabi Live Logo" />
</p>
<br />

## Description

* This is the source code for [Hanabi Live](http://hanabi.live/), which is a website that allows people to play the card game [Hanabi](https://boardgamegeek.com/boardgame/98778/hanabi) online.
* The client is programmed in [TypeScript](https://www.typescriptlang.org/). It is located in the `public/js` directory.
  * A lot of the code was originally taken from [Keldon's Hanabi webpage](http://keldon.net/hanabi/). (The site no longer works.)
* The server is programmed in [Go](https://golang.org/). It is located in the `src` subdirectory.
  * It uses a [MariaDB](https://mariadb.org/) database to store information about the users and games.

<br />

## Discord

Find teammates to play games with at [the Hanabi Discord server](https://discord.gg/FADvkJp). We also discuss code changes here.

<br />

## List of Variants

Hanabi Live implements [many special variants](https://github.com/Zamiell/hanabi-live/tree/master/docs/VARIANTS.md), in which the rules are changed to make the game more difficult.

<br />

## List of Features

See the [features documentation](https://github.com/Zamiell/hanabi-live/tree/master/docs/FEATURES.md).

<br />

## Installation

See the [installation documentation](https://github.com/Zamiell/hanabi-live/tree/master/docs/INSTALL.md).

<br />

## Credits

* [Keldon Jones](http://keldon.net/) was the original creator of the client-side user interface.
* [Hyphen-ated](https://github.com/Hyphen-ated/) created [Make Hanabi Great Again](https://github.com/Hyphen-ated/MakeHanabiGreatAgain), a useful Chrome extension that extended the features of Keldon's site. The features from the extension are integrated into Hanabi Live.
