# NexusOS (team.nexus.os)

Windows 12 NEXUS web-OS, упакованная в Android-приложение через Capacitor.
Весь интерфейс — это `www/index.html`. Изменил его, запушил — получил новый APK.

## Как собрать APK

1. Создай пустой репозиторий на github.com (например `nexus-os`).
2. В Termux, из папки проекта:

       pkg install git
       git init
       git add .
       git commit -m "NexusOS"
       git branch -M main
       git remote add origin https://github.com/ТВОЙ_НИК/nexus-os.git
       git push -u origin main

   Вместо пароля GitHub просит Personal Access Token (Settings → Developer settings → Tokens, право `repo` и `workflow`).

3. Открой вкладку **Actions** → **Build NexusOS APK** → дождись зелёной галочки (~5–8 минут).
4. Внизу страницы запуска, в **Artifacts**, скачай `NexusOS` (внутри `NexusOS.apk`).
5. Установи APK (разреши установку из неизвестных источников).

## APK без zip-архива

Создай тег — файл `NexusOS.apk` появится прямо в **Releases**:

    git tag v1
    git push origin v1

## Что делает патч

`patch/patch-android.sh` включает альбомную ориентацию и полноэкранный режим
(системные панели скрыты, показываются свайпом от края).
