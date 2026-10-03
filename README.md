# Embercrown — Card Chronicle

A basic Gwent-inspired main menu + card collection screen, built as a
standalone practice project. Original assets and wordmark only — not
affiliated with, and not using any assets from, CD Projekt Red's Gwent.

## Stack

Next.js 16 (App Router) · TypeScript · Tailwind CSS v4 · framer-motion ·
lucide-react. Fonts (Cinzel, EB Garamond) are self-hosted via
`@fontsource`, so no external network calls are needed at build or run
time.

## Run it

```bash
npm install
npm run dev
```

Then open http://localhost:3000.

## What's here

- **Main Menu** (`app/page.tsx`) — full-bleed torch-lit background, an
  ornate gold-filigree panel with Collection / Options / Exit.
- **Navigation** (`components/PageTransition.tsx`) — cross-fade between
  routes; `components/BackButton.tsx` returns to the menu.
- **Collection** (`app/collection/page.tsx`) — empty state, card grid,
  and an always-visible "Add Card" button.
- **Add Card flow** (`components/AddCardModal.tsx`) — name, description,
  faction dropdown, power, and an optional image upload (downscaled
  client-side in `lib/image.ts` before it's stored).
- **Card component** (`components/CardFrame.tsx`) — the reusable
  Gwent-style card frame: ornate border, power badge, art area, name,
  faction tag, description. Used for every card in the grid.
- **Signature motif** (`components/OrnateFrame.tsx`) — the corner
  flourish reused by the menu panel, the modal, and every card.

## Storage

Cards live in React state and are mirrored to `localStorage`
(`lib/useCollection.ts`, `lib/storage.ts`) so your collection survives a
refresh. There's no backend — clearing site data clears the collection.

## Out of scope (by design)

No battle logic, no multiplayer/accounts, no sound, no faction rules or
deck-building constraints — just the menu and collection UI.
# Gwent
