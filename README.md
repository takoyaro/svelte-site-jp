
# Svelte Site JP

[Svelte](https://github.com/sveltejs/svelte)の公式ページ[svelte.dev](https://svelte.dev/)を日本語に翻訳するプロジェクトです。


## Running locally

Set up the site sub-project:

```bash
git clone https://github.com/tomoam/svelte-site-jp.git
cd svelte-site-jp
npm ci
npm run update
npm run dev
```

and navigate to [localhost:3000](http://localhost:3000).


## REPL GitHub integration

In order for the REPL's GitHub integration to work properly when running locally, you will need to:
- [create a GitHub OAuth app](https://github.com/settings/developers):
   - set `Authorization callback URL` to `http://localhost:3000/auth/callback`;
   - set `Application name` as you like, and `Homepage URL` as `http://localhost:3000/`;
   - create the app and take note of `Client ID` and `Client Secret`
- in this repo, create `site/.env` containing:
   ```
   GITHUB_CLIENT_ID=[your app's Client ID]
   GITHUB_CLIENT_SECRET=[your app's Client Secret]
   BASEURL=http://localhost:3000
   ```

## Building the site

To build the website, run `npm run build`. The output can be found in `__sapper__/build`.

## Testing

Tests can be run using `npm run test`.


## Linking `@sveltejs/site-kit` and `@sveltejs/site-repl`

This site depends on `@sveltejs/site-kit`, a collection of styles, components and icons used in common by *.svelte.dev websites, and `@sveltejs/site-repl`.

In order to work on features that depend on those packages, you need to [link](https://docs.npmjs.com/cli/link) their repositories:

- `cd <somewhere>`
- `git clone https://github.com/sveltejs/site-kit`
- `git clone https://github.com/sveltejs/svelte-repl`
- `cd <somewhere>/site-kit`
- `npm link`
- `cd <somewhere>/svelte-repl`
- `npm link`
- `cd <svelte-repo>/site`
- `npm link @sveltejs/site-kit`
- `npm link @sveltejs/svelte-repl`
 


## Translating the API docs

Anchors are automatically generated using headings in the documentation and by default (for the english language) they are latinised to make sure the URL is always conforming to RFC3986.

If we need to translate the API documentation to a language using unicode chars, we can setup this app to export the correct anchors by setting up `SLUG_PRESERVE_UNICODE` to `true` in `config.js`.
