--- 
title: "Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego"
description: "Ta procedura pokazuje kolejne kroki tworzenia reguł uzupełnienia."
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: f3a20b7bf476cae854c7f7c86d89d73e44b6749b
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a>Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura pokazuje kolejne kroki tworzenia reguł uzupełnienia. Reguły uzupełnienia mogą służyć do kontrolowania sposobu rozdzielania produktów do sklepów podczas korzystania z funkcji przeładunku kompletacyjnego i dystrybucji na zamówienie. Reguły uzupełnienia mogą być skonfigurowane dla sklepów lub grup sklepów. Waga zdefiniowana dla każdego wiersza w regule będzie określać sposób rozdziału ilości produktów między sklepy, jeśli reguły uzupełnienia są używane jako metoda dystrybucji w przeładunku kompletacyjnym lub dystrybucji na zamówienie. Ta procedura wykorzystuje firmę demonstracyjną USRT.

1. Przejdź do okna Reguły uzupełnienia.
2. Kliknij przycisk Nowy.
3. W polu Reguła uzupełnienia wpisz wartość.
4. Wypełnij pole Opis.
5. Kliknij przycisk Zapisz.
6. Kliknij przycisk Dodaj.
7. Na liście oznacz wybrany wiersz.
    * W polu typu można wybrać Hierarchia uzupełnienia lub Kanał. Ta wartość określa, czy opcja wybrana w polu Nazwa jest hierarchią kanałów, czy określonym kanałem.  W tym przykładzie należy pozostawić to ustawienie jako Hierarchia uzupełnienia.  
8. W polu Nazwa wybierz wartość.
    * Wartość domyślnej wagi jest ustawiana na podstawie wagi zdefiniowanej w magazynie.  Ta waga może być używana dla reguły uzupełnienia lub też można wpisać nową wagę w polu Waga.  
9. W polu Waga wprowadź liczbę.
10. Kliknij przycisk Dodaj.
11. Na liście oznacz wybrany wiersz.
12. W polu Typ wybierz opcję „Kanał”.
13. W polu Nazwa wprowadź lub wybierz wartość.
14. W polu Waga wprowadź liczbę.
15. Kliknij przycisk Zapisz.


