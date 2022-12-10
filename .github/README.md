# md2apkg-run

- This code works as described below, despite the terse file structure you see in this repo. The magic happens within the GitHub Action definition. 
- MIT License applies to all files in this repository
- [See also `md2apkg`'s license](https://github.com/Steve2955/md2apkg/blob/main/LICENSE.md)

Consider giving this repo a ⭐ if you like what you see and want to let me know you're interested in seeing more from this project

## Quickstart Guide

1. Create a new repo from template (use the big green button above)
2. Edit the Markdown file `Deck/index.md` to include your desired deck name
  - See [`md2apkg` docs](https://github.com/Steve2955/md2apkg) to understand how to write flashcards in Markdown using `md2apkg`
  - See [md2apkg-run-demo](https://github.com/asa55/md2apkg-run-demo) to see `md2apkg-run` in action, and for more detail on how to construct decks using `md2apkg-run`
3. Push your changes (i.e. commit directly to main branch)
4. Click the `Actions` tab
5. Click `Run md2apkg converter` beneath `All workflows`
6. Click `Run workflow`
7. Click `Run md2apkg converter` beneath `workflow runs`
8. Click `flashcards` under `Artifacts produced during runtime`
  - This will initiate a download of the `.zip` file containing the `Deck.apkg` Anki flashcard deck, which you just built from you `.md` files in the previous steps
  - You can then import your `Deck.apkg` directly into Anki using the desktop or mobile app (you'll just need to unzip/extract it after downloading)

## Who is this for?

If you like Anki flashcards, and want to make your own custom decks using Markdown, [`md2apkg`](https://github.com/Steve2955/md2apkg) can help (`md2apkg-run` is built on but unaffiliated with [`md2apkg`](https://github.com/Steve2955/md2apkg)).
I didn't want to download or run `md2apkg` on my computer. GitHub Actions could easily simplify this last step.
This is where `md2apkg-run` comes in. It is a thin wrapper around `md2apkg` that lets you write your flashcards and export them as Anki-compatible flashcard decks (`.apkg` files), all without ever leaving the GitHub web interface.

`md2apkg-run` is also used heavily by me personally for every repository supporting the [`*-docs-as-flashcards` project](https://asa55.github.io/docs-as-flashcards/). (This was the primary driver that prompted me to write `md2apkg-run` in the first place).

## What does it do?

1. You (the user) manually create subfolders underneath `Deck/` with `.md` files inside. (Note: No spaces in your subfolder names)
2. Your `.md` files are converted into Anki flashcards
3. Your flashcards are automatically tagged according to the subfolder names where the source `.md` files are located
4. All of your flashcards are packaged into a single `Deck.apkg` file, which is the filetype needed for you to import your flashcards into Anki

## Future

- Auto-tagging is currently the only way to apply tags (make subdirectories under `Deck/` and tagging is done for you)
  - `md2apkg` defines an approach to add your own custom tags. Doing so in flashcards defined in `md2apkg-run` will technically apply all the tags from the automation and the ones you define, but also some additional tags, e.g. a tag that looks like `<!--`.
- Automatically building out subdecks is desirable, but not a feature of `md2apkg-run` at this time. It's not required since tagging works well, but subdecks are a nice-to-have imo
  - I first looked for tools that can arrange aptly named `.apkg` decks into a single deck with subdecks. Genanki was the most interesting tool I came across but the docs are unclear if I can use the subdecking feature I want the way I hope to. Topic of future experimentation
  - I then looked at using sqlite to merge database tables that exist inside of the `.apkg` files, but importing the result into Anki was unsuccessful. Though I'm convinced the theory was sound, it's a fragile approach
  - Consider dropping me a line if anyone reading this is aware of any open-source subdecking tools
  
## Important Note
  
I'm using this repository as a template for flashcards I'm making. This code works. If you're reading this some time in the future and wondering if this code is too stale to use, look for an `Archive` tag on the repository. If it's not archived, it still functions. Whether or not I'm actively contributing to this repo, I'll keep a pulse on this over time.
