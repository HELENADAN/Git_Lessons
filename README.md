Шпаргалка по синхронизации удаленного и локального репозиториев
---
### Как сгенерировать SSH-ключ
1. Проверить наличие  
   $ cd ~ # перешли в домашнюю директорию   
   $ ls -la .ssh/ # вывели список созданных ключей  
2. Генерация ключей  
   $ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" + дважды кликнуть ENTER, если не нужен пароль  
   ls -a ~/.ssh # проверка генерации ключей
### Как связать репозитории
4. Связать ключ и GitHub  
   $ clip < ~/.ssh/id_ed25519.pub # скопировать содержимое ключа в буфер обмена
5. Перейти на GitHub и выбрать пункт Settings-> delayKey -> Title "Personal Key" -> Description ^C -> кликнуть галочку!
6. Проверить правильность ключа ->>>> $ ssh -T git@github.com >>>>> кликнуть yes
7. Связать репозитории  
   $ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git  
   $ git remote -v
### Как синхронизировать данные
9. Синхронизируем данные  
   $ git push -u origin main