---
title: Wydawanie zlecenia produkcyjnego
description: W tej procedurze pokazano sposób zwalniania zlecenia produkcyjnego.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2676d9fd98ce7166f011cf55d043c6f48fc4cc93
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836196"
---
# <a name="release-a-production-order"></a>Wydawanie zlecenia produkcyjnego

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób zwalniania zlecenia produkcyjnego. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Jest to czwarta z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.

1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
    * W siatce zaznacz zlecenie produkcyjne, które ma stan Zaplanowane.  
2. W okienku akcji kliknij opcję Zlecenie produkcyjne.
3. Kliknij opcję Zwolnienie.
    * Na tej stronie można potwierdzić zwolnienie wybranego zakresu zleceń produkcyjnych. Aby dodać zamówienia, kliknij przycisk Wybierz.  
    * Krok Zwolnienie wskazuje, kiedy zlecenia produkcyjne jest zwalniane do wydziału produkcji, tak aby operatorzy na produkcji mogli informować o postępie zadań produkcyjnych. Mogą być wystawiane dokumenty produkcyjne zawierające istotne informacje o realizacji zadań. Praca magazynowa dotycząca pobrania surowca jest generowana dla towarów, które są skonfigurowane dla procesu magazynowego.  
4. Kliknij kartę Ogólne.
    * Wybierz raporty o produkcji, które mają być drukowane. Raport Karta zadań drukuje stronę dla każdego zadania zaplanowanego i wymaga zaplanowania zlecenia produkcyjnego na poziomie zadania. Raport zawiera informacje o zaplanowanych godzinach rozpoczęcia i zakończenia, ilości do wyprodukowania oraz o zasobach, które będą realizowały zadanie. Raport Zadanie marszruty zbiera te same informacje na tej samej stronie, ale nie drukuje strony dla każdego zadania. Raport Karta marszruty pokazuje tylko operacje, bez zadań. Dlatego ten raport nie wymaga planowania zadań, ale może być używany podczas planowania zleceń produkcyjnych na poziomie operacji.  
5. Zaznacz pole wyboru Drukowanie karty marszruty.
6. Kliknij przycisk OK.
7. Zamknij stronę.

