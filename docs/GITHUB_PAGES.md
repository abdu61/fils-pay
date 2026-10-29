# GitHub Pages deployment

The `pages.yml` workflow publishes only the React frontend in `apps/web`
to [https://abdu61.github.io/fils-pay/](https://abdu61.github.io/fils-pay/).
The app and API routes are configured for the repository subpath, and the
workflow builds a fallback page for direct links.

GitHub Pages does not run the FilsPay API, database, admin console, or
settlement services. To connect the frontend, add a repository Actions
variable named `VITE_API_BASE_URL` with the HTTPS API origin (for example,
`https://api.example.com`). The API must allow requests from
`https://abdu61.github.io` and support the frontend's credentialed session
cookies. Without that variable, API requests display a configuration error;
they do not target the visitor's own localhost.

The Pages site is public because this repository is public. Merging a change
to `main` deploys it. Pull requests build the frontend but do not publish it.
