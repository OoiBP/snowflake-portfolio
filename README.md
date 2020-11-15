# MyProfile (my_profile)

A demo project of my profile page

## Install the dependencies

```bash
npm install
```

### Start the app in development mode (hot-code reloading, error reporting, etc.)

```bash
quasar dev
```

### Lint the files

```bash
npm run lint
```

### Build the app for production

```bash
quasar build
```

### Deploy to GitHub pages

If facing Content-Security-Policy, add following `link` tag to `index.html`

```html
<link rel="shortcut icon" type="image/x-icon" href="favicon.ico" />
```

### Setup Custom Domain

Set the Custom Domain you want for the project at repository Setting (e.g. portfolio.example.com)

Buy a domain name from DNS provide (e.g. Exabytes), go to DNS Manager create a new zone, set the IP to 185.199.108.153,
create a new record, set the name to the subdomain (e.g. portfolio), set type as CNAME, set rdata to <username>.github.io

Wait for the DNS provision to take effect.

### Customize the configuration

See [Configuring quasar.conf.js](https://quasar.dev/quasar-cli/quasar-conf-js).
