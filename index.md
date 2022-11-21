# Deck Name

## First flashcard

(front of card) This flashcard will not be tagged, because it is in `index.md`

%

(back of card) The only firm requirement is that line 1 of this file has a single `#` followed by a space followed by the Deck Name of your choosing.

## Second flashcard

You can define more than one flashcard in a `.md` file in this way. Or you can create your own `.md` files.

%

One nice feature of `md2apkg-action` is that it basically just concatenates every `.md` file you define in this repository together (except for `README.md`), so whether you define flashcards in one or many `.md` files has the same effect when the deck is being built.

## Third flashcard

The real question is for you to decide what makes the most sense for your needs.

%

See the [`md2apkg`](https://github.com/Steve2955/md2apkg) docs to understand how to write flashcards using `.md`.

## Fourth flashcard

One last thing that makes `md2apkg-action` really cool: if you create folders and put `.md` flashcard definitions inside, all your flashcards will automatically get tagged according to the folder hierarchy you define.


%

For example, say you make a file called `flashcards.md` and tuck it inside folders like so `/tagA/tagB/flashcards.md`, then every flashcard in `flashcards.md` will get automagically tagged with both of the following tags: `tagA`, and `tagA::tagB`. Same goes for other `.md` files you define on that path.

This helps a lot for organizing your study sessions in Anki, if you feel so inclined.

Note that the folder names are special, but file names are ignored with regards to this project building your deck.
