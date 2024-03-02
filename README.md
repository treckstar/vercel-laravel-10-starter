# Vercel Laravel 10 Starter (PHP 8.3)

## Credit

<p align=center><strong>🏋️‍♀️ It works with these frameworks and tools. Discover more at <a href="https://github.com/juicyfx/vercel-examples">examples</a>.</strong></p>
<p align=center>
Made with  ❤️  by <a href="https://github.com/f3l1x">@f3l1x</a> (<a href="https://f3l1x.io">f3l1x.io</a>) • 🐦 <a href="https://twitter.com/xf3l1x">@xf3l1x</a>
</p>

Majority of updates taken from pull request by [@cmizzi](https://github.com/cmizzi/vercel-examples)

## Important Files

This repository inherits from Laravel 10.x. Important files are the following ones:

- [`.vercelignore`](./.vercelignore)
- [`.vercel.json`](./vercel.json)

## 💯 Versions

Change the version of `vercel-php` dependency in `.vercel.json` for the version you want to use.

- `vercel-php@0.7.0` - Node 18.x / PHP 8.3.x (https://vercel-laravel-10-starter.sites.treckstar.net)
- `vercel-php@0.6.1` - Node 18.x / PHP 8.2.x (https://example-php-8-2.vercel.app)
- `vercel-php@0.5.4` - Node 18.x / PHP 8.1.x (https://example-php-8-1.vercel.app)
- `vercel-php@0.4.3` - Node 18.x / PHP 8.0.x (https://example-php-8-0.vercel.app)
- `vercel-php@0.3.5` - Node 18.x / PHP 7.4.x (https://example-php-7-4.vercel.app)

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
