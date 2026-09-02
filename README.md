# Papertrail

Open `index.html` in a browser to run the research discovery app.

## Publish it for friends

The project is already prepared as a static public website. The fastest options are:

1. Create a GitHub repository and upload the contents of this folder.
2. In GitHub, open **Settings â†’ Pages**, choose **Deploy from a branch**, select `main` and `/root`, then save.
3. GitHub will give you a public `https://...github.io/...` link to share.

Alternatively, drag this folder into [Netlify Drop](https://app.netlify.com/drop) for an instant public preview URL, or import the repository into [Vercel](https://vercel.com/new).

No server is required for the current version. The site calls OpenAlex directly from the browser and falls back to the included demo papers if the live service is unavailable.

Features:

- Search papers by topic, year range, and adjustable result count.
- Live OpenAlex lookup with curated fallback results when the live source is unavailable.
- Automatic in-browser summary from each paper abstract.
- Direct paper links and saved reading list stored in the browser.
- Custom author, keyword, and open-access filters.
- Built-in research copilot for comparisons, practical picks, research gaps, and free-form prompts.

The current version is a client-side prototype. For production use, connect the copilot action to an LLM API through a small server-side proxy so keys are not exposed in the browser.

