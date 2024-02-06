## 🚀 Getting Started

### 1. Setting up the .env file

rename the `env.txt` to `.env` and fill in your details

```ENV
BLOG_SLUG=blog
PORTFOLIO_SLUG=work
SHOP_SLUG=shop
MENU_SLUG=menu
WEBSITE_LANGUAGE=en
CURRENCY=USD
UNITS=metric
SNIPCART_KEY=<your-snipcart-public-key>
NODE_VERSION=18
NEWSLETTER_PROVIDER=mailchimp
MAILCHIMP_API_KEY=XXXXXXXXXXXXXXXX-us21
MAILCHIMP_SERVER_PREFIX=us21	
MAILCHIMP_LIST_ID=XXXXXXXXX

FROM_EMAIL_ADDRESS=[test@email.com](mailto:test@email.com)
TO_EMAIL_ADDRESS=[test@email.com](mailto:test@email.com)

MAILGUN_API_KEY=XXXXXXXXX
MAILGUN_DOMAIN=XXXXXXXXX
MAILGUN_API_URL=<https://api.eu.mailgun.net>

POSTMARK_SERVER_TOKEN=XXXXXXXXX

SLACK_CHANNEL_ID=XXXXXXXXX
SLACK_TOKEN=XXXXXXXXX

```

### 2. Configure your Static CMS Backend

Navigate to `src/pages/admin.astro` and provide your Git repository details. You can find a list of all supported Git backends at:
<https://www.staticcms.org/docs/backends-overview>


**_Gitlab Example:_**

```javascript

const config = {
	locale: lang,
	site_url: url,
	logo_url: 'https://url-to-your-logo',
	local_backend: true,
	backend: {
		name: 'gitlab',
		repo: '/<your-gitlab-repo>',
		auth_type: 'pkce', // Required for pkce
		app_id: 'xxxx', // Application ID from your GitLab settings
		commit_messages: {
			create: 'Create {{collection}} "{{slug}}"',
			update: 'Update {{collection}} "{{slug}}"',
			delete: 'Delete {{collection}} "{{slug}}"',
			uploadMedia: 'Upload "{{path}}"',
			deleteMedia: 'Delete "{{path}}"'
		}
	},
	search: 'true',
    ....
}

```

### 3. Add your site to the astro config

```javascript

export default defineConfig({
	site: 'https://your-website.com',
    ....

```

## 🛸 Commands

All commands are run from the root of the project, from a terminal:

| Command                    | Action                                           |
| :------------------------- | :----------------------------------------------- |
| `npm install`              | Installs dependencies                            |
| `npm run dev`              | Starts local dev server at `localhost:4321`      |
| `npm run cms-proxy-server` | Starts Static CMS proxy server for local-backend |
| `npm run build`            | Build your production site to `./dist/`          |
| `npm run preview`          | Preview your build locally, before deploying     |
| `npm run astro ...`        | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help`  | Get help using the Astro CLI                     |

## 👀 Want to learn more about Astro?

Check out [Astro documentation](https://docs.astro.build) or jump into Astro's [Discord server](https://astro.build/chat).








