# Project Template

A minimal Expo + Expo Router + React Native (TypeScript) starter with NativeWind (Tailwind) support.

This repository uses Expo, `expo-router`, and NativeWind for Tailwind-style styling.

## Quick overview

- Framework: Expo (React Native)
- Router: `expo-router`
- Styling: Tailwind via `nativewind` and `tailwindcss`
- Language: TypeScript

## Common scripts

The following scripts are available from `package.json`:

- `pnpm start` — run the Expo Metro dev server (same as `expo start`)
- `pnpm android` — start and open Android
- `pnpm ios` — start and open iOS
- `pnpm web` — open the web build
- `pnpm lint` — run ESLint
- `pnpm run reset-project` — custom reset script (see `scripts/reset-project.js`)

You can run them with `pnpm` (or `npm run ...` / `yarn ...`).

## Run (dev)

Start the dev server:

```bash
pnpm start
```

From the Expo dev tools you can:

- Press `a` to open Android emulator/device
- Press `i` to open iOS simulator
- Press `w` to open in web browser

Or directly run:

```bash
pnpm android
pnpm ios
pnpm web
```

## Project file layout

```
app/
   _layout.tsx      # Root layout for expo-router (renders <Stack />)
   index.tsx        # Home screen (edit this)
   global.css       # Global CSS (Tailwind / NativeWind)
assets/
   images/          # Images and media
app.json
package.json
pnpm-lock.yaml
tailwind.config.js
babel.config.js
tsconfig.json
```

## Key files & small templates

Below are the existing minimal templates in this repo. You can copy/replace them when you need to scaffold new screens.

- `app/index.tsx` (home screen)

```tsx
import { Text, View } from "react-native";

export default function Index() {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: "center",
        alignItems: "center",
      }}
    >
      <Text>Edit app/index.tsx to edit this screen.</Text>
    </View>
  );
}
```

- `app/_layout.tsx` (expo-router root layout)

```tsx
import { Stack } from "expo-router";
import "./global.css";

export default function RootLayout() {
  return <Stack />;
}
```

- `app/global.css` (Tailwind entry, nativewind should be configured in `tailwind.config.js`)

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Add global styles here */
```

## NativeWind / Tailwind notes

This repo includes `nativewind` and `tailwindcss` in dependencies. If you need to reconfigure:

1. Check `tailwind.config.js` for content paths (should include `app/**/*.{js,ts,tsx}`)
2. Restart Metro bundler after changing Tailwind config

If Tailwind classes aren’t applied, ensure the NativeWind babel plugin is present in `babel.config.js` and restart the bundler.

## TypeScript

This project uses TypeScript (see `tsconfig.json`). Keep `nativewind-env.d.ts` for global Tailwind types.

## Assets

Put images in `assets/images` and reference them with `require("../assets/images/your.png")` or `import` when using `expo-asset`/`expo-image`.

## Troubleshooting

- Metro cache issues: `pnpm start -- --clear` or `expo start -c`
- iOS simulator not opening: ensure Xcode Command Line Tools installed and simulator available
- Android emulator: ensure Android Studio and an AVD are configured
- If Tailwind classes don’t apply, restart Metro and ensure `nativewind` Babel plugin is enabled in `babel.config.js`.
