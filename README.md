# E5785Lh-23c: файлы прошивок

Чужие файлы, которые нужны для установки [e5785lh-23c-mod](https://github.com/vakame7058/e5785lh-23c-mod): прошивки Huawei, мод bay v5, WebUI и загрузчик. Инструкции, исходники и все наше — в основном репозитории. Файлы лежат в [релизе](https://github.com/vakame7058/e5785lh-23c-mod-bin/releases/latest), контрольные суммы — в [SHA256SUMS](SHA256SUMS).

> Внимание: только для E5785Lh-23c (плата `CL1E5785SM VER.A`). На E5785Lh-22c не ставить. Все на свой риск.

## Файлы

| файл | что это | откуда | где нужен |
|---|---|---|---|
| `E5785Lh-92a-23c_E5783h-92a_UPDATE_21.191.63.02.00.BIN` | официальная прошивка 21.191.63.02 для 92a и 23c | Huawei, пакет `E5785Lh-92aTCPU-V200R001B191D63SP02C00 Firmware general 05016ARS` | стоковая прошивка, сверка разделов |
| `WEBUI_21.100.52.00.03_NE5.BIN` | официальный WebUI 21.100.52.00.03 | Huawei, пакет `E5785LhWebUI-V200R001B100D52SP00C03 Client Software general 05016ART` | стоковый веб-интерфейс |
| `E5785Lh-92a-23c_E5783h-92a_UPDATE_21.191.63.02.00.baymod.v5.fw` | мод bay v5 на базе 21.191.63.02 | bay3255, 4PDA, тема 907081, пост 95373571 | все разделы, кроме `webui` |
| `modwebui_1.5a.zip` | веб-интерфейс мода | bay3255 и e-dok, 4PDA, тема 907081, пост 80753809 | раздел `webui`; без него экран черный |
| `usblsafe-e5785.bin` | загрузчик для входа через BootROM, собран под 22c | [forth32/balong-usbdload](https://github.com/forth32/balong-usbdload) | исходный файл для правки |
| `usblsafe-e5785-ptable23c.bin` | тот же загрузчик с таблицей разделов 23c | `tools/recovery/patch_usblsafe_ptable23c.py` из основного репозитория | загрузка в память через иголку |

Файлы Huawei и мода выложены без изменений: суммы совпадают с исходными архивами. Второй загрузчик можно получить самому из первого:

```bash
python3 tools/recovery/patch_usblsafe_ptable23c.py usblsafe-e5785.bin usblsafe-e5785-ptable23c.bin
```

## Проверка

```bash
sha256sum -c SHA256SUMS
```

## Порядок установки

Порядок, команды и откат — в основном репозитории: [установка](https://github.com/vakame7058/e5785lh-23c-mod/blob/main/docs/install.md) и [восстановление](https://github.com/vakame7058/e5785lh-23c-mod/blob/main/docs/recovery.md).

## Права

Файлы принадлежат их авторам: Huawei, bay3255, e-dok, forth32. Здесь они собраны для удобства владельцев роутера. Если вы правообладатель и хотите убрать файл, откройте issue.
