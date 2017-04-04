---
title: "Sprzedaży/likwidacji środków trwałych dla Polski"
description: "Ten temat zawiera informacje o funkcjach sprzedaży/likwidacji środka trwałego dla użytkowników w firmach w Polsce."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetParameters, AssetPosting, CustFreeInvoice, LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 266964
ms.assetid: 99f3a20c-2e2e-4fc7-b846-3d86802174c4
ms.search.region: Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: e7c51c19ba9f28e5a3f46546c451f509074fe8e9
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-assets-disposal-for-poland"></a>Sprzedaży/likwidacji środków trwałych dla Polski

Ten temat zawiera informacje o funkcjach sprzedaży/likwidacji środka trwałego dla użytkowników w firmach w Polsce. 

Środki trwałe mogą być sprzedawane za pomocą funkcji usuwania poprzez faktury niezależnej, dziennik środka trwałego lub dziennik główny w księdze głównej. Aby uzyskać więcej informacji dotyczących likwidacji środków trwałych, zobacz [likwidacji środków trwałych konta księgowe](../fixed-assets/fixed-asset-disposal-posting-accounts.md). Dla użytkowników w firmach w Polsce rozszerzenie funkcjonalności sprzedaży/likwidacji środków trwałych obejmuje:

-   Szablon dla likwidacji środka trwałego na **profile księgowania środków trwałych** strony.
-   Dwa dodatkowe parametry na **zezwolenia na sprzedaż środka trwałego** strony. A **Sprawdź, czy środków trwałych mogą być sprzedawane** pole wyboru i **zezwolenia na sprzedaż środka trwałego** pole wyboru na **odwołanie i notatki** skróconej środka trwałego. Jeśli **Sprawdź, czy środków trwałych mogą być sprzedawane** pole wyboru jest zaznaczone, tylko zasoby oznaczone jako **zezwolenia na sprzedaż środka trwałego** mogą być sprzedawane.
-   Konto sprzedaży dla likwidacji środków trwałych, która zawiera dodatkowy parametr na **sprzedaży** skróconej na **ustalone parametry aktywa** strony. Za pomocą tego parametru można zdefiniować domyślne konto księgowe do księgowania sprzedaży środka trwałego.
-   Dodatkowe pola na wytwarzanie częściowej sprzedaży/likwidacji ** strony dla użytkowników, aby wprowadzić wartość procentową. Procent ten będzie służyć do obliczenia kwoty wiersza jako wartość księgową netto środków trwałych pomnożona o wartość procentową.

## <a name="templates-for-fixed-asset-disposal"></a>Szablony dla sprzedaży/likwidacji środka trwałego
Dla sprzedaży/likwidacji środka trwałego można użyć szablonu jako opcja, aby uprościć ustawianie kont dla likwidacji środków trwałych dla profilów księgowania. Aby utworzyć lub edytować szablony dla sprzedaży/likwidacji środka trwałego, wykonaj następujące kroki.

1.  Kliknij **aktywa trwałe**&gt;**instalacji**&gt;**profile księgowania środków trwałych**.
2.  W **usuwania** sekcji, kliknij **Utwórz szablon** i wybierz profil księgowania środków trwałych.
3.  Wypełnij następujące pola
    |                    |                                                                                                                                |
    |--------------------|--------------------------------------------------------------------------------------------------------------------------------|
    | **Field**          | **Description**                                                                                                                |
    | **Book**           | Wybierz księgę, którą chcesz skonfigurować lub zaktualizować konta księgowania dla likwidacji środka trwałego.                                         |
    | **Main account**   | Wybrane konto zostanie automatycznie użyta jako **konta głównego** w instalacji lub aktualizacji kont na potrzeby księgowania sprzedaży/likwidacji.       |
    | **Offset account** | Wybrane konto zostanie automatycznie użyta jako **konto przeciwstawne** w instalacji lub aktualizacji kont na potrzeby księgowania sprzedaży/likwidacji. |
    | **Overwrite**      | Jeśli zaznaczone, system zastąpi istniejące konta likwidacji dla wybranego **książki**.                                     |

4.  Click **OK**. System automatycznie tworzy lub aktualizuje reguł księgowania dla wybranej księgi dla następujących stałe składniki sprzedaży/likwidacji środków trwałych (typy transakcji):
    -   Amortyzacja (lata ubiegłe)
    -   Amortyzacja (ten rok)
    -   Korekty amortyzacji (lata wcześniejsze)
    -   Korekty amortyzacji (ten rok)
    -   Amortyzacja dodatkowa (poprzednie lata)
    -   Amortyzacja dodatkowa (bieżący rok)
    -   Umorzenie BO (lata ubiegłe)
    -   Umorzenie BO (ten rok)
    -   Zmiana wartości umorzenia (lata ubiegłe)
    -   Zmiana wartości umorzenia (ten rok)

## <a name="permission-to-sell"></a>Zezwolenia na sprzedaż
Zezwolenia na sprzedaż funkcjonalność rozszerza podstawowe likwidacji przez sprzedaż funkcjonalności dla użytkowników w firmach w Polsce z dwóch dodatkowych parametrów:

-   **Sprawdź, czy środków trwałych mogą być sprzedawane** — to pole wyboru umożliwia aktywować dodatkowy filtr w polu wyszukiwania, wybierając środek trwały ma być sprzedawane w wierszu dziennika lub faktury niezależnej. Dodatkowy filtr ma wpływ transakcji o typie **Likwidacja — sprzedaż** tylko. Aby edytować **Sprawdź, czy środków trwałych mogą być sprzedawane** pola, otwórz **sprzedaż** skróconej na **środków trwałych**&gt;**instalacji**&gt;**stałej parametrów trwałych** strony.
-   **Zezwolenia na sprzedaż środka trwałego** — Użyj tego pola wyboru umożliwia określenie, czy mogą być sprzedawane poszczególnych parametrów dla każdego środka trwałego. Aby edytować to pole, otwórz **odwołanie i notatki** skróconej dla wybranego środka trwałego.

## <a name="sales-account-for-fixed-assets-disposal"></a>Konto sprzedaży dla sprzedaży/likwidacji środków trwałych
Po transakcji sprzedaży sprzedaży/likwidacji w księdze głównej przy użyciu dziennika środka trwałego lub dziennik główny, konto sprzedaży jest równa wiersza dziennika na podstawie ustawień na **profile księgowania środków trwałych** strony. Podczas tworzenia transakcji likwidacji sprzedaży za pomocą faktury niezależnej, użytkownik powinien wypełnić **konta głównego** pole za pomocą konta sprzedaży. Konto sprzedaży dla środków trwałych, że funkcja usuwania umożliwia użytkownikom w firmach w Polsce skonfigurowanie konta księgowego, który będzie traktowana jako konto sprzedaży dla transakcji sprzedaży likwidacji tworzony domyślnie przy użyciu faktury niezależnej. Aby skonfigurować konto sprzedaży dla sprzedaży/likwidacji środków trwałych, otwórz **sprzedaż** skróconej na **środków trwałych**&gt;**instalacji**&gt;**ustalone parametry aktywa** strony.

## <a name="partial-sales-of-fixed-assets"></a>Sprzedaż częściowa środków trwałych
Sprzedaż lub złomowanie likwidacji środka trwałego umożliwia usuwanie całego środka trwałego, który tylko. Częściowa sprzedaż funkcje modułu środków trwałych pozwala użytkownikom w firmach w Polsce do dysponowania częściowo środka trwałego za pośrednictwem zarówno sprzedaż lub złomowanie typy transakcji. Częściowa sprzedaż środków trwałych jest dostępna za pośrednictwem faktury niezależnej, stałych dziennik ŚT lub dziennika głównego w księdze głównej. Aby częściowo likwidacja środka trwałego, wprowadź wartość procentową (liczba całkowita od 0 do 100) w **Sprzedaż częściowa** w jednej z następujących lokalizacji:

-   **Ogólne** tab na **dziennika środka trwałego** linii.
-   **Środki trwałe** tab na **dziennika głównego** linii.
-   **Ogólne** tab na **faktury niezależnej** linii.

Domyślnie **Sprzedaż częściowa** jest wartość pola **100**. Gdy użytkownik wybierze **usuwania odpadków** lub **sprzedaż usuwania** i typ transakcji środka trwałego w arkuszu, wartość księgowa netto będzie domyślnie w wierszu dziennika. Jeśli użytkownik zmieni wartość procentową, wartość księgowa netto w wierszu dziennika zostanie zmniejszona. Użytkownik może również ręcznie zmienić wartość księgowa netto, po którym procent w **Sprzedaż częściowa** pola zostaną obliczone ponownie. **Przykład** środek trwały został nabyty w USD 10.000, USD 1.000 amortyzacji, wartości księgowej netto USD 9.000. Pierwszy częściowa sprzedaż 50% - wartość księgowa netto obliczane dla wiersza arkusza jest 50 %USD 9.000 = USD 4.500. Drugi częściowa sprzedaż 50% - obliczona wartość księgową netto dla wiersza arkusza jest 50% pozostałą wartość księgową netto USD 4.500 = USD 2.250. Jeśli użytkownik chce, aby koszt netto pozostałą wartość księgową USD 2.250, on na arkuszu lub wiersza faktury niezależnej należy wprowadzić procent 100.


