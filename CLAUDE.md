# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Valle Aventura is a single-page web application ("Welcome Book") built in Spanish. The entire application is bundled into a single `index.html` file (~26 MB) — this is the deployed artifact, not source code.

## Running the App

Open `index.html` directly in any modern web browser. There is no build step, dev server, or package manager in this repository.

## Architecture

`index.html` is a self-contained runtime loader that:
- Embeds all assets (images, fonts, scripts, styles) as base64-encoded, gzip-compressed data in a `__bundler` manifest
- Decompresses and reconstructs those assets into blob URLs at runtime
- Renders the full application from within a single file

The bundle contains Vue.js and/or React with Next.js/Nuxt.js references, served via Cormorant Garamond (Google Font, embedded).

**Branding:** dark green (`#2d4a2e`), gold (`#f0c419`), cream (`#f5f1e6`) — mountain/adventure theme.

## Modifying the App

This repo contains only the compiled output. To make changes you need the original source project (likely a visual builder export such as Webflow, or a Vue/React/Nuxt project). Directly editing the minified bundle inside `index.html` is possible but fragile — prefer locating/restoring the source.
