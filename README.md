# Workout Tracker

A mobile-friendly minimum-effective-dose workout tracker hosted with GitHub Pages.

## Features

- Email/password accounts through Supabase Auth
- Private cloud history shared across devices
- Workout, cardio, and mobility logging
- Next-weight recommendations based on the latest matching exercise:
  - increase after both sets reach the top of the rep range near target RIR
  - hold while progressing within the range
  - reduce slightly when performance falls below the range
- Local storage remains as an offline/device fallback

## Supabase setup

The app uses the Supabase project `Workout Tracker`. Its publishable browser key is intentionally included in `index.html`; access is protected by Row Level Security. Never add a secret or service-role key to this repository.

In Supabase Dashboard, open **Authentication → URL Configuration** and set:

- Site URL: `https://bezbear.github.io/workout-tracker/`
- Redirect URL: `https://bezbear.github.io/workout-tracker/**`

Under **Authentication → Providers → Email**, choose whether new accounts must confirm their email. If confirmation is enabled, users must follow the email link before their first sign-in.

## Privacy

Each cloud table uses Row Level Security so authenticated users can only read and change rows whose `user_id` matches their account.
