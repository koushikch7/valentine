# Valentine Page

A single-page Valentine experience that personalizes a romantic page from URL parameters. Designed for static hosting (Cloudflare Pages) with no backend.

## Features
- Personalization via URL parameters
- Optional Google Photos album embed
- Date-based "time together" counter
- Interactive Valentine popup (Yes/No)
- Downloadable memory snapshot
- Theme selection

## URL Parameters
- name: Required. The valentine name.
- date: Optional. Important date in YYYY-MM-DD.
- datetype: Optional. marriage | firstmeet | engagement
- message: Optional. Short custom message (max 250 characters).
- theme: Optional. sunset | rose | midnight | golden
- album: Optional. Public Google Photos album link (https only).

Example:
https://us.example.com/?name=Shivani&date=2022-11-27&datetype=marriage&message=You%20are%20my%20calm%20in%20every%20storm&theme=sunset&album=https%3A%2F%2Fphotos.app.goo.gl%2FXXXX

## Setup Form (No Params)
If no parameters are provided, the page shows a setup form to generate a personalized link. The form validates:
- Name is required
- Message length is limited to 250 characters
- Album link must be a valid https URL

## Deploy to Cloudflare Pages
1. Push this repository to GitHub.
2. Create a Cloudflare Pages project and connect the repo.
3. Build command: (leave empty)
4. Output directory: /

## Notes
- Autoplayed music starts after the user accepts the popup (browser policy compliance).
- Album links must be public and shared with link sharing enabled.
