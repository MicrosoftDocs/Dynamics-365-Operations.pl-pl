---
title: Klucze konfiguracji a jednostki danych
description: "W tym temacie opisano związek między kluczami konfiguracji a jednostkami danych w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 25341
ms.assetid: 8e214c95-616b-4ee1-b5a4-fa5ce5147f2c
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: af7f9a373496eee4df354d5dd9e5a25c51317c43
ms.openlocfilehash: f9ea932b48d57baad4b4ab66069191ebd7cbbd6c
ms.contentlocale: pl-pl
ms.lasthandoff: 02/27/2018

---

# <a name="configuration-keys-and-data-entities"></a>Klucze konfiguracji a jednostki danych

[!include[banner](../includes/banner.md)]

Zanim zaczniesz używać jednostek danych do importowania lub eksportowania danych, zalecamy ustalenie wpływu kluczy konfiguracji na jednostki danych, których zamierzasz używać. 

Aby dowiedzieć się więcej o kluczach konfiguracji w programie Finance and Operations, zobacz [Raport kodów licencji i kluczy konfiguracji](../sysadmin/license-codes-configuration-keys-report.md).

### <a name="configuration-key-assignments"></a>Przypisania kluczy konfiguracji
Klucze konfiguracji można przypisywać do jednego lub wszystkich poniższych artefaktów.
-   Jednostki danych
-   Tabele używane jako źródła danych
-   Pola tabeli
-   Pola jednostki danych

W tabeli poniżej podsumowano, jak wartości kluczy konfiguracji w różnych artefaktach stanowiących bazę obiektu zmieniają oczekiwane zachowanie obiektu.

| Ustawienie klucza konfiguracji w jednostce danych | Ustawienie klucza konfiguracji w tabeli | Ustawienie klucza konfiguracji w polu tabeli | Klucz konfiguracji w polu jednostki danych | Oczekiwane zachowanie                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------|-----------------------------|-----------------------------------|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wyłączony                          | Nie oceniane               | Nie oceniane                     | Nie oceniane                   | Jeśli klucz konfiguracji jednostki danych jest wyłączony, jednostka danych nie będzie działać. Nie ma znaczenia, czy klucze konfiguracji w źródłowych tabelach i polach są włączone, czy wyłączone.                                                                                                                                                                                                                                                                                                                                          |
| Włączone                           | Wyłączony                    | Nie oceniane                     | Nie oceniane                   | Jeśli klucz konfiguracji jednostki danych jest włączony, struktura zarządzania danymi sprawdza klucz konfiguracji w każdej tabeli źródłowej. Jeśli klucz konfiguracji tabeli jest wyłączony, tabela nie będzie dostępna do użytku w jednostce danych. Jeśli klucz konfiguracji tabeli jest wyłączony, ustawienia kluczy konfiguracji tabeli i jednostki danych nie są oceniane. Jeżeli tabela podstawowa w jednostce ma wyłączony klucz konfiguracji, system będzie działał tak, jakby został wyłączony klucz konfiguracji jednostki. |
| Włączone                           | Włączone                     | Wyłączony                          | Nie oceniane                   | Jeśli włączono klucz konfiguracji w jednostce danych, a są włączone klucze konfiguracji źródłowych tabel, struktura zarządzania danymi będzie sprawdzać klucz konfiguracji w polach w tabelach. Jeśli klucz konfiguracji pola jest wyłączony, to pole nie będzie dostępne do użytku w jednostce danych, nawet gdy odnośne pole jednostki danych ma włączony klucz konfiguracji.                                                                                                                                   |
| Włączone                           | Włączone                     | Włączone                           | Wyłączony                        | Jeśli klucz konfiguracji jest włączony na wszystkich innych poziomach, ale klucz konfiguracji pola jednostki nie jest włączony, to pole nie będzie dostępne do użytku w jednostki danych.                                                                                                                                                                                                                                                                                                                                                                          |

> [!NOTE]
> Jeśli jednostka ma inną jednostkę jako źródło danych, powyższa semantyka jest stosowana w sposób cykliczny.

### <a name="entity-list-refresh"></a>Odświeżanie listy jednostek
Po odświeżeniu listy jednostek struktura zarządzania danymi tworzy metadane klucza konfiguracji do użytku w czasie wykonywania. Te metadane są generowane przy użyciu logiki opisanej powyżej. Stanowczo zalecamy poczekać na zakończenie odświeżania listy jednostek, zanim zaczniesz używać zadań i jednostek strukturze zarządzania danymi. Jeśli nie zaczekasz, metadane kluczy konfiguracji mogą być nieaktualne i w efekcie powodować nieoczekiwane rezultaty. Podczas odświeżania listy jednostek jest wyświetlany następujący komunikat na stronie listy jednostek.

![Odświeżanie listy jednostek](./media/Entity_refresh_list.png)

### <a name="data-entity-list-page"></a>Strona listy jednostek danych
Strona listy jednostek danych w obszarze roboczym Zarządzanie danymi pokazuje ustawienia kluczy konfiguracji jednostek. Rozpoczęcie od tej strony pozwoli zrozumieć wpływ kluczy konfiguracji na jednostkę danych.
Te informacje są wyświetlane przy użyciu metadanych wygenerowanych podczas odświeżania jednostki. Kolumna klucza konfiguracji zawiera nazwę klucza konfiguracji skojarzonego z jednostką danych. Pusta kolumna oznacza, że nie istnieje klucz konfiguracji skojarzony z jednostką danych. W kolumnie stanu klucza konfiguracji jest pokazywany stan klucza konfiguracji. Jeśli znajduje się tam znacznik wyboru, oznacza to, że klucz jest włączony. Puste pole oznacza, że klucz jest wyłączony albo nie ma żadnego skojarzonego klucza.

![Strona listy jednostek](./media/Data_entity_list_page.png)

### <a name="target-fields"></a>Pola docelowe
Następnym krokiem jest przejście do bardziej szczegółowych poziomów jednostki danych w celu obejrzenia wpływu kluczy konfiguracji na tabele i pola. Formularz pól docelowych dla jednostki danych zawiera klucz konfiguracji oraz informacje o stanie kluczy w powiązanych tabelach i polach w jednostce danych.  Jeśli sama jednostka danych ma wyłączony klucz konfiguracji, jest wyświetlany komunikat ostrzegawczy informujący, że tabele i pola w formularzu pól docelowych dla tej jednostki nie będą w ogóle dostępne, niezależnie od stanów ich kluczy konfiguracji.

![Pola docelowe](./media/Target_fields_1.png)

### <a name="child-entities"></a>Jednostki podrzędne 
Niektóre jednostki używają innych jednostek jako źródeł danych lub są złożonymi jednostkami danych. Informacje o kluczach konfiguracji takich jednostek są wyświetlane w formularzu Jednostki podrzędne. Tego formularza używa się w sposób podobny do używania strony listy jednostek opisanej powyżej. Formularz pól docelowych jednostki podrzędnej również zachowuje się w sposób opisany powyżej.

![Pola docelowe](./media/Target_fields_2.png)

### <a name="using-data-entities"></a>Używanie jednostek danych
Po rozpoznaniu całkowitego wpływu kluczy konfiguracji na jednostki danych, których chcesz używać, można rozpocząć korzystanie z jednostek danych, dodając je do projektów danych. 

### <a name="run-time-validations-for-configuration-keys"></a>Sprawdzanie kluczy konfiguracji podczas wykonywania
Sprawdzanie podczas wykonywania jest uruchamiane przy użyciu metadanych kluczy konfiguracji wygenerowanych podczas odświeżania listy jednostek w następujących przypadkach.

-   Podczas dodawania jednostki danych do zadania

-   Gdy użytkownik klika przycisk „Sprawdź poprawność” na liście jednostek

-   Gdy użytkownik ładuje pakiet danych do projektu danych

-   Gdy użytkownik ładuje szablon do projektu danych

-   Podczas ładowania istniejącego projektu danych

-   Podczas ładowania szablonu do projektu danych

-   Przed wykonaniem zadania eksportu/importu (wsadowego, niewsadowego, cyklicznego, przy użyciu protokołu Odata)

-   Gdy użytkownik generuje mapowanie

-   Gdy użytkownik mapuje pola w interfejsie użytkownika mapowania

-   Gdy użytkownik dodaje tylko pola, które można importować


### <a name="managing-configuration-key-changes"></a>Zarządzanie zmianami w kluczach konfiguracji
Po każdym zaktualizowaniu kluczy konfiguracji na poziomie jednostki, tabeli lub pola należy odświeżyć listę jednostek w strukturze zarządzania danymi. Daje to pewność, że struktura pobierze najnowsze ustawienia kluczy konfiguracji. Do czasu odświeżenia listy jednostek będzie wyświetlane następujące ostrzeżenie na stronie listy jednostek. Aktualizacje kluczy konfiguracji zaczną obowiązywać natychmiast po odświeżeniu listy jednostek. Po wprowadzaniu modyfikacji kluczy konfiguracji zalecamy sprawdzenie poprawności istniejących projektów danych i zadań, aby mieć pewność, że działają zgodnie z oczekiwaniami.

![Pola docelowe](./media/Target_fields_3.png)


