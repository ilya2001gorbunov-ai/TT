Клип
Приложение для коротких видео: лента, оценка авторов, рейтинг в профиле, платные сообщения, витрина подарков, карта пользователей рядом. Это демо-версия: платежи не подключены, данные хранятся на устройстве.
Как получить APK
Создайте на GitHub новый репозиторий (например, klip).
Загрузите в него все файлы из этого архива, включая папку .github:
git init
git add .
git commit -m "Клип"
git branch -M main
git remote add origin https://github.com/ВАШ_ЛОГИН/klip.git
git push -u origin main
Откройте вкладку Actions и дождитесь зелёной галочки (5–10 минут).
Откройте раздел Releases справа на главной странице репозитория и скачайте klip.apk.
На телефоне откройте файл и разрешите установку из неизвестных источников.
Если сборка не создаёт релиз: Settings → Actions → General → Workflow permissions → Read and write permissions, затем запустите сборку заново через Actions → Build APK → Run workflow. Файл также лежит во вкладке Actions в разделе Artifacts.
Что менять
Весь интерфейс находится в www/index.html. После изменения и git push APK пересоберётся автоматически.
Имя и идентификатор приложения: capacitor.config.json.
Google Maps
В www/index.html на вкладке «Карта» нарисована демо-карта. Чтобы подключить настоящую, получите API-ключ в Google Cloud Console, подключите Maps JavaScript API в index.html и добавьте разрешение геолокации в android/app/src/main/AndroidManifest.xml (ACCESS_FINE_LOCATION). Папка android создаётся при сборке, поэтому разрешение добавляйте шагом в .github/workflows/build-apk.yml.
Android 17
Это отладочная сборка (debug), она устанавливается напрямую без Google Play и работает на новых версиях Android. Для публикации в Google Play нужны подписанная release-сборка и актуальный targetSdk.
