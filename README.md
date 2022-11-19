# actions-convert-md-to-anki-flashcards

## Who is this for?

If you like Anki flashcards, and want to make your own custom decks using Markdown, this repo can help. It takes next to no time at all to get up and running. Fork this repo, edit `flashcards.md` to your liking (or not at all if you want to see the demo flashcards I made), go to the Actions tab to trigger the conversion, and download the output as a `.apkg` Anki flashcard deck. You can do all of this from your browser without ever leaving GitHub's website or downloading any tooling. More detailed instructions are below.

## What does this code do?

This repo is a thin wrapper around [`md2apkg`](https://github.com/Steve2955/md2apkg) (converts `.md` to the format Anki requires, `.apkg`. [Click here](https://github.com/Steve2955/md2apkg) to navigate to that repo, props to the author). There is a limited feature set, but it's a very clean solution for source control purposes imo and I'm not worried about using Anki's full feature set.

It's possible there is a better way of accomplishing what I'm doing here to trigger the `md2apkg` using GitHub Actions. If I figure that out, you'll see the changes propagated into this project. The long term vision as far as I can tell will be to wrap `md2apkg` as a reusable action. 

The pain point this repo solves is that `md2apkg` requries you to work locally as far as I can tell. I generally don't like installing tools on my desktop and wanted GitHub Actions to do the heavy lifting for me, hence the creation of `actions-convert-md-into-anki-flashcards`. This repo basically lets GitHub Actions do the heavy lifting.

## How do I use it?

To make your own Anki flashcards using markdown without ever downloading anything aside from the `.apkg`, fork this repo and edit the `flashcards.md` file. Edit the `flashcards.md` file to your liking, and push your changes to your fork on GitHub. The GigHub Actions workflow that will build the `flashcards.apkg` file from your `flashcards.md` file is triggered manually from the Actions tab (you'll see the option to run the Actions workflow). This will trigger GitHub Actions to create a `.apkg` artifact. By navigating to the Actions tab, clicking the Action you just ran, and scrolling down to the bottom of the page, you'll see the option to download the artifact as a `.zip` file. Pull that into whatever device you use Anki, unzip the `.apkg` file, and import it into Anki via the Anki UI.

Optionally, you might want to delete artifacts you don't need anymore (there's a trash can icon next to the `.apkg` artifact). But GitHub will do this for you after a certain amount of time has passed. If you need it again and it's not available, just trigger the GitHub Action again to build a new one.

## Roadmap

I'm interested in finding a way to nest `.md` files in e.g. a folder hierarchy, then automatically using that hierarchy to infer / apply tags or subdeck names. This feature is not implemented yet, right now everything is flat under `flashcards.md`, and you have to apply tags manually per the `md2apkg` docs.

This is more generic than `actions-convert-md-into-anki-flashcards` which was so named due to the intent of what I was trying to do going into this.  I may change the project name slightly because at this point I'm realizing this wrapper could probably be abstracted away from the usage itself. Ideally I'd like for this to be a GitHub Action you can call into whatever repo you've created, instead of a repo you fork. Functionally, your repo at that point would have an Actions workflow file, and the markdown file(s) you want converted to `.apkg`.
