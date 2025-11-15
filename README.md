```bash
# American Center for Cricket — Static Website (ACC)

This repository contains a ready-to-publish static website (index.html) for the American Center for Cricket (ACC). The site is static (no build required) and uses Tailwind CSS via CDN for styling.

Files added:
- `index.html` — full static site (hero, programs, coaches, contact/enroll form)
- `CNAME` — your custom domain file (AmericanCenter4Cricket.com)

Quick publish steps (GitHub Pages)
1. Add/commit these files to the root of your repository (branch `main` or `master`).
   - Example:
     ```
     git add index.html CNAME README.md
     git commit -m "Add static ACC site and CNAME"
     git push origin main
     ```

2. Enable GitHub Pages
   - In your repository on GitHub: Settings → Pages.
   - Source: choose the branch (`main`) and folder: `/ (root)`.
   - Save. GitHub will publish the site at `https://<your-username>.github.io/<repo>/` and will use the CNAME file to set the custom domain.

3. DNS configuration for your domain (AmericanCenter4Cricket.com)
   - For apex domain (AmericanCenter4Cricket.com), add A records pointing to GitHub Pages IPs:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
   - Add a CNAME for `www` pointing to: `<your-github-username>.github.io`
     - e.g., `www` CNAME -> `americancenter4cric.github.io`
   - Wait for DNS propagation (can take minutes to 48 hours).
   - Back in GitHub Pages settings, set the custom domain to `AmericanCenter4Cricket.com` (it may auto-detect from the CNAME file). Ensure “Enforce HTTPS” is enabled once certificate is issued.

Contact form
- The current form uses Formspree placeholder `action="https://formspree.io/f/your-form-id"`.
- To receive form submissions:
  1. Sign up at https://formspree.io and create a form. Replace `your-form-id` with the provided ID.
  2. Alternatively, you can replace the form with a Mailto link or implement your own backend.

Notes & recommended production improvements
- Tailwind CDN is fine for prototypes. For production, consider:
  - Prebuilding CSS with Tailwind to reduce unused CSS and improve performance.
  - Optimizing images and adding a logo in `Logo.jpg`.
  - Adding an `assets/` folder for images, PDF curriculum, and favicon.
  - Optionally set up a CI/CD workflow (GitHub Actions) to build and publish to `gh-pages` branch.
- To use HTTPS + custom domain, ensure DNS is correct and enable “Enforce HTTPS” in Pages settings.
