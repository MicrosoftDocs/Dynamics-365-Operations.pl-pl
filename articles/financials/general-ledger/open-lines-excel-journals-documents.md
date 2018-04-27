---
title: "Publikowanie wierszy arkuszy i dokumentów z programu Excel"
description: "W tym temacie wyjaśniono, jak wprowadzać i publikować wiersze arkuszy finansowych z programu Microsoft Excel. Znajdują się tu informacje dotyczące różnych szablonów, których można używać w zależności od typu wprowadzanych transakcji."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: a2da864254efda2621e1b157413a16d251020786
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publikowanie wierszy arkuszy i dokumentów z programu Excel

[!INCLUDE [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak wprowadzać i publikować wiersze arkuszy finansowych z programu Microsoft Excel. Znajdują się tu informacje dotyczące różnych szablonów, których można używać w zależności od typu wprowadzanych transakcji.

Użytkownicy mogą wprowadzać i publikować wiersze arkuszy finansowych z programu Microsoft Excel. Gdy użytkownik utworzy arkusz, przycisk **Otwórz wiersze w programie Excel** powoduje wyświetlanie dostępnych szablonów. Szablony są przeznaczone do obsługi określonych scenariuszy, jednak nie każda kombinacja typu konta jest obsługiwana w arkuszu. W poniższej tabeli przedstawiono dostępne szablony i obsługiwane przez nie typy kont.

|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Szablon**             | **Obsługiwane typy kont**                                                                                             | **Jak uzyskać dostęp do szablonu**                                                          |
| Wiersze arkusza księgi     | Konto: Konto przeciwstawne Księga, Odbiorca, Dostawca, Bank: Międzyfirmowe Księga, Odbiorca, Dostawca, Bank jest obsługiwane.       | Arkusze finansowe                                                                         |
| Rejestr faktur         | Konto: Konto przeciwstawne Dostawca: Międzyfirmowe Księga nie jest obsługiwane.                                                    | Rejestr faktur rozrachunków z dostawcami                                                                     |
| Arkusz faktur          | Konta: Konto przeciwstawne Dostawca: Międzyfirmowe Księga jest obsługiwane.                                                      | Arkusz faktur rozrachunków z dostawcami                                                                      |
| Faktura dostawcy           |                                                                                                                         | Faktura dostawcy                                                                          |
| Arkusz faktur dla odbiorcy | Konto: Konto przeciwstawne Odbiorca: Międzyfirmowe Księga jest obsługiwane.                                                     | Arkusze finansowe                                                                         |
| Faktura niezależna        |                                                                                                                         | Na stronie **Faktura niezależna** kliknij przycisk **Otwórz w programie Excel** (ikona pakietu Microsoft Office). |
| Arkusz środków trwałych     | Składnik aktywów do księgi, bank, odbiorca lub dostawca. Międzyfirmowe nie jest obsługiwane.                                               | Arkusz środków trwałych                                                                     |
| Arkusz płatności dostawców   | Konto: Konto przeciwstawne Dostawca: Międzyfirmowe Księga, Bank jest obsługiwane.                                                 | Arkusz płatności dostawców                                                                  |
| Arkusz płatności odbiorcy | Konto: Konto przeciwstawne Odbiorca: Międzyfirmowe Księga, Bank jest obsługiwane.                                               | Arkusz płatności odbiorcy                                                                |
| Arkusz wydatków w ramach projektu  | Konto: Konto przeciwstawne Projekt, Księga, Odbiorca, Dostawca: Międzyfirmowe Projekt, Księga, Odbiorca, Dostawca jest obsługiwane. | Arkusz finansowy wydatków (w obszarze Zarządzanie projektami i ich księgowanie)                       |

Podczas publikowania wierszy są one weryfikowane w celu uzyskania pewności, że są zgodne z regułami skonfigurowanymi w arkuszach finansowych. Po opublikowaniu wierszy użytkownicy mogą edytować i księgować załączniki z poziomu programu Microsoft Dynamics 365 for Finance and Operations. 

Aby dodać wymiary finansowe do szablonu, trzeba wprowadzić dodatkowe zmiany. Aby uzyskać więcej informacji, zobacz [Dodawanie wymiarów do szablonu programu Microsoft Excel](../../dev-itpro/financial/add-dimensions-excel-templates.md). Po dodaniu wymiarów do jednostki są one dostępne w projektancie programu Excel i mogą być dodawane do szablonu.






