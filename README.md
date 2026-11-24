# CatVoice

Живые голоса для аддона **CatChat** (World of Warcraft Forever, русский клиент). Чат в игре читается вслух голосом по расе и полу того, кто написал.

**[Скачать последний выпуск](../../releases/latest)** — файл `CatVoice-Setup-<версия>.exe`.

## Что это

- Программа для Windows: 17 русских голосов (мужской и женский для каждой расы и рассказчик) и синтезатор речи.
- Работает на вашем компьютере. Интернет, учётные записи и видеокарта не нужны, текст чата никуда не уходит.
- Сама по себе ничего не делает: голосами пользуется аддон CatChat.

## Установка

1. Закройте игру.
2. Запустите `CatVoice-Setup-<версия>.exe`.
   Windows покажет синее окно «Система Windows защитила ваш компьютер»: у установщика нет платной подписи издателя. Нажмите «Подробнее», затем «Выполнить в любом случае».
3. В конце оставьте галочку «Проверить голос сейчас». В течение минуты прозвучит фраза.
4. Поставьте аддон CatChat и заходите в игру: аддон сам проведёт по настройке.

Обновление — новым установщиком поверх старого, удалять прежнюю версию не нужно.

## Что нужно

- Windows 10 или 11, 64 бита.
- 2 ГБ на диске.
- World of Warcraft Forever, русский клиент, аддон CatChat.

## Что программа меняет в системе

- Кладёт файлы в `C:\Program Files\CatVoice`.
- Регистрирует в Windows голоса и голосовой движок (SAPI). Игра загружает этот движок сама, когда читает текст вслух.
- Добавляет в хранилища Windows сертификат, которым подписан движок: без него игра движок не загрузит. Закрытого ключа у этого сертификата нет, подписать им что-то ещё нельзя.
- Запускает синтезатор вместе с Windows (галочка в установщике).

Удаление снимает всё это обратно: меню «Пуск», папка CatVoice, «Удалить CatVoice».

## Если что-то не так

- Нет звука: меню «Пуск», папка CatVoice, «Починить CatVoice».
- В подземельях, рейдах и на боссах тишина: игра прячет там чат от аддонов, это не поломка.
- В игре: `/catchat check`, кнопка «Скопировать отчёт».

## Проверка файла

Рядом с установщиком лежит файл `.sha256` с контрольной суммой. Сверить в PowerShell:

```
Get-FileHash .\CatVoice-Setup-0.1.0.exe -Algorithm SHA256
```

## Авторство и лицензии

- Синтез речи: модель **Shtorm-PocketTTS-RU**, автор ArtShtorm, лицензия CC BY 4.0, https://huggingface.co/ArtShtorm/Shtorm-PocketTTS-RU. Изменения: веса доучены на дополнительных записях речи.
- Основа модели и программа синтеза: **Pocket TTS**, Kyutai Labs, https://github.com/kyutai-labs/pocket-tts.
- Ударения: **silero-stress** (Silero Team, MIT) и словарь **RUAccent**.
- **PyTorch**, BSD-3-Clause.

Полный список компонентов с лицензиями лежит в установленной программе: `C:\Program Files\CatVoice\THIRD_PARTY.md`.

Голоса нельзя использовать, чтобы выдавать себя за другого человека, и для обмана.

---

## English

CatVoice provides Russian voices for the **CatChat** addon (World of Warcraft Forever, Russian client): chat is read aloud in a voice matching the sender's race and sex.

**[Download the latest release](../../releases/latest)**. Windows 10 or 11, 64-bit, 2 GB of disk space. Everything runs locally: no internet, no accounts, no GPU.

Close the game, run the installer (Windows SmartScreen will warn about an unknown publisher: choose "More info", then "Run anyway"), listen for the test phrase, then install the CatChat addon. To remove: Start menu, CatVoice, "Удалить CatVoice".
