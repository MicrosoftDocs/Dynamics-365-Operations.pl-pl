---
title: Raporty cen detalicznych
description: Ten temat zawiera omówienie funkcji raportu cen, która pozwala na wyświetlanie nadchodzące zmian cen dla produktów w asortymencie.
author: shajain
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 7fa2710d64d632c6e4ef376528aff8316b02a380ce7e2a976d53a3dd39375fa7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767273"
---
# <a name="retail-price-reports"></a>Raporty cen detalicznych

[!include [banner](includes/banner.md)]


W celu zapewnienia konkurencyjnych cen klientom, sprzedawcy detaliczni często zmieniają ceny produktów. Kierownicy sklepów mają możliwość łatwego dostępu do ostatnich i nadchodzących zmian cen, co pozwala im odpowiednio planować zasoby wymagane do aktualizacji etykiet z cenami na sklepowych półkach. W wersji 10.0 programu Commerce kierownik sklepu może otworzyć raport **Cena**, przechodząc do menu **Wszystkie sklepy \> Sklep \> Raport cen** i wyświetlając zaktualizowane ceny produktów skojarzone ze sklepem. 

Aby włączyć raport cen, parametr **Włącz raport cen w sklepie** musi być włączony. Ten parametr jest umieszczony na karcie **Parametry sprzedaży \> Rabaty \> Różne**. Otwarcie karty **Raport cen** wyświetla okno dialogowe z różnymi konfiguracjami. Poniżej przedstawiono listę dostępnych konfiguracji.

| Konfiguracja | opis |
|---|---|
| Data Od / Data Do| Zakres dat, dla których należy generować raport cen. Czas trwania jest obecnie ograniczony do 7 dni. |
| Kanał| Sklep, dla którego należy generować raport cen. |
| Wyświetl produkty z dostępnymi zapasami| Ustawienie **Tak** spowoduje wyświetlenie cen tylko dla tych produktów, które obecnie mają dostępne zapasy fizyczne w sklepie. |
| Wyświetl ceny wariantów | Ustawienie **Tak** spowoduje wyświetlenie cen wariantów wraz z produktami głównymi. Należy **włączyć** tę opcję tylko wówczas, gdy występują różne ceny wariantów, ponieważ liczba wierszy bardzo rośnie. W przyszłych wersjach włączymy obsługę cen na podstawie wymiarów, tak aby kierownik sklepu mógł wybrać wymiary, dla których mają być wyświetlane ceny. |
| Wyświetl produkty ze zmianami cen | Ustawienie **Tak** spowoduje wyświetlanie cen tylko dla tych dat, w których cena została zmieniona. Cena dla *jednego dnia przed* wybraną **Datą Od** zawsze będzie wyświetlana, tak aby kierownik sklepu mógł łatwo zidentyfikować produkty, których ceny nie zmieniły się przez cały wybrany okres, i mógł również łatwo wyświetlić bieżącą cenę. |

Po wygenerowaniu raportu można pobrać plik programu Excel dla wszelkich dodatkowych potrzeb filtrowania. Raport cen może również służyć do sprawdzania historycznych cen produktów dla dat z przeszłości.


[!INCLUDE[footer-include](../includes/footer-banner.md)]