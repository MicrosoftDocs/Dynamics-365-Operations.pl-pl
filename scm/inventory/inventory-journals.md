---
title: Arkusze magazynowe
description: "W tym artykule opisano, jak używać arkuszy magazynowych do księgowania różnych rodzajów transakcji magazynowych."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e50d12b62e03ae3c3c6a37b5f0be879ad8d802d7
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="inventory-journals"></a>Arkusze magazynowe

[!include[banner](../includes/banner.md)]


W tym artykule opisano, jak używać arkuszy magazynowych do księgowania różnych rodzajów transakcji magazynowych. 

Arkusze magazynowe w programie Microsoft Dynamics 365 for Operations są używane do księgowania różnych typów transakcji na fizycznych zapasach, np. do księgowania wydań i przyjęć, przesunięć magazynowych, tworzenia list składowych BOM i uzgadniania zapasów fizycznych. Wszystkie arkusze magazynowe są używane w sposób podobny, ale są one podzielone na różne typy.

## <a name="types-of-inventory-journals"></a>Typy arkuszy magazynowych
Dostępne są następujące typy arkuszy magazynowych:

-   Przesunięcie
-   Korekta zapasów
-   Przenieś
-   lista BOM
-   Przyjęcie pozycji
-   Przyjęcie z produkcji
-   Inwentaryzacja
-   Zliczanie znaczników

### <a name="movement"></a>Przesunięcie

Używając arkusza przesunięcia magazynowego, koszt można dodać do towaru po dodaniu zapasów, jednak można ręcznie przydzielić koszt dodatkowy do konta księgi głównej poprzez określenie konta przeciwstawnego księgi głównej podczas tworzenia arkusza. Ten typ arkusza magazynowego przydaje się do wydatkowania pozycji w innym dziale, jeśli chcesz usunąć pozycję z magazynu na cele wydatków.

### <a name="inventory-adjustment"></a>Korekta zapasów

W przypadku korzystania z arkusza korekt zapasów koszt można dodać do towaru po dodaniu zapasów. Koszt dodatkowy jest automatycznie księgowany na koncie określonej księgi głównej, na podstawie ustawień profili księgowania grup towarów. Ten typ arkusza magazynowego umożliwia aktualizowanie zysków i strat do ilości zapasów, gdy towar ma zachować jego domyślne konto przeciwstawne księgi głównej. Podczas księgowania arkusza korekt zapasów księgowane jest przyjęcie na magazyn lub rozchód z magazynu, zmieniane są wartości zapasów i tworzone są transakcje księgi.

### <a name="transfer"></a>Przenieś

Arkusz przeniesienia służy do przenoszenia towarów między lokalizacjami składowania, partiami lub wariantami produktów bez kojarzenia efektów kosztowych. Na przykład można przenosić elementy z jednego magazynu do innego magazynu w obrębie tej samej firmy. W przypadku korzystania z arkusza przeniesienia, należy określić wymiary magazynowe „od” i „do” (na przykład dla oddziału i magazynu). Dostępne zapasy zdefiniowanego wymiaru magazynowego są odpowiednio zmieniane. Przeniesienia zapasów odzwierciedlają natychmiastowe przeniesienie materiału. Zapasy w tranzycie nie są śledzone. Jeśli konieczne jest śledzenie zapasów w tranzycie, należy skorzystać z zamówienia przeniesienia. Przy księgowaniu arkusza przeniesienia tworzone są dwie transakcje magazynowe dla każdego wiersza arkusza:

-   Wydanie z magazynu w lokalizacji "od"
-   Przyjęcie na magazyn w lokalizacji "do"

### <a name="bom"></a>lista BOM

Podczas zgłaszania BOM jako gotowych można utworzyć arkusz BOM. Przy użyciu arkusza BOM, można księgować bezpośrednio BOM. To księgowanie generuje przyjęcie produktu na magazyn wraz z powiązanym BOM i wydaniem z magazynu produktów uwzględnionych w BOM. Ten typ arkusza magazynowego jest przydatny w sytuacjach dużej produkcji, gdzie marszruty nie są wymagane.

### <a name="item-arrival"></a>Przyjęcie pozycji

Arkusz przyjęcia towaru służy do rejestrowania przyjęć towarów (na przykład z zamówienia zakupu). Arkusz przyjęcia towaru można utworzyć w ramach zarządzania przyjęciem na stronie **Przegląd przyjęć** lub można ręcznie utworzyć wpis dziennika na stronie **przyjęcia towaru**. Jeśli w arkuszu przyjęcia towaru włączysz opcję sprawdzania lokalizacji pobrania, program Dynamics 365 for Operations szuka lokalizacji dla przyjmowanych towarów i jeśli znajdzie miejsce, generuje docelowe lokalizacje dla nadchodzących towarów.

### <a name="production-input"></a>Przyjęcie z produkcji

Arkusz przyjęcia z produkcji działa jak arkusz przyjęcia towaru, ale jest używany w przypadku zleceń produkcyjnych.

### <a name="counting"></a>Inwentaryzacja

Arkusze zliczania pozwalają poprawić bieżącą ilość dostępnych zapasów zarejestrowaną dla towarów lub grup towarów. Następnie można zaksięgować rzeczywistą fizyczna ilość, tak aby wprowadzić korekty wymagane do uzgadniania różnic. Zasady obliczania można skojarzyć z grupami inwentaryzacji, co ułatwia grupowanie towarów o różnych właściwościach, dzięki czemu pozycje można uwzględnić w arkuszu zliczania. Na przykład można ustawić grupy inwentaryzacji, tak aby zliczały pozycje o określonej częstotliwości lub obliczały towar, gdy zapasy spadną do określonego poziomu. Aby uzyskać informacje o definiowaniu grup inwentaryzacji, zobacz [Definiowanie procesów inwentaryzacji zapasów (przewodnik po zadaniu)](http://ax.help.dynamics.com/en/wiki/define-inventory-counting-processes/).

### <a name="tag-counting"></a>Zliczanie znaczników

Arkusze zliczania służą do przypisywania numerowanego znacznika do zliczonej partii. Znacznik powinien zawierać numer, numer pozycji i ilość towaru. Aby zagwarantować, że znacznik jest używany tylko jeden raz i, że wszystkie znaczniki są używane, numer każdego towaru powinien mieć niepowtarzalny zestaw znaczników z własną sekwencją numerów. Dla każdego znacznika można ustawić trzy wartości stanu:

-   **Używany** — numer towaru jest zliczany dla znacznika.
-   **Unieważnione** — numer towaru jest unieważniany dla znacznika.
-   **Brakujący** — brakuje numeru towaru dla znacznika.

Po zaksięgowaniu arkusza zliczania znaczników na podstawie jego wierszy jest tworzony nowy arkusz zliczania. Aby uzyskać więcej informacji na temat zliczania znaczników, zobacz [Zliczanie znaczników zapasów](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Praca z arkuszami
Tylko jeden użytkownik może mieć w danej chwili dostęp do określonego arkusza. Jeśli kilku użytkowników musi mieć dostęp do arkuszy w tym samym czasie do tworzenia wierszy arkusza, użytkownicy muszą zaznaczyć arkusze, które nie są aktualnie używane, aby uniknąć nadpisania danych. W sytuacji, w której wiele działów używa tego samego typu arkusza warto utworzyć wiele nazw arkusza (na przykład jeden na dział). Można także podzielić arkusze tak, że każda procedura księgowania będzie wprowadzana we własnym unikatowym arkuszu magazynowym. Dla procedur księgowania powiązanych z transakcjami magazynowymi należy utworzyć jeden arkusz do okresowych korekt zasobów i jeden do zliczania zasobów.

## <a name="posting-journal-lines"></a>Wiersze arkusza księgowania
Można księgować wiersze arkusza, które można utworzyć w dowolnym momencie, dopóki towar nie zostanie zablokowany z innych transakcji. Wpisane w arkuszu dane pozostają w arkuszu nawet po zamknięciu go bez księgowania wierszy arkusza.




