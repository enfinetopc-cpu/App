# ENFINET OPC Subscriber App — Starter Project

Ito ay **starter/preview project**, hindi pa production-ready app. Ang dashboard ay may custom design at shortcut links sa official website. Hindi pa nakakakuha ng aktuwal na subscriber balance, pangalan, billing records, o payment history mula sa database.

## Paano i-build gamit ang Android phone

1. I-download at i-extract ang ZIP.
2. Gumawa o mag-sign in sa GitHub account gamit ang browser ng phone.
3. Gumawa ng bagong **private repository** na may pangalang `enfinet-opc-subscriber`.
4. I-upload ang mga file/folder mula sa ZIP sa repository root. Siguraduhing kasama ang `.github/workflows/build-apk.yml` (maaaring kailanganing paganahin ang pagpapakita ng hidden files sa file manager).
5. Buksan ang tab na **Actions** ng repository. Kung may prompt, piliin ang pag-enable ng workflows.
6. Piliin ang **Build ENFINET OPC Android APK** at pindutin ang **Run workflow**.
7. Kapag successful, buksan ang run, hanapin ang **Artifacts**, at i-download ang `enfinet-opc-subscriber-debug-apk`.
8. I-extract ang na-download na artifact ZIP at i-install ang `app-debug.apk` sa Android phone.

GitHub Actions cloud-build reference: https://docs.github.com/actions

## Bago ipamahagi sa subscribers

- Ito ay debug APK para sa testing lamang. Hindi ito signed production release.
- Huwag ipamahagi sa subscribers hangga't hindi nasusubukan at naihahanda ang signed release.
- Para ipakita ang aktuwal na billing at payment history, kailangang magdagdag ng secure PHP API sa server na nagva-validate ng subscriber session/token at nagbibigay lamang ng sariling records ng naka-login na subscriber.
- Huwag ilagay ang MySQL credentials, payment secrets, o private signing key sa app source code o public repository.
- Panatilihing sa official ENFINET checkout ang pagbabayad; huwag mag-imbak ng card/payment credentials sa app.
- Bago ang production, kailangang subukan ang login, logout, network errors, payment redirect, at Android back navigation.

## App identifiers

- App name: ENFINET OPC
- Package ID: `com.enfinetopc.subscriber`
- Version starter: `1.0.0`
