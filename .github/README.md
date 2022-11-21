# md2apkg-run

- This code works as described below, despite the terse file structure you see in this repo. The magic happens within the GitHub Action definition. 
- MIT License applies to all files in this repository
- [See also `md2apkg`'s license](https://github.com/Steve2955/md2apkg/blob/main/LICENSE.md)

## Quickstart Guide

1. Create a new repo from template (use the big green button above)
2. Edit the Markdown file `Deck/index.md` to include your desired deck name
  - Any flashcards defined within `index.md` (or in `.md` files adjacent to `index.md`) will not be tagged
  - If you create any folders underneath `Deck/` with `.md` files inside, flashcards defined in these will have tags automatically applied based on the folder names you specify
  - If you want to include images, place them anywhere in the folder hierarchy (even your own custom folders) and relative link to them using the `.md` syntax for images
3. Push your changes (i.e. commit directly to main branch)
4. Click the `Actions` tab
5. Click `Run md2apkg converter` beneath `All workflows`
6. Click `Run workflow`
7. Click `Run md2apkg converter` beneath `workflow runs`
8. Click `flashcards` under `Artifacts produced during runtime`
  - This will initiate a download of the `.zip` file containing the `flashcards.apkg` Anki flashcard deck, which you just built from `flashcards.md` in the previous steps
  - You can then import your `flashcards.apkg` directly into Anki using the desktop or mobile app (you'll just need to unzip/extract it after downloading)

## Who is this for?

If you like Anki flashcards, and want to make your own custom decks using Markdown, [`md2apkg`](https://github.com/Steve2955/md2apkg) can help (`md2apkg-run` is built on but unaffiliated with [`md2apkg`](https://github.com/Steve2955/md2apkg)).
I didn't want to download or run `md2apkg` on my computer. GitHub Actions could easily simplify this last step.
This is where `md2apkg-run` comes in. It is a thin wrapper around `md2apkg` that lets you write your flashcards and export them as Anki-compatible flashcard decks (`.apkg` files), all without ever leaving the GitHub web interface.
