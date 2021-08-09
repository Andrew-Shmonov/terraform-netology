# terraform-netology

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.  
 `git show aefea ` 
 aefead2207ef7e2aa5dc81a34aedf0cad4c32545

2. Какому тегу соответствует коммит 85024d3?
 `git show 85024d3 ` 
 85024d3100126de36331c6982bfaac02cdab9e76 (tag: v0.12.23)  

3. Сколько родителей у коммита b8d720? Напишите их хеши.  
 Лично я смотрел в графах гитлаба, но можно `git show b8d720^`  
 Два родителя:  
 56cd7859e05c36c06b56d013b55a252d0bb7e158  
 9ea88f22fc6269854151c571162c5bcf958bee2b

4. Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.  
 Опять же использовал графы гитлаба и поиск. Чтобы просто посмотреть, очень удобно). Можно командой в консоли `git log v0.12.23..v0.12.24`
 v0.12.23  
    ↓  
    225466bc3e5f35baa5d07197bbc079345b77525e  
    Cleanup after v0.12.23 release  
    ↓  
    dd01a35078f040ca984cdd349f18d0b67e486c35  
    Update CHANGELOG.md  
    ↓  
    4b6d06cc5dcb78af637bbb19c198faff37a066ed  
    Update CHANGELOG.md  
    ↓  
    d5f9411f5108260320064349b757f55c09bc4b80  
    command: Fix bug when using terraform login on Windows  
    ↓  
    06275647e2b53d97d4f0a19a0fec11f6d69820b5  
    Update CHANGELOG.md  
    ↓  
    5c619ca1baf2e21a155fcdb4c264cc9e24a2a353  
    website: Remove links to the getting started guide's old location  
    ↓  
    6ae64e247b332925b872447e9ce869657281c2bf  
    registry: Fix panic when server is unreachable  
    ↓  
    3f235065b9347a758efadc92295b540ee0a5e26e  
    Update CHANGELOG.md  
    ↓  
    b14b74c4939dcab573326f4e3ee2a62e23e12f89  
    [Website] vmc provider links  
    ↓  
 v0.12.24  

5. Найдите коммит, в котором была создана функция func providerSource. Её определение в коде выглядит так: func providerSource(...) (вместо троеточия перечислены аргументы).  
 `git log -S “func providerSource(” --pretty=format:"%h, %an, %ad, %s"`
 8c928e835

6. Найдите все коммиты, в которых была изменена функция globalPluginDirs.
 Поиском нашёл, в каком файл находится функция, потом `git log -L :globalPluginDirs(:plugins.go`
 78b122055  
 52dbf9483  
 41ab0aef7  
 66ebff90c  
 8364383c3 (добавлена)

7. Кто автор функции synchronizedWriters? 
 `git log -S "synchronizedWriters(" --pretty=format:"%h, %an, %ad, %s"`  и можно посмотреть по времени коммита 
 Martin Atkins
