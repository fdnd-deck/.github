# FDND-Deck

It's where presentations for our talks en workshops live...

## MARP workflow in .github op gh/fdnd-deck

Voorstel voor een workflow voor publiceren van op MARP gebaseerde presentaties via deck.fdnd.nl. Het idee is om op termijn alle college’s lichtgewicht te maken en te publiceren via GitHub.

Op MARP gebaseerde presentaties bestaan voornamelijk uit tekst en `<iframe>` elementen en waar niet anders kan een afbeelding. Hier onder 2 flows voor gh-actions.

### build-deck

1. ACTION: Als er gepushed wordt op de main branch in een repo in de organisatie
2. ACTION: Kopieer alle bestanden uit betreffende branch naar de `/tmp-deck` in .github
3. NPM: Draai het script in `/src`
4. ACTION: Publiceer alle bestanden uit `/build` via gh-pages in de betreffende repo in de organisatie
5. ACTION: trigger update-deck.fdnd.nl

### update-deck.fdnd.nl

1. NPM: Haal uit alle niet gearchiveerde repositories in de organisatie waar gepubliceerde pages zijn de URL en de labels op en genereer de pagina
2. ACTION: Publiceer de bestanden uit `/build` via gh-pages in de betreffende repo in de organisatie
