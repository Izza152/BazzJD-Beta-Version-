# BazzJD 🎵

Media player hybrid modern bernuansa Dark Mode untuk **Android, iOS, dan Windows (Flutter)**.
BazzJD memutar **musik lokal**, **streaming URL**, dan wujud **audio-only** dari YouTube Music.
Dilengkapi **equalizer native**, **lirik sinkron (karaoke)**, **pemutar latar belakang**, dan **pengaturan ritme** lengkap.

Desain: dark `#121212`, aksen lime `#00FF88`, mengikuti `refrensi_ui.jpg`.

## Fitur Utama
- 🎧 **Local Audio Player** — mp3, aac, flac, wav, m4a, ogg, opus, wma, aiff, ape, dsf, mka, …
- 🌐 **Streaming URL Player** — putar URL audio (mobile & desktop).
- 🎬 **YouTube Music (audio-only)** — tanpa video, stream segar.
- ⏯️ **Background Playback** — notifikasi & lock screen: play/pause/skip/seek/album art.
- 🎛️ **Equalizer native (Android)** + graceful disable di iOS/Windows.
- ⚡ **Speed 0.5–2.0×**, **Pitch control**.
- 🎤 **Synced Lyrics (Karaoke)** — LRCLIB auto-match, `.lrc` lokal, offset calibration, pencarian manual.
- 🔐 **Akun opsional** — server BazzJD sendiri + sync; fallback **Guest lokal**.
- ⚙️ Settings runtime — tema (6 aksen + dark/light), balance, crossfade 0–12s, gapless, filter live YouTube, quality audio YT, backup JSON.
- 🧭 Shell adaptif — mobile Bottom Navigation + MiniPlayer; desktop NavigationRail + bottom player.

## Struktur
```
lib/
├── core/        theme, models, utils
├── services/    audio_player_service, equalizer_service, permission_service
├── data/        lyric_service, youtube_service, playlist_repository, settings_repository, ...
├── providers/   Riverpod state
├── features/    shell, player, equalizer, lyrics, auth, home, search, library, playlists, settings
└── widgets/     track_tile, artwork resolver, konteks menu

backend/         FastAPI + yt-dlp + SQLite (opsional)
```

## Menjalankan
```bash
flutter pub get
flutter run                     # device aktif
flutter run -d windows          # desktop
flutter build windows           # rilis Windows
flutter build apk              # rilis Android
```

Backend (opsional):
```bash
cd backend && run.ps1   # Windows
```

## Lisensi
Proyek private (`publish_to: none`). Fitur offline-friendly; tanpa akun tetap jalan.

---

## Credits & Sumber yang Digunakan

### Layanan / Sumber Data
- YouTube Music (InnerTube WEB_REMIX)
- LRCLIB (lrclib.net) — lirik sinkron
- GitHub — inspirasi tampilan dark.

### Pustaka Open Source
- Flutter & Dart (Google) — BSD-3-Clause
- just_audio, just_audio_background, audio_service, audio_session — Ryan Heise & kontributor — Apache-2.0
- youtube_explode_dart — ekstrak audio-only YouTube
- flutter_riverpod, rxdart, async — state & reaktivitas
- on_audio_query — pustaka media
- file_picker, path_provider, permission_handler, device_info_plus
- shared_preferences, google_fonts, cached_network_image, flutter_svg, marquee
- window_manager, screen_retriever, flutter_acrylic, ffi
- FastAPI, Uvicorn, yt-dlp, Python, SQLite, FFmpeg/ffprobe (backend)
- Material Design Icons (Google)

### Aset Desain
- `assets/branding/bazzjd_icon_512.png`
- `assets/branding/bazzjd_icon_1024.png`
- `assets/branding/bazzjd_wordmark.png`
- Desain mengikuti `refrensi_ui.jpg` (dark `#121212`, aksen lime `#00FF88`).

### Kontributor
- Pengembang utama: **BazzJD Team / Izza**
- Desain UI/UX pengembang.

### Penghargaan
- Ryan Heise — ekosistem audio Flutter
- Kontributor open source: `youtube_explode_dart`, `flutter_riverpod`, `lrclib`
- Komunitas Flutter

> Catatan: Gunakan sumber audio YouTube sesuai ketentuan platform & hukum setempat.
