---
title: Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze
description: Ta procedura pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a3c635c32a53226da6ce72db86ee7d9d0c17bdb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847094"
---
# <a name="set-up-short-picking-item-reallocation"></a>Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani. Istnieje możliwość używania procesu automatycznej zmiany alokacji, który wykorzystuje dyrektywy lokalizacji do pobierania towarów, jeśli są one dostępne w innej lokalizacji. Alternatywnie w przypadku używania ręcznej zmiany alokacji na urządzeniu przenośnym jest wyświetlana lista lokalizacji z dostępnymi ilościami, dzięki czemu pracownik magazynu może wybrać lokalizację do pobrania zapasów. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="set-up-work-exceptions"></a>Ustaw wyjątki pracy
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Wyjątki dotyczące pracy.
2. Kliknij przycisk Nowy.
    * Istnieje możliwość zdefiniowania kilku wyjątków dotyczących pracy z różnymi zasadami zmiany alokacji towarów, aby umożliwić pracownikowi magazynu wybór towaru na podstawie potrzeb przesyłki, którą akurat przetwarza.  
3. W polu Kod wyjątku pracy wpisz wartość.
    * Zatytułuj wyjątek dotyczący pracy w taki sposób, aby wskazywał, do czego wyjątek jest używany. Na przykład: Ręczne pobieranie w niedomiarze.  
4. Wypełnij pole Opis.
5. W polu Typ wyjątku zaznacz wartość „Pobranie w niedomiarze”.
6. Zaznacz pole wyboru Korekta zapasów.
    * Ta opcja oznacza, że zapasy będą automatycznie korygowane na 0 w lokalizacji pobierania w niedomiarze.  
7. W polu Kod domyślnego typu korekty wprowadź lub wybierz wartość.
    * Na przykład w firmie USMF można wybrać pozycję „Usuń Res Adj Out”.  
8. W polu Zmiana alokacji pozycji wybierz opcję „Ręcznie”.
    * Jeśli wybierzesz opcję Ręcznie lub Automatyczne i ręczne, pracownikowi magazynu trzeba włączyć funkcję stosowania ręcznej zmiany alokacji.  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Konfigurowanie pracownika do używania ręcznej zmiany alokacji
1. Zamknij stronę.
2. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Pracownik.
3. Kliknij przycisk Edytuj.
4. Na liście zaznacz pracownika 24.
5. Rozwiń sekcję Praca.
6. W polu Zezwalaj na ręczną zmianę alokacji pozycji wybierz opcję Tak.

