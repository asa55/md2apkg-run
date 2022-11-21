# convert-md-into-anki-flashcards

## Quickstart Guide

1. Create a new repo from template (use the big green button above)
2. Modify `Deck Name` folder name to whatever you want your deck's name to be
3. Inside the `Deck Name` folder, you can create any `.md` files with any name inside folders with any name
  - `.md` files are used to define flashcards as shown in the sample `.md` files provided
  - The filename doesn't matter as long as it ends in `.md`
  - The folder names *do* matter, because the folder names themselves are used to automatically generate tags. Nested folders are used to autogenerate nested tags on flashcards defined by the `.md` files inside them
4. Push your changes (i.e. commit directly to main branch)
5. Click the `Actions` tab
6. Click `Convert flashcards.md to flashcards.apkg` beneath `All workflows`
7. Click `Run workflow`
8. Click `Convert flashcards.md to flashcards.apkg` beneath `workflow runs`
9. Click `artifact` under `Artifacts produced during runtime`
  - This will initiate a download of the `.zip` file containing the `flashcards.apkg` Anki flashcard deck, which you just built from `flashcards.md` in the previous steps
  - You can then import your `flashcards.apkg` directly into Anki using the desktop or mobile app (you'll just need to unzip/extract it after downloading)

## Who is this for?

If you like Anki flashcards, and want to make your own custom decks using Markdown, this repo can help.
I love Anki flashcards, and I wanted to make it easy to maintain my own decks.
This repo helps you create and maintain decks using GitHub as a version control system (which I am completely biased towards and partial to). You can build Ank- compatible flashcard decks in your browser without ever leaving GitHub's website or downloading any tooling.

## How does it work?

This repo is a thin wrapper around [`md2apkg`](https://github.com/Steve2955/md2apkg) (converts `.md` to the format Anki requires, `.apkg`. [Click here](https://github.com/Steve2955/md2apkg) to navigate to that repo, props to the author).

The feature set for creating cards is limited compared to what Anki offers, but it offers all the features I care about.

The pain point this repo solves is that `md2apkg` requries you to work locally as far as I can tell. I generally don't like installing tools on my desktop and wanted GitHub Actions to do the heavy lifting for me, hence the creation of `convert-md-into-anki-flashcards`. This repo basically lets GitHub Actions do the heavy lifting associated with running the conversion CLI tool and also automagically applying tags via some bash scripting.

This repo functions as a template. You'll need to create a copy (or a fork) and work from that. One repo corresponds to one deck, but you can apply custom tags per-card. Keep this in mind as you consider how best to structure / author your flashcards.

## License

MIT License copyright a.s.augenstein 2022

[see `md2apkg`'s license here](https://github.com/Steve2955/md2apkg/blob/main/LICENSE.md)
