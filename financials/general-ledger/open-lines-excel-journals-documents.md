---
title: "Publikowanie dokumentów z programu Excel i wierszy arkusza"
description: "W tym temacie wyjaśniono, jak należy wprowadzić i publikować linią dla arkuszy finansowych z programu Microsoft Excel. Zawiera informacje dotyczące różnych szablonów, których można użyć, w zależności od typu transakcji, które wprowadzasz."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 087339cb3002b42bcb985c2ccfc2d97c752a817c
ms.lasthandoff: 03/31/2017


---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publikowanie dokumentów z programu Excel i wierszy arkusza

W tym temacie wyjaśniono, jak należy wprowadzić i publikować linią dla arkuszy finansowych z programu Microsoft Excel. Zawiera informacje dotyczące różnych szablonów, których można użyć, w zależności od typu transakcji, które wprowadzasz.

Użytkownicy mogą wprowadzać i publikować linią dla arkuszy finansowych z programu Microsoft Excel. Gdy użytkownik utworzy dziennika, **otwarte wiersze w programie Excel** przycisk Wyświetla szablony, które są dostępne. Szablony są przeznaczone do obsługi określonych scenariuszy, jednak nie każda kombinacja typu konta jest obsługiwana w dzienniku. W poniższej tabeli przedstawiono typy kont, które wspierają i szablony, które są dostępne.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Template**             | **Typy kont obsługiwanych**                                                                                             | **Jak uzyskać dostęp do szablonu**                                                          |
| Wiersze arkusza księgi     | Konto: Księgi, odbiorcy, dostawcy, konta bankowego przesunięcie: księgi, odbiorcy, dostawcy, Bank międzyfirmowe jest obsługiwany.       | Arkusze finansowe                                                                         |
| Rejestr faktur         | Konto: Konto przeciwstawne dostawcy: międzyfirmowe księgi nie jest obsługiwany.                                                    | Rejestr faktur AP                                                                     |
| Arkusz faktur          | Konta: Konto dostawcy przesunięcie: księgi międzyfirmowe jest obsługiwany.                                                      | Arkusz faktur rozrachunków z dostawcami                                                                      |
| Faktura dostawcy           |                                                                                                                         | Faktura dostawcy                                                                          |
| Arkusz faktur dla odbiorcy | Konto: Konto odbiorcy przesunięcie: księgi międzyfirmowe jest obsługiwany.                                                     | Arkusze finansowe                                                                         |
| Faktura niezależna        |                                                                                                                         | Na **faktury niezależnej** kliknij przycisk **otwarty w programie Excel** (ikona Microsoft Office). |
| Arkusz środków trwałych     | Trwały do księgi, bank, odbiorca lub Dostawca. Międzyfirmowe nie jest obsługiwany.                                               | Arkusz środków trwałych                                                                     |
| Arkusz płatności dostawców   | Konto: Konto przeciwstawne dostawcy: księgi, Bank międzyfirmowe jest obsługiwany.                                                 | Arkusz płatności dostawców                                                                  |
| Arkusz płatności odbiorcy | Konto: Konto odbiorcy przesunięcie: księgi, Bank międzyfirmowe jest obsługiwany.                                               | Arkusz płatności odbiorcy                                                                |
| Arkusz wydatków w ramach projektu  | Konta: Projekt, księgi, odbiorcy, konto przeciwstawne dostawcy: projekt, księgi, odbiorcy, dostawcy międzyfirmowego jest obsługiwany. | Arkusz finansowy wydatków (w obszarze Zarządzanie projektami i ich księgowanie)                       |

Jeśli wiersze są opublikowane, mają oni prawo upewnij się, że są one zgodne z regułami, które są ustawione w arkuszach finansowych. Po opublikowaniu wiersze użytkowników można edytować i zaksięgować załączniki z Microsoft Dynamics 365 dla operacji. 

Aby dodać wymiarów finansowych do szablonu, są wymagane dodatkowe zmiany. Aby uzyskać dodatkowe informacje, zobacz [dodać wymiary do szablonu programu Microsoft Excel](\dev-itpro\financial-dimensions\add-dimensions-excel-templates). Po wymiary są dodawane do podmiotu, są dostępne w projektancie programu Excel i mogą być dodawane do szablonu.




