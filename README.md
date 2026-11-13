# BookFinder Telegram Bot

A cloud-hosted Telegram bot that searches **Google Books** and **Open Library** for book titles, authors, and ISBNs. It returns bibliographic matches, Google Books preview/full-view indicators when provided by the API, and links to Open Library and WorldCat.

It does **not** scrape file-sharing sites or promise that a catalogue record is a free downloadable book. Borrowing and full-text access depend on the edition, rights, country, and library.

## Deploy it on Render (no local setup required)

### 1. Create your Telegram bot
1. Open [@BotFather](https://t.me/BotFather) in Telegram.
2. Send `/newbot`.
3. Follow the prompts and copy the bot token. Keep it private.

### 2. Put this project on GitHub
1. Download and unzip this project.
2. Create a new repository on [GitHub](https://github.com/new).
3. Upload all files and folders from this project to the repository.

### 3. Deploy on Render
1. Sign in to [Render](https://render.com/).
2. Choose **New + → Blueprint**.
3. Connect the GitHub repository you just created.
4. Render reads `render.yaml`. Confirm creation of the web service.
5. When prompted, enter the `BOT_TOKEN` from BotFather.
6. `WEBHOOK_SECRET` is generated automatically by the Blueprint.
7. Deploy. Wait until the service is marked **Live**.

The Blueprint uses Render's Starter web-service plan because the bot needs a continuously running HTTPS endpoint for Telegram webhooks. Check Render's current pricing before confirming.

### 4. Start using it
Open your bot's Telegram username and press **Start**. Send a query such as:

- `Human Molecular Genetics Strachan`
- `The Selfish Gene Richard Dawkins`
- `9780198794141`

No computer needs to stay on after deployment.

## Features
- Searches Google Books and Open Library concurrently.
- Accepts title, author, or ISBN queries.
- Displays authors, year, publisher, ISBN, source, and available preview/access indicators.
- Adds direct catalogue, Google Books, and WorldCat links.
- Supports searches in multiple languages to the extent supported by the catalogues.

## Notes
- Public Google Books and Open Library endpoints are used without an API key.
- A match means a catalogue record was found; it does not guarantee a free full-text copy.
- Open Library lending availability and local library access can vary.
- Do not publish your Telegram bot token or webhook secret.
- To change code later, push changes to GitHub; Render can redeploy from the repository.

## Troubleshooting
- **Bot does not respond:** check that the Render service is Live and that `BOT_TOKEN` is correct.
- **Webhook registration error:** verify the Render service has a public HTTPS URL and that `WEBHOOK_SECRET` is set.
- **No results:** try the title plus author, or use the ISBN.
