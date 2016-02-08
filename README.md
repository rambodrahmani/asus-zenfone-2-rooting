# Asus Zenfone 2 Rooting
Istruzioni minimali per il Rooting dell'Asus Zenfone 2 (ASUS_Z00AD)

### Avvertenze
####ROOT AT YOUR OWN RISK!

####N.B: Una volta eseguito il procedimento di Rooting del dispositivo, non potrete installare aggiornamenti di sistema senza aver precedentemente eseguito l'Unroot. L'installazione di un aggiornamento di sistema risulterà nell'inutilizzabilità del vostro dispositivo con conseguente perdita dei dati.


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

Collegare l'Asus Zenfone 2 al vostro computer e utilizzare i seguenti comandi per assicurarvi che il dispositivo sia stato riconosciuto.

1)
```bash
lsusb
```
Output:
```bash
...
Bus 002 Device 010: ID ****:**** ASUSTek Computer, Inc.
...
```
2)
```bash
adb devices
```
Output:
```bash
List of devices attached
F7A******419    device
```

### Rooting del Dispositivo

Eseguite il seguente comando e attendete che il dispositivo si riavvii:
```bash
adb reboot-bootloader
```
(adb reboot-bootloader: reboots the device into the bootloader.)

Il risultato che si ottiene è il seguente:

![Alt text](normal-boot.jpg "Asus Zenfone 2 Bootloader")

A questo punto eseguiti comandi uno dopo l'altro aspettando che ciascun termini prima di eseguire il successivo:

N.B: i comandi sono immessi con la cartella Asus_Zenfone_2_Rooting_Files come direttorio corrente:

```bash
sudo fastboot flash /system/bin/resize2fs magic
sudo fastboot flash /system/bin/tune2fs busybox
sudo fastboot flash /system/bin/partlink supersu.tgz
sudo fastboot oem start_partitioning
sudo fastboot flash /system/bin/logcat installer
sudo fastboot oem stop_partitioning
sudo fastboot reboot
```

Il procedimento di Rooting è terminato, il dispositivo si avvierà normalmente dopo l'ultimo comando.

Come ultima verifica dell'avvenuto Rooting del dispositivo, controllate che l'APP SuperSU sia installata e funzionante. Avviatela, sarà richiesto di eseguire l'aggiornamento.

### Riferimenti

- http://forum.xda-developers.com/zenfone2/general/root-newbie-root-instructions-zenfone-2-t3114063