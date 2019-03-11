---
title: Zasady podziału księgowań
description: Ten artykuł zawiera informacje o zasadach podziału księgowań oraz opis opcji dostępnych do przetwarzania tych zasad. Zasady podziału księgowań są używane do przypisywania kwot pieniężnych z dokumentu źródłowego do określonych kont księgowych.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3ba6a581efe8353ccb9e02606db58d18550d71af
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "320473"
---
# <a name="accounting-distributions"></a>Zasady podziału księgowań

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o zasadach podziału księgowań oraz opis opcji dostępnych do przetwarzania tych zasad. Zasady podziału księgowań są używane do przypisywania kwot pieniężnych z dokumentu źródłowego do określonych kont księgowych. 

Zasady podziału księgowań są funkcją na poziomie programu, która jest używana i rozszerzona przez każdy dokument źródłowy, taki jak zamówienie zakupu, faktura od dostawcy, raport z wydatków i faktura niezależna. Domyślnie generowane są domyślne zasady podziału księgowań dla każdego wiersza dokumentu źródłowego i kwoty pieniężnej i jest włączony do modyfikacji warunkowo. 

> [!Note] 
> Niektóre dokumenty obsługują również kwoty pieniężne nagłówka dokumentu, takie jak opłaty dla zamówień i faktur. 

Ogólne funkcje zasad podziału księgowań oferują następujące opcje przetwarzania zasad podziału księgowań:

-   **Rozdziel kwoty** — Wyświetlanie i modyfikowanie zasad podziału księgowań dla pojedynczego nagłówka lub wiersza dokumentu i wszystkich wierszy podrzędnych, takich jak podatki lub opłaty.
    -   Dla najwyższych zasad podziału księgowań (nadrzędne) konto nadrzędne i wymiary finansowe można edytować bezpośrednio w ramach kontroli zapisu podzielonej na segmenty w siatce. Typowym przykładem takiej zasady podziału księgowań jest cena rozszerzona.
    -   Zasady podziału księgowań są oparte na walucie terminu dla dokumentu. Zazwyczaj jest to waluta transakcji. Kwoty w walucie księgowania i raportowania są generowane w ramach księgowania księgi podrzędnej.
    -   Zasady podziału pokazują datę księgowania i zdarzenie księgowania. Zazwyczaj zdarzenie księgowe jest ustawione na **Brak**, aż do zaksięgowania dokumentu lub umieszczeniu go w arkuszu. W tym momencie zdarzenie księgowe staje się **Oryginałem**. Zaksięgowane zasady podziału można modyfikować.
    -   Przycisk **Podziel** może być włączony dla nadrzędnych zasad podziału. Za pomocą przycisku **Podziel** można wygenerować nowe zasady podziału księgowań i podział może być oparty na wartości procentowej, kwocie lub ilości.
    -   Przycisk **Podziel równo** może być używany w połączeniu z przyciskiem **Podziel**, aby automatycznie alokować kwotę równo między wszystkie zasady podziału księgowań.
    -   Przycisk **Resetuj** może być włączony dla nadrzędnych zasad podziału księgowań, gdy istnieje więcej niż jedna zasada. Przycisk **Resetuj** powoduje wycofanie wszystkich ręcznych modyfikacji zasad podziału księgowań przez usunięcie wszystkich istniejących zasad podziału księgowań i ponowne wygenerowanie domyślnych zasad podziału księgowań.
    -   Wszelkie podrzędne zasady podziału księgowań, takie jak rabat, opłata i podatek, zawsze mają nadrzędną zasadę podziału księgowań. Można wyświetlić relację nadrzędny/podrzędny w menu **Odwołanie** &gt; **Informacje nadrzędne**.
    -   Konto główne i wymiary finansowe mogą być edytowane również dla podrzędnych.
    -   Wymiary finansowe dotyczące zasad podziału księgowań są zgodne z domyślnym wzorcem zakładającym, że dokument może być rozszerzany. Aby uzyskać szczegółowe informacje, zobacz powiązane artykuły.
    -   Zasady podziału księgowań dla odchylenia mogą być generowane w scenariuszach uzgadniania, takich jak uzgadnianie między fakturą od dostawcy a zamówieniem zakupu. Można wyświetlić relacje uzgadniania między zasadami podziału księgowań w menu **Odwołanie** &gt; **Informacje o dokumencie**.
    -   Przycisk **Popraw** jest dostępny dla dokumentów, które obsługują korekty. Przycisk **Popraw** tworzy nowe zasady podziału księgowań. Najpierw zasady podziału księgowań są tworzone w celu rezerwacji oryginalnych zasad podziału księgowań. Te zasady podziału księgowań nie mogą być modyfikowane. Następnie tworzona jest nowa prawidłowa zasad podziału księgowań. Te zasady podziału księgowań mogą być modyfikowane, jeśli oryginalne zasady podziału księgowań mogły być modyfikowane.
    -   Przycisk **Szczegóły projektu** jest włączony jako rozszerzenie, jeśli wiersz jest powiązany z projektem. Zasady podziału księgowań projektu umożliwiają modyfikowanie szczegółów, takich jak źródła finansowania i właściwości wiersza.
    -   Można wyświetlić bieżący stan księgowania dokumentu w menu **Odwołanie**. Stan dotyczy całego dokumentu i wskazuje, czy dokument jest w toku, czy też został zakończony.
-   **Wyświetl dystrybucje** — Wyświetlanie zasad podziału księgowań dla wszystkich wierszy i kwot pieniężnych w dokumencie. Nie można zmodyfikować zasad podziału księgowań w tym widoku.


Aby uzyskać więcej informacji, zobacz [Zasady podziału księgowań i zapisów w arkuszu księgi podrzędnej dla faktur niezależnych](accounting-distributions-subledger-journal-entries-vendor-invoices.md).


