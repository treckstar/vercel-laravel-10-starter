# Laravel Vercel

This repository inherits from Laravel 10.x. Important files are the following ones:

- [`.vercelignore`](./.vercelignore)
- [`.vercel.json`](./vercel.json)

## Build assets

Add the following snippet in the `composer.json` file.

```json
{
    "scripts": {
        "vercel": [
            "npm install",
            "npm run build"
        ]
    }
}
```

## Enable HTTPS

See [`app/Http/Middleware/TrustProxies.php`](./app/Http/Middleware/TrustProxies.php).

```diff
-   protected $proxies = null;
+   protected $proxies = "*";   
```
## Common

You still need to setup the basics, such as making an `.env` file, setting an `APP_KEY`, etc.

Do not save your `APP_KEY` in the `.vercel.json` file. You must set this in the settings.

### Create `.env` file

```
cp .env.example .env
```

### Create `dist` folder

If you do not want to change the build output folder settings, run this:

```
mkdir dist
echo "# for vercel output" >> dist/.gitkeep
```

There is a chance that your local `.dotfiles` have the `dist` folder in a `.gitignore` file, so force add it:

```
git add dist -f
git commit -m "chore: dist folder for vercel output"
git push
```
