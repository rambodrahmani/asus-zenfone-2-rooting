# Asus Zenfone 2 Rooting
Istruzioni minimali per il Rooting dell'Asus Zenfone 2 (ASUS_Z00AD)

### Prerequisiti
####Asus_Zenfone_2_Rooting_Files.zip

Scaricare ed estrarre il file "Asus_Zenfone_2_Rooting_Files.zip" che trovate tra i files di questa repo.
Dentro sono presenti sia gli strumenti (Windows e Mac OS X) che i file da utilizzare per flashare il dispositivo.

####Linux

Per Linux dovrete installare android-tools:

Arch:	https://wiki.archlinux.org/index.php/Android

Debian:	https://packages.debian.org/sid/android-tools-adb

Ubuntu:	https://launchpad.net/ubuntu/+source/android-tools

### Abilitare USB Debugging

Al percorso System Settings > About > Software information fate click 7 volte su "Build number" sino a che non apparirà il messaggio che indica l'attivazione della modalità Developer.

Dopo di che al percorso System Settings > Developer options, sezione "Debugging", trovate l'opzione per abilitare "USB debugging" per dispositivo.

### Collegamento USB

Collegare l'Asus Zenfone 2 al vostro computer e utilizzare il seguente comando per assicurarvi che il dispositivo sia stato riconosciuto.

```bash

adb devices

```


