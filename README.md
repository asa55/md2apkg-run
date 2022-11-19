# docs-as-flashcards

`docs-as-flashcards` contains official documentation, rewritten as flashcards, maintained by yours truly. Docs are dense reads but very important. Rote memorization isn't a replacement for deeper understanding, but it *is* pre-requisite.

## Who is this for?

If you like Anki flashcards, and want to make your own custom decks using Markdown, this repo could be of some use.

## What does this code do?

This repo is a thin wrapper around `md2apkg` (converts `.md` to the format Anki requires, `.apkg`. [Click here](https://github.com/Steve2955/md2apkg) to navigate to that repo, props to the author). There is a limited feature set, but it's a very clean solution for source control purposes imo and I'm not worried about using Anki's full feature set.

The pain point this repo solves is that `md2apkg` requries you to work locally. I generally don't like installing tools on my desktop and wanted GitHub Actions to do the heavy lifting for me, hence the creation of `docs-as-flashcards`. This repo basically lets GitHub Actions do the heavy lifting.

## How do I use it?

To make your own Anki flashcards using markdown without ever downloading anything aside from the `.apkg`, fork this repo and edit the `flashcards.md` file. When you push to the main branch (or PR into the main branch), this will trigger GitHub Actions to create a `.apkg` artifact. By navigating to the Actions tab, clicking the Action you just ran, and scrolling down to the bottom of the page, you'll see the option to download the artifact as a `.zip` file. Pull that into whatever device you use Anki, unzip the `.apkg` file, and import it into Anki via the Anki UI.

## Roadmap

I'm interested in the best ways to either programmatically generate a sensible deck name based on e.g. the GitHub username and repo name, or just lettign users enter it manually, but right now it defaults to the first heading you set in `flashcards.md`.

I'm interested in finding a way to nest `.md` files in e.g. a folder hierarchy, then automatically using that hierarchy to infer / apply tags or subdeck names. This feature is not implemented yet, right now everything is flat under `flashcards.md`, and you have to apply tags manually per the `md2apkg` docs.

This is more generic than `docs-as-flashcards` which was so named due to the intent of what I was trying to do going into this.  I may change the project name slightly because at this point I'm realizing this wrapper could probably be abstracted away from the usage itself. Ideally I'd like for this to be a GitHub Action you can call into whatever repo you've created, instead of a repo you fork. Functionally, your repo at that point would have an Actions workflow file, and the markdown file(s) you want converted to `.apkg`.
