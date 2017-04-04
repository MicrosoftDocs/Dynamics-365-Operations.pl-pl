---
title: "Podział okresów w arkuszy okresowych"
description: "Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas księgowania arkusza. Podczas tworzenia arkusza należy określić interwał czasowy dla cyklu, taki jak dni lub miesiące. Można także określić liczbę okresów, dla których arkusz będzie księgowany."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261354
ms.assetid: 76c0d7bf-f795-4d42-9a86-a9f36989962c
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 58ab77aea9e66834c516806e5f0cfe3069c94ff3
ms.lasthandoff: 03/31/2017


---

# <a name="split-periods-in-periodic-journals"></a>Podział okresów w arkuszy okresowych

Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas księgowania arkusza. Podczas tworzenia arkusza należy określić interwał czasowy dla cyklu, taki jak dni lub miesiące. Można także określić liczbę okresów, dla których arkusz będzie księgowany.

Aby wielokrotnie pobierać i księgowania wierszy transakcji, można użyć **arkuszy okresowych** strony. Dla osób prawnych w Republice Czeskiej, Estonii, Węgier, Łotwy, Litwy, Polski i Rosji **arkuszy okresowych** strona zostaje przedłużony przez podział okresów funkcji. <!---For more information, see [Create and process a periodic journal](http://ax.help.dynamics.com/en/wiki/create-and-process-a-periodic-journal/).-->

### <a name="example-split-for-periods-in-periodic-journals"></a>Przykład: Podziel na okresy w arkuszach okresowych

Firma ubezpieczeniowa oferuje organizacji zniżki dla przedpłaty polisy ubezpieczeniowej na cały rok. Płatność jest zaksięgowana na koncie aktywów, takich jak przedpłaty na ubezpieczenia. Następnie miesięczny koszt ubezpieczenia jest amortyzowany w ciągu roku przez utworzenie arkusza okresowego, który zawiera kredyt na koncie przedpłat na ubezpieczenia i debet na koncie kosztów ubezpieczenia. W takim przypadku można użyć podziału dla funkcji okresów. Kliknij **Podziel na okresy** znajdującego się w okienku akcji na **arkusza okresowego****linii** strona, a następnie określ następujące pola.

|                       |                                                                                                                                                                                                             |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**             | **Description**                                                                                                                                                                                             |
| **Start date**        | Umożliwia wybór daty dla pierwszego wiersza arkusza okresowego.                                                                                                                                                        |
| **Number of periods** | Wprowadź liczbę okresów, którego Podziel wiersz arkusza. Ta wartość określa liczbę nowych transakcji, które zostaną wygenerowane. Kwota transakcji jest równo dzielona między nowymi transakcjami. |
| **Unit**              | Wybierz jednostkę miary okresu.                                                                                                                                                                  |
| **Interwał okresu**   | Określ interwał między okresów sprawozdawczych.                                                                                                                                                              |

Na przykład aby wygenerować kwartalnych komentarze, należy wprowadzić **4** w **liczba okresów** pól, zaznacz **miesięcy** w **jednostek** i wpisz **3** w **interwał okresu** pole. System generuje cztery wiersze arkusza, każdy dla jednej czwartej wprowadzony, w odstępach 3-miesięczne kwoty wiersza dziennika. Podobna funkcja jest również dostępna dla dziennika głównego. Podczas przeglądania wierszy dziennika głównego, wybierz **Arkusz okresowy**&gt;**zapisywania dziennika**.


