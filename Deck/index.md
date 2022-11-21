# Deck Name

## One flashcard

(front of card) This flashcard will not be tagged, because it is directly underneath the `Deck/` folder.

%

(back of card) One thing that makes `md2apkg-action` really cool is that if you create folders underneath `Deck/` and put `.md` flashcard definitions inside, all your flashcards will automatically get tagged according to the folder hierarchy you define.

For example, say you make a file called `flashcards.md` and tuck it inside folders like so `Deck/tagA/tagB/flashcards.md`, then every flashcard in `flashcards.md` will get automagically tagged with both of the following tags: `tagA`, and `tagA::tagB`. Same goes for other `.md` files you define on that path.
You can define more than one flashcard in a `.md` file in this way. Or you can create your own `.md` files.

## Another flashcard

One nice feature of `md2apkg-action` is that it concatenates every `.md` file you define, meaning that you can split out your flashcards into multiple files to make it easier to manage if you so desire, and the resulting `Deck.apkg` will be the same. 

%

It's up to you to decide what makes the most sense for your needs.

## A third flashcard

There is a lot more flexibility for flashcard definitions than is demonstrated here.

%

See the [`md2apkg`](https://github.com/Steve2955/md2apkg) docs to understand how to write flashcards using `.md`.
