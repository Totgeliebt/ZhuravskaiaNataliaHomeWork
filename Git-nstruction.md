# Работа с Git
## 1. Проверка наличия установленного Git
В терминале выполнить команду `git version`.
Если Git утсановлен, появится сообщение с информацие о версии программы. Иначе будет сообщение об ошибке.
## 2. Установка Git
Загружаем последнюю версию Git с сайта https://git-scm.com/downloads.
Устанавливаем с настройками по умолчанию.
## 3.Настройка Git
При первом использовании Git необходимо представиться. Для этого нужно ввести в терминале 2 команды: 
```
git config --global user.name «Ваше имя»
git config --global user.email ваша "почта@example.com"
```
 ## 4. Инициализация репозитория

Получить репозиторий можно двумя способами. 

1. Можно создать папку на компьютере, открыть ее в редакторе кода, например в VS Code, и набрать команду `git init`  в терминале. 
2. А можно создать папку через терминал, введя команду `md 'Название папки'`, и затем `git init`.

 ## 5. Проверить текущее состояние репозитория
  
  Узнать о состоянии репозитория можно с помощью команды `git status`. После выполнения этой команды в терминале, мы получим сообщения о том, был ли изменен текущий статус, отслеживаются ли изменения, зафиксированы ли они. Также мы получим некоторые подсказы от Git, что мы можем сделать дальше. 

   ## 6. Отследить изменения

   Чтобы уведомить Git, что мы хотим отслеживать изменения в текущем файле, мы должны набрать команду `git add "Название файла"`. Мы также можем отслеживать изменения всех файлов, которые были изменены с помощью команды `git add .`

## 7. Зафиксировать изменения 
Теперь пришло время сохранить, или зафиксировать, изменения, которые мы внесли в наш файл и уже отслеживаем. 
Для этого введем в терминале `git commit -m" "`, где в кавычках опишем,какие изменения мы вносили, чтобы другие разработчики или даже мы сами спустя длительное время смогли с легкостью ориентироваться во множесте всех изменений. 

**ВАЖНО!**
```
Зафиксировать неотслеживаемые изменения не получится, поэтому не забывайте выполнять комманды в правильном порядке: сначала `git add "Название файла"`, затем `git commit -m" "`. 
 ```
 ***Кстати***

*Есть команда, совмещающая в себе отслеживание и фиксирование сразу - `git commit -a -m" "`. Но обратите внимание на одну особенность этой команды  - она отслеживает и фиксирует ВСЕ измененнные файлы проекта, не только текущий.*

## 8.Журнал изменений

Чтобы увидеть все произведенные коммиты, введите `git log` или `git log --oneline` (для оптимизированного краткого списка всех коммитов). Каждому коммиту присвоен особый число-буквенный код - своеобразное "имя" коммита, он пригодится нам для того, чтобы перемещаться между коммитами. Чтобы вернуться к работе в командной строке нажмите клавишу `q`.

## 9. Перемещение между коммитами

Теперь мы можем выбрать коммит, к которому мы хотим обратиться, то есть вернуться к файлу в определенном его состоянии. Здесь нам как раз пригождаются краткие описания, которые мы добавляли, и число-буквенные "имена" коммитов. Введите команду `git checkout Имя коммита` , где вместо Имя коммита подставьте первые 4 символа "имени". Обратите внимание, как сейчас выглядит ваш файл -  какие изменени сохранены, а какие отсутствуют. 

Чтобы продолжить работу с последнего места сохранения, необходимо вернуться к свежайшему коммиту с помощью команды `git checkout master`.

## 10. Просмотреть изменения.

Мы можем увидеть какие именно изменения были внесены в последний коммит введя в терменале `git diff`. В сообщении то, что было добавлено, будет подсвечено зеленым цветом, а что удалено - красным. 

***Кстати*** 
```
Людям свойственно ошибаться и многие ошибки можно довольно легко исправить. Если вы опечатались или некорректно заполнили информацию в сообщении о последнем коммите, воспользуйтесь командой git commit --amend -m" ", и в новом сообщении введите корректную версию.
```

### Если вы хотите узнать больше о Git  и как в нем работать, посетите официальный сайт https://git-scm.com/ или скачайте руководство по работе с Git по этой ссылке https://git-scm.com/book/en/v2


# Работа с ветками

Для разработки в команде работа с ветками крайне важна. Ветка - это своего рода черновик. Работа на разных ветках это очень удобно: разработал фичу, обсудил с коллегами, получил добро и добавил в проект. 
## 1. Создаем новую ветку
Наберите в терминале команду `git branch имя ветки` для создания новой ветки и затем  `git checkout имя ветки` , чтобы на нее перейти. 
Готово! Можете начинать работу!

## 2. Удаление веток
Кроме добавления, мы также можем удалять ненужные ветки с помощью команды `git branch -d имя ветки`

## 3. Слияние веток
Чтобы добавить изменения, выполненные вами на другой ветке в ветку **master** необходимо выполнить команду `git merge имя ветки`. 

**ВАЖНО!**
```
Нужно находиться на той ветке, в которую вы хотите добаить побочную. Поэтому удостоверьтесь, что вы находитесь на ветке master - наберите команду `git branch`.
```
## 4. Дополнительные команды

Команда `clear` очищает терминал, делается это для удобства работы.


# Работа с удаленным репозиторием Github

## 1. Начало работы
Для того, чтобы начать работу с удаленным репозиторием, зарегестрируйтесь на сайте https://github.com/.
 
 Заполните свой профиль - напишите пару слов о себе и добавьте фото. Ваш репозиторий - это ваша визитная карточка как разработчика. Удостоверьтесь, что вы презентуете себя подобающим образом.

 ## 2. Создать репозиторий
 Создать новый репозиторий можно несколькими способами.
 
 1. В правом верхнем углу в меню пользователя вы можете увидеть иконку "+" - нажмите ее, выберите `New repository` 
 2. Либо в меню наверху по центру выберете вкладку `Repositories` и нажмите зеленую кнопку `New`.
Вам нужно придумать имя вашему репозиторию и выбрать уровень приватности - **private** или **public**. Нажмите кнопку в самом низу `Create repository` и следуйте инструкциям на странице.

## 3.Клонировать репозиторий

Если Вы хотите внести свои предложения в чей-то проект(репозиторий), вы можете "скопировать" чужой удаленный репозиторий себе в аккаунт, затем открыть его локально и внести необходимые изменения. Для этого перейдите на страницу интересующего вас репозитория и нажмите кнопку `fork`, затем откройте среду разработки, закройте все открытые папки и вы увидите в меню слева `clone repository`. Появится выпадающее меню, где нужно нажать на `clone from github` и далее выбрать место на вашем компьютере, куда вы хотите разместить данный репозиторий. 

***Кстати*** 
```
Считается хорошей практикой вносить все изменения в побочную ветку, не в **main**.
```

## 4. Создаем pull request

Чтобы владелец удаленного репозитория, в который вы хотите внести свои дополнения, смог увидеть и оценить ваш бесценный вклад, нужно создать `pull request`. Зафиксируйте изменения уже известным вам способом и сделайте git push. Откройте страницу сайта github и обновите страницу. Вы можете заметить, что над вашим репозиторием появилась строчка о новом коммите. Нажмите на нее и вы перейдете на страницу создания `pull request` - нажмите `new pull request` и - `create pull request`.

## 5. Обноовить состояние локального репозитория

Представьте, что вы работаете в команде и ваши коллеги добавили какие-то новые фичи в ваш проект, чтобы эти изменения появились у вас в локальном репозитории, нужно выполнить команду `git pull`.