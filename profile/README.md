<div align="center">

<img src="https://raw.githubusercontent.com/Awlak-Benjah/.github/main/profile/icon.png" width="96" height="96" alt="Awlak Benjah? app icon" />

# Awlak Benjah?

**Track your degree semester by semester and see your projected average against the pass mark.**<br />
Offline. No account. In English, French and Arabic.

[awlak-benjah.com](https://awlak-benjah.com)

<br />

<table>
  <tr>
    <td align="center">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Awlak-Benjah/.github/main/profile/screens/en-US-dark.jpg" />
        <img src="https://raw.githubusercontent.com/Awlak-Benjah/.github/main/profile/screens/en-US-light.jpg" width="240" alt="The dashboard in English" />
      </picture>
      <br />English
    </td>
    <td align="center">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Awlak-Benjah/.github/main/profile/screens/fr-FR-dark.jpg" />
        <img src="https://raw.githubusercontent.com/Awlak-Benjah/.github/main/profile/screens/fr-FR-light.jpg" width="240" alt="The dashboard in French" />
      </picture>
      <br />Français
    </td>
    <td align="center">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Awlak-Benjah/.github/main/profile/screens/ar-SA-dark.jpg" />
        <img src="https://raw.githubusercontent.com/Awlak-Benjah/.github/main/profile/screens/ar-SA-light.jpg" width="240" alt="The dashboard in Arabic, laid out right to left" />
      </picture>
      <br />العربية
    </td>
  </tr>
</table>

</div>

## What we hold ourselves to

- **Your grades stay on your phone.** The app works with no account. Signed out, it downloads degree presets and sends anonymous crash reports, which you can turn off, and that's all. Every change that would send data anywhere updates the privacy policy in the same pull request, or it doesn't ship.
- **Arabic is laid out right to left from the start, not translated at the end.** Every screen mirrors, down to the native menus and sheets. React Native doesn't reach those on its own, so we wrote a native module that does.
- **Native where your thumb lands.** On iOS, toggles, menus, pickers and sheets are SwiftUI with Liquid Glass. On Android they're our own. Everything around them is our own design.
- **Lint checks the architecture, so reviews don't have to.** Module boundaries, MVVM layers and "no logic in a view" are rules that fail the build.

## How it's built

```mermaid
flowchart LR
  subgraph phone[On your phone]
    app[Expo app] --- db[(SQLite<br/>your grades)]
  end
  app -- "preset catalog" --> api[API]
  app -. "optional account: name and email" .-> api
  api --- pg[(Postgres)]
  console[Admin console] --> api
  site[awlak-benjah.com]
```

| | |
| --- | --- |
| **App** | Expo SDK 58, React Native 0.88, SwiftUI through `@expo/ui`, SQLite with Drizzle, Reanimated |
| **API** | NestJS, contract-first oRPC, Postgres, better-auth |
| **Console** | Vite, React, TanStack Router and Query, shadcn |
| **Site** | Astro on Cloudflare Workers |
| **Repo** | Turborepo, pnpm, TypeScript 7, oxlint, dependency-cruiser, release-please |

<sub>The app's source is private. Questions: [support@awlak-benjah.com](mailto:support@awlak-benjah.com)</sub>
