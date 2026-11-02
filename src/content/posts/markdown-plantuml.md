---
title: Markdown PlantUML диаграм
published: 1970-01-01
description: Firefly дахь PlantUML плагины дүрслэл, сэдэв солих болон харилцан үйлчлэлийн чадварыг шалгах жишээ өгүүлэл.
tags: [PlantUML, Firefly, Markdown]
category: Өгүүллийн жишээ
slug: markdown-plantuml
series: "Firefly функцын жишээ2"
seriesOrder: 4
---

## Markdown дахь PlantUML диаграмын гарын авлага

PlantUML нь цэвэр текстээр диаграм дүрслэх хэрэгсэл юм. Та зөвхөн бүтэцтэй синтакс бичихэд дарааллын диаграм, класс диаграм, хэрэглээний тохиолдлын диаграм, үйл ажиллагааны диаграм зэрэг нийтлэг инженерийн диаграмыг үүсгэх боломжтой.

Энэ нь техникийн блог болон төслийн баримт бичигт бичихэд онцгой тохиромжтой:

- Диаграм болон үндсэн хэсэг хамтдаа хувилбарт удирдагдах тул хамтын ажиллагаа, хяналт хялбар болно
- Диаграмыг засахдаа зөвхөн текстийг засах хангалттай тул байнгын давталтад тохиромжтой
- Markdown-той оёж нэгдэх тул баримт бичгийн нэгдмэл байдлыг хадгална

Firefly дээр `plantuml` кодын блок нь бүтээх үе шатанд кодлогдож, серверийн SVG хаяг үүсгэнэ; хуудасны тал нь гэрэл/харанхуй сэдвээр зургийн эх сурвалжийг автоматаар сольж, томруулах, чирэх, бүрэн дэлгэцийн харилцан үйлчлэлийг дэмжинэ.

Хурдан эхлэхийг хүсвэл энэ хамгийн бага загварыг санаж болно:

```plantuml
@startuml
Alice -> Bob: Hello
Bob --> Alice: Hi
@enduml
```

## Үйл ажиллагааны диаграмын жишээ

```plantuml
@startuml
start
:Хэрэглэгч захиалга илгээх;
if (Нөөц хангалттай?) then (Тийм)
	:Нөөц блоклох;
	:Төлбөрийн баримт үүсгэх;
	if (Төлбөр амжилттай?) then (Тийм)
		:Хүргэлтийн баримт үүсгэх;
		:Агуулах руу цуглуулах мэдэгдэл өгөх;
	else (Үгүй)
		:Захиалга цуцлах;
		:Нөөц чөлөөлөх;
	endif
else (Үгүй)
	:Нөөц дууссан гэж мэдэгдэх;
endif
stop
@enduml
```

## Төлөвийн диаграмын жишээ

```plantuml
@startuml
[*] --> Ноорог

Ноорог --> Хянагдах : Илгээх
Хянагдах --> Ноорог : Татгалзах
Хянагдах --> Нийтлэгдсэн : Хяналт давсан
Нийтлэгдсэн --> Архивласан : Хугацаа дуусч архивлах
Нийтлэгдсэн --> Ноорог : Буцаан татах

state Нийтлэгдсэн {
	[*] --> Харагдах
	Харагдах --> Нуугдсан : Гараар нуух
	Нуугдсан --> Харагдах : Дахин харуулах
}

Архивласан --> [*]
@enduml
```

## Хэрэглээний тохиолдлын диаграмын жишээ

```plantuml
@startuml
left to right direction
actor Зочин
actor Хэрэглэгч
actor Админ

rectangle Блог систем {
	usecase "Өгүүлэл үзэх" as UC1
	usecase "Агуулга хайх" as UC2
	usecase "Сэтгэгдэл бичих" as UC3
	usecase "Таалагдах хадгалах" as UC4
	usecase "Сэтгэгдэл хянах" as UC5
	usecase "Өгүүлэл нийтлэх" as UC6
}

Зочин --> UC1
Зочин --> UC2
Хэрэглэгч --> UC1
Хэрэглэгч --> UC2
Хэрэглэгч --> UC3
Хэрэглэгч --> UC4
Админ --> UC5
Админ --> UC6
@enduml
```

## Компонентын диаграмын жишээ

```plantuml
@startuml
package "Firefly Site" {
	[Astro App] as App
	[Markdown Parser] as Parser
	[PlantUML Encoder] as Encoder
	[Theme Switcher] as Theme
	[Search Indexer] as Search
}

cloud "PlantUML Server" as PU
database "Content Store" as Content

App --> Parser : parse markdown
Parser --> Encoder : encode plantuml blocks
Encoder --> PU : request svg
App --> Theme : switch dark/light src
App --> Search : build page index
Parser --> Content : read posts
@enduml
```

## Байршуулалтын диаграмын жишээ

```plantuml
@startuml
node "User Device" {
	artifact "Browser"
}

node "CDN / Edge" {
	artifact "Static Assets"
}

node "Cloudflare Worker" {
	artifact "SSR Handler"
}

node "PlantUML Service" {
	artifact "SVG Renderer"
}

database "Object Storage" {
	artifact "Markdown Content"
}

"Browser" --> "Static Assets" : GET js/css/img
"Browser" --> "SSR Handler" : request page
"SSR Handler" --> "Markdown Content" : read post
"Browser" --> "SVG Renderer" : fetch diagram svg
@enduml
```

## ER диаграмын жишээ

```plantuml
@startuml
entity User {
	*id : uuid <<PK>>
	--
	username : varchar
	email : varchar
	created_at : datetime
}

entity Post {
	*id : uuid <<PK>>
	--
	author_id : uuid <<FK>>
	title : varchar
	content : text
	published_at : datetime
}

entity Comment {
	*id : uuid <<PK>>
	--
	post_id : uuid <<FK>>
	user_id : uuid <<FK>>
	body : text
	created_at : datetime
}

User ||--o{ Post : writes
User ||--o{ Comment : creates
Post ||--o{ Comment : has
@enduml
```

## Дарааллын диаграмын жишээ (нэвтрэх болон токен шинэчлэх)

```plantuml
@startuml
autonumber
actor User as Хэрэглэгч
participant Web as Вэб хуудас
participant API as Гарцын API
participant Auth as Баталгаажуулалтын сервис
database Redis as Сессийн кэш

Хэрэглэгч -> Вэб хуудас : Данс, нууц үг оруулан илгээх
Вэб хуудас -> Гарцын API : POST /login
Гарцын API -> Баталгаажуулалтын сервис : Бүртгэл шалгах
Баталгаажуулалтын сервис -> Сессийн кэш : refresh_token бичих
Баталгаажуулалтын сервис --> Гарцын API : access_token + refresh_token
Гарцын API --> Вэб хуудас : 200 нэвтрэлт амжилттай

... access_token хугацаа дуусах ...

Вэб хуудас -> Гарцын API : POST /refresh
Гарцын API -> Баталгаажуулалтын сервис : refresh_token шалгах
Баталгаажуулалтын сервис -> Сессийн кэш : refresh_token солих
Баталгаажуулалтын сервис --> Гарцын API : Шинэ access_token
Гарцын API --> Вэб хуудас : 200 шинэ токен
@enduml
```

## C4 хэв маягийн контейнер диаграмын жишээ

```plantuml
@startuml
!includeurl https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

Person(user, "Блогын зочин", "Өгүүлэл унших болон агуулга хайх")

System_Boundary(system, "Firefly Blog") {
	Container(web, "Web App", "Astro + Svelte", "Хуудас дүрслэх болон харилцан үйлчлэл")
	Container(worker, "SSR Worker", "Cloudflare Workers", "Сервер талын дүрслэлийн хүсэлт боловсруулах")
	ContainerDb(content, "Content Store", "Markdown / Object Storage", "Өгүүлэл болон нөөцийн мета өгөгдөл хадгалах")
	Container(search, "Search Index", "Pagefind", "Бүрэн текст хайлт үзүүлэх")
}

System_Ext(plantuml, "PlantUML Server", "SVG диаграм үүсгэх")

Rel(user, web, "Зочлох", "HTTPS")
Rel(web, worker, "SSR хуудас хүсэх", "HTTPS")
Rel(worker, content, "Өгүүлэл унших")
Rel(web, search, "Түлхүүр үг хайх")
Rel(web, plantuml, "Диаграмын SVG хүсэх")

LAYOUT_LEFT_RIGHT()
@enduml
```
