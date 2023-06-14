# Security

Security is an important aspect of all modern web applications. Implementing good security practices help prevent and mitigate various security threats and keep the user's data safe. The checklist below includes the common recommendations and sanity checks that will greatly improve security of your web applications.

## General rules

- Use encrypted protocols everywhere (HTTPS for web traffic, WSS for secure socket connection)
- Don’t build custom authentication system yourself, use tried and tested libraries instead
- Keep your dependencies up-to-date to prevent zero-day vulnerabilities
- Exclude admin and private URLs from indexing and crawling (using robots.txt)
- Don’t use iterable URLs (e.g. prefer `/users/[guid]` or `/users/[handle]` instead of `/users/[incremented-integer]`)
- Remove unused functionality instead of hiding it (with `display: none`, for instance)
- Use DDOS mitigation via a global caching proxy service like CloudFlare
- For apps containing sensitive data, consider implementing auto session termination after a period of inactivity or require addition password check for destructive actions
- Set `Cache-Control: no-store, max-age=0` for non-public/non-static content to make sure that the sensitive user-specific data doesn’t remain cached on disk after a logout
- Add [subresource integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) checks if loading your JavaScript libraries from a third party CDN

## Server secrets

- Don’t hardcode API keys and tokens, store them in the `.env` file instead
- Don’t commit `.env` file to the repository. Alternatively, f you want everyone with access to the repo have access to all the secrets, you can encrypt & version `.env` file using git-crypt
- Don’t expose secret tokens from `.env` file to the client (make sure that you only access them in the server code, e.g. inside React server components or `getServerSideProps`)

## Client secrets

- Store session IDs and auth tokens in `Secure` `HttpOnly` cookies, not `localStorage` or `sessionStorage` (also [SameSite=Lax](https://web.dev/samesite-cookies-explained/#explicitly-state-cookie-usage-with-the-samesite-attribute))
- Scope cookies to a domain (and a path, if applicable)

## User input

- Sanitize all user input, especially the values that will be passed to `dangerouslySetInnerHTML` to prevent XSS attacks
- Always use whitelisting over blacklisting, aka list values that are allowed instead of listing values that aren’t
- Use CAPTCHAs on sign-in and sign-up forms to prevent password enumeration

## iFrames

- Don’t use iFrames unless absolutely necessary (e.g. for third-party integrations)
- Add `sandbox` attribute to enable [extra set of restrictions](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attributes) on the iFrame content
- Disable iFrame embedding to prevent click-jacking attacks with `X-Frame-Options` header:

```bash
X-Frame-Options: "DENY"
```

## Security headers

> Use [https://securityheaders.com/](https://securityheaders.com/) to verify your security headers configuration

- Use strong Content Security Policy headers ([CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy)) to mitigate XSS and data injection attacks

```bash
Content-Security-Policy: default-src 'none'; script-src 'self'; img-src 'self'; style-src 'self'; connect-src 'self';
```

It’s better to start with the most restrictive settings, and start loosening them as needed (e.g. allowing unsafe-inline styles when using styled components or whitelisting more domains when using 3rd party integrations)

- Disable access to browser features and APIs that aren’t used:

```bash
Feature-Policy: accelerometer 'none'; ambient-light-sensor 'none'; autoplay 'none'; camera 'none'; encrypted-media 'none'; fullscreen 'self'; geolocation 'none'; gyroscope 'none'; magnetometer 'none'; microphone 'none'; midi 'none'; payment 'none';  picture-in-picture 'none'; speaker 'none'; sync-xhr 'none'; usb 'none'; vr 'none';

Permissions-Policy: accelerometer=(), ambient-light-sensor=(), autoplay=(), camera=(), encrypted-media=(), fullscreen=(), geolocation=(), gyroscope=(), magnetometer=(), microphone=(), midi=(), payment=(), picture-in-picture=(), speaker=(), sync-xhr=(), usb=(), vr=();
```

⚠️ `Feature-Policy` header is being renamed to `Permission-Policy`, so in the future only the latter will be used.

- Use [HSTS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security) header to block all attempts to downgrade HTTPS to HTTP (or WSS to WS)

```bash
Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```

- Enable [X-XSS-Protection](https://www.owasp.org/index.php/OWASP_Secure_Headers_Project#X-XSS-Protection) mode to mitigate XSS attacks

```bash
X-XSS-Protection: 1; mode=block
```

## Github

- Disable forking for the repository
- Restrict & control access
- Protect production branch - prevent force push & deletion, require signed commits, require PR approval from code owners before merging
- Use minimally scoped credentials for running Github Actions
- Use Github Secrets for storing environment variables for Github Actions
- Don't reference values in Github Actions that can be set by users (e.g. PR title and body)
