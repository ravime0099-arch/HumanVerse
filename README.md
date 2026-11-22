# HumanVerse

HumanVerse is a mobile-first web/PWA foundation for anatomy learning, medical education and creative character workflows.

## Included in this first web build
- Responsive dashboard and navigation for all planned studios.
- Anatomy learning overview with selectable body-system summaries and a clearly labeled schematic illustration.
- Fictional character profile configurator (local browser save; not a 3D renderer).
- Medical Academy starter lesson outlines.
- Patient 3D Lab placeholder with medical-privacy warning.
- Local-only community feed prototype.
- Guest browsing mode and Supabase email/password authentication hook.
- Installable PWA manifest and lightweight offline shell.
- GitHub Actions workflow for GitHub Pages deployment.

## Enable Supabase authentication
1. Open `config.js`.
2. Set `supabaseUrl` to the HumanVerse Supabase Project URL.
3. Set `supabaseAnonKey` to the Supabase anon/public key.
4. Never put a `service_role` key or database password in frontend code.
5. In Supabase Authentication settings, configure the Site URL and allowed redirect URL for the published GitHub Pages address.
6. For production, review email confirmation, password policies, abuse controls and all RLS policies before allowing real user data.

The frontend deliberately does not write to the existing `hv_*` tables yet: their exact column contracts and security policies must be audited before connecting user-generated content or private data.

## Deploy
The workflow in `.github/workflows/pages.yml` deploys the repository root to GitHub Pages after pushes to `main`. In GitHub, open **Settings → Pages** and set **Build and deployment → Source** to **GitHub Actions** if it is not already selected. The first deployment may take a few minutes.

## Current limitations
This is a working front-end foundation, not the complete product. The 3D anatomy atlas, medically validated models, DICOM/CT/MRI segmentation, secure private messaging, production community backend, age assurance and moderation service require separate implementation and security review. Do not upload identifiable patient data. The site is not a medical device and is not intended for diagnosis or treatment.
