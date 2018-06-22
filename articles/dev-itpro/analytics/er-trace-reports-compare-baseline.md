---
title: "Śledzenie wyników wygenerowanych raportów i porównywanie ich z wartościami bazowymi"
description: "Ten temat zawiera informacje dotyczące sposobu porównywania wyników generowanych raportów ER z wartości raportu bazowego."
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: 1a598d0bd053c60c3f8df6b05ecb7ff15addfaa3
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2018

---

# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Śledzenie wyników wygenerowanych raportów i porównywanie ich z wartościami bazowymi

[!include[banner](../includes/banner.md)]

Można śledzić wyniki formatów ER, dzięki którym są generowane wychodzące dokumenty elektroniczne. Po włączeniu generowania śledzenia (parametr użytkownika ER **Uruchom w trybie debugowania**), nowy rekord śledzenia jest generowany w dzienniku formatu ER po każdym uruchomieniu raportu ER. Następujące informacje są przechowywane w każdym śledzeniu, które jest generowane:

- Wszystkie ostrzeżenia wygenerowane przez reguły weryfikacji
- Wszystkie błędy wygenerowane przez reguły weryfikacji 
- Wszystkie wygenerowane pliki przechowywane jako załączniki rekordu śledzenia

Można przechowywać pojedyncze podstawowe pliki aplikacji dla dowolnego formatu ER. Pliki są traktowane jako bazowe, jeśli opisują oczekiwane wyniki generowanych raportów. Jeśli plik podstawowy jest dostępny dla formatu ER, który był uruchomiony przy włączonej funkcji generowania śladu, sklep śledzi nie tylko szczegóły wspomniane wcześniej, ale również wynik porównania wygenerowanego dokumentu elektronicznego z plikiem podstawowym. Za pomocą jednego kliknięcia można umieścić wygenerowany dokument elektroniczny i jego plik podstawowy w jednym pliku zip. Następnie można przeprowadzić szczegółowe porównanie za pomocą narzędzi zewnętrznych, takich jak Windiff.

Można ocenić śledzenie w celu przeanalizowania, czy wygenerowane dokumenty elektroniczne mają oczekiwaną zawartość. Można przeprowadzić tę ewaluację w środowisku testowania akceptacji użytkownika (UAT) po zmianie kodu podstawowego (na przykład jeśli zostanie przeniesiony do nowej instancji aplikacji, zainstalowane będą pakiety poprawek albo po wdrożeniu modyfikacji kodu). W ten sposób można uzyskać pewność, że ocena nie wpłynie na wykonywanie używanych raportów modułu ER. W wielu raportach modułu ER ocena może zostać przeprowadzona w trybie nienadzorowanym.

Aby dowiedzieć się więcej o tej funkcji, należy odtworzyć przewodniki **ER Generowanie raportów i porównanie wyników (część 1)** i **ER Generowanie raportów i porównanie wyników (część 2)**, które wchodzą w skład procesu biznesowego **7.5.4.3 Informatyczne usługi lub rozwiązania testowe (10679)** i można je pobrać z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Te wskazówki zadania przeprowadzą Cię przez proces konfigurowania struktury ER w celu użycia plików wyjściowych do oceny wygenerowanych dokumentów elektronicznych.

