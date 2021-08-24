---
title: Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego
description: Ta procedura pokazuje kolejne kroki tworzenia reguł uzupełnienia.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 776defca4a9d2a860901efe9e8890fd11ec8ce7302c53dc1507cc77ff501aded
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753059"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a>Konfigurowanie reguł i parametrów dla przeładunku komplementacyjnego i dystrybucji od kupującego

[!include [banner](../includes/banner.md)]

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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]