---
title: Wydawanie zlecenia produkcyjnego
description: W tej procedurze pokazano sposób zwalniania zlecenia produkcyjnego.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f5c5ca5ebf51d0722318c455e6ca59d3a893793
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831969"
---
# <a name="release-a-production-order"></a>Wydawanie zlecenia produkcyjnego

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]