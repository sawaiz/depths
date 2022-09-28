# Depths
A voyage of musical discovery,

[logo image]

In a weekly episode over four months, ten seekers will recommend unappreciated songs given a theme. A master playlist for each week will be created highlighting those pieces.

New depths of sound demand to be discovered, with the seekers being selected from diverse backgrounds and musical tastes. Music can be private; it's easy to share yet rarely is. The seekers are veiled, the listeners learn about them only through their selections.

## Guidelines
- The Voyage lasts four months, and the ten seekers will participate for sixteen weeks.
- The songs must be less than 12m long, pieces under 6 minutes are preferred to keep the playlist around an hour.
- Seekers will be contacted each week through email with the theme, and will have six days to submit.
- The list of previous episodes is provided, please don't submit duplicates.
- Album versions are preferred, but if no good version is available, a live recording will be accepted.
- The “theme” is open to interpretation, it's there to reduce overchoice, make your choices your own, it yields more diverse pieces. There are no boundaries in language, genre, or content.
- The playlist will be voted on and then the order will be curated to provide the best listening experience.
- A public voting system will be created with FPTP voting for their favorite song. The ranking will determine the final playlist order. The vote will take place over the following week. The goal isn't to score highest, the ranking is just there to make it more accessible. There is no final score.

## Proposal

Would you all be interested in a very low effort "book club for music" (working on a name too)? I'm finishing up the rules and format, but it will be 10 people in a 4 month season where each week you will submit a song you think is underrated (you will be given a "theme" to jog your memory and make picking easier). 

Then a playlist that is under one hour will be made and possibly voted on by you/general public for the final ranking in the playlist.

I’m trying to get as broad of a set of people to have the best selection of music


## Voyages

## Software
The webiste is hosted through github pages and consists of a very basic html5+css+vanillaJS. All custom coded. The database is a static JSON file also hosted though the same server. It is optmizied for very fast loading even on slow networks. Ther are no images or fancyy JS (except building tables from the JSON). There are no external libraries inlcuded, and where external fonts are loaded, a similar placeholder is used and swaped so font loading does not delay page rending or cause a significant jump in formatting on the swap.

## Tools

This mashup of sed scripts was put together on a flight using only memory and man pages to help convert the HTML page to JSON for the upgrade. Hopefully wont ever be needed again.

```bash
cat index.html | head -n 532 | tail -n 10 | sed -E 's/^ +<tr><td>/\{"name": "/g' | sed -E 's/<\/td><td>/", "song": "/' | sed -E 's/<\/td><td>/", "artist": "/' | sed -E 's/<\/td><td>/", "album": "/' | sed -E 's/<\/td><td>/", "year": /' | sed -E 's/<\/td><td><a href=/, "link": /' | sed -E 's/>Link.+$/\},/' | pbcopy
```
An example of capturing 4 numbers and keeping them witth a capture group
```bash
s/({4}\d)/$1/g
```

## Cards
Built with latex fora 55x55mm

Build
```bash
latexmk -halt-on-error -xelatex
```

## Logo
The logo is a hand drawn svg with various colors. It is used as the favicon, as well as for 
