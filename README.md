# AURVION

AURVION is a local-first Windows voice assistant project. The intended architecture combines an offline speech pipeline, a selectable local GGUF language model, an allow-listed desktop automation layer, a configurable voice/personality interface, and a Windows installer.

## Build status

The repository is being prepared for a Windows CI build. The installer is **not yet a released or verified binary**. A successful GitHub Actions run will publish the setup executable as a downloadable workflow artifact.

## Windows build

The workflow `.github/workflows/build-windows.yml` runs on GitHub-hosted Windows x64 and:

1. validates the expected project and branding files;
2. installs Python dependencies;
3. downloads the Russian Vosk speech model;
4. runs the test suite;
5. packages the app with PyInstaller;
6. compiles the Inno Setup installer;
7. uploads `AURVION_Setup_Windows_x64` as a workflow artifact.

Run it from **Actions → AURVION Windows installer → Run workflow**.

## Important

- The local GGUF language model is not bundled; users select a compatible model file locally.
- Startup is intended to be optional and per-user, not a hidden system service.
- Desktop automation runs in the signed-in user's session. Administrator operations remain subject to Windows UAC.
- Do not use the app to bypass restrictions on computers managed by a school or employer.
- The safety filters are preliminary and must not be represented as a complete security guarantee.
