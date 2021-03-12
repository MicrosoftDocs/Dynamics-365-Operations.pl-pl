---
title: Arkusze magazynowe
description: W tym temacie opisano, jak używać arkuszy magazynowych do księgowania różnych rodzajów transakcji magazynowych.
author: perlynne
manager: tfehr
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a822f5f7bb76604bbebdb3282fd51985d3ccba8e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978045"
---
# <a name="inventory-journals"></a>Arkusze magazynowe

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak używać arkuszy magazynowych do księgowania różnych rodzajów transakcji magazynowych.

Arkusze magazynowe w Supply Chain Management są używane do księgowania transakcji magazynu fizycznego różnych typów, takich jak księgowanie rozchodów i przychodów, przesunięć magazynowych, tworzenie list składowych BOM i uzgadnianie zapasów fizycznych. Wszystkie arkusze magazynowe są używane w sposób podobny, ale są one podzielone na różne typy.

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

Używając arkusza przesunięcia magazynowego, koszt można dodać do towaru po dodaniu zapasów, jednak można ręcznie przydzielić koszt dodatkowy do konta księgi głównej poprzez określenie konta przeciwstawnego księgi głównej podczas tworzenia arkusza. Ten typ arkusza magazynowego jest przydatny, jeśli chcesz zastąpić domyślne konta księgowania.

### <a name="inventory-adjustment"></a>Korekta zapasów

W przypadku korzystania z arkusza korekt zapasów koszt można dodać do towaru po dodaniu zapasów. Koszt dodatkowy jest automatycznie księgowany na koncie określonej księgi głównej, na podstawie ustawień profili księgowania grup towarów. Ten typ arkusza magazynowego umożliwia aktualizowanie zysków i strat do ilości zapasów, gdy towar ma zachować jego domyślne konto przeciwstawne księgi głównej. Podczas księgowania arkusza korekt zapasów księgowane jest przyjęcie na magazyn lub rozchód z magazynu, zmieniane są wartości zapasów i tworzone są transakcje księgi.

### <a name="transfer"></a>Przenieś

Arkusz przeniesienia służy do przenoszenia towarów między lokalizacjami składowania, partiami lub wariantami produktów bez kojarzenia efektów kosztowych. Na przykład można przenosić elementy z jednego magazynu do innego magazynu w obrębie tej samej firmy. W przypadku korzystania z arkusza przeniesienia, należy określić wymiary magazynowe „od” i „do” (na przykład dla oddziału i magazynu). Dostępne zapasy zdefiniowanego wymiaru magazynowego są odpowiednio zmieniane. Przeniesienia zapasów odzwierciedlają natychmiastowe przeniesienie materiału. Zapasy w tranzycie nie są śledzone. Jeśli konieczne jest śledzenie zapasów w tranzycie, należy skorzystać z zamówienia przeniesienia. Przy księgowaniu arkusza przeniesienia tworzone są dwie transakcje magazynowe dla każdego wiersza arkusza:

-   Wydanie zapasów w lokalizacji „z”.
-   Przyjęcie zapasów w lokalizacji „do”.

### <a name="bom"></a>BOM

Podczas zgłaszania BOM jako gotowych można utworzyć arkusz BOM. Przy użyciu arkusza BOM, można księgować bezpośrednio BOM. To księgowanie generuje przyjęcie produktu na magazyn wraz z powiązanym BOM i wydaniem z magazynu produktów uwzględnionych w BOM. Ten typ arkusza magazynowego jest przydatny w sytuacjach dużej produkcji, gdzie marszruty nie są wymagane.

### <a name="item-arrival"></a>Przyjęcie pozycji

Arkusz przyjęcia towaru służy do rejestrowania przyjęć towarów (na przykład z zamówienia zakupu). Arkusz przyjęcia towaru można utworzyć w ramach zarządzania przyjęciem na stronie **Przegląd przyjęć** lub można ręcznie utworzyć wpis dziennika na stronie **przyjęcia towaru**. Jeśli w arkuszu przyjęcia towaru włączysz opcję sprawdzania lokalizacji pobrania, Supply Chain Management szuka lokalizacji dla przyjmowanych towarów i jeśli znajdzie miejsce, generuje docelowe lokalizacje dla nadchodzących towarów.

### <a name="production-input"></a>Przyjęcie z produkcji

Arkusz przyjęcia z produkcji działa jak arkusz przyjęcia towaru, ale jest używany w przypadku zleceń produkcyjnych.

### <a name="counting"></a>Inwentaryzacja

Arkusze inwentaryzacyjne pozwalają poprawić bieżącą ilość dostępnych zapasów zarejestrowaną dla towarów lub grup towarów. Następnie można zaksięgować rzeczywistą fizyczna ilość, tak aby wprowadzić korekty wymagane do uzgadniania różnic. Zasady obliczania można skojarzyć z grupami inwentaryzacji, co ułatwia grupowanie towarów o różnych właściwościach, dzięki czemu pozycje można uwzględnić w arkuszu zliczania. Na przykład można ustawić grupy inwentaryzacji, tak aby zliczały pozycje o określonej częstotliwości lub obliczały towar, gdy zapasy spadną do określonego poziomu. Aby uzyskać informacje o definiowaniu grup inwentaryzacji, zobacz [Definiowanie procesów inwentaryzacji zapasów](tasks/define-inventory-counting-processes.md).

### <a name="tag-counting"></a>Zliczanie znaczników

Arkusze zliczania służą do przypisywania numerowanego znacznika do zliczonej partii. Znacznik powinien zawierać numer, numer pozycji i ilość towaru. Aby zagwarantować, że znacznik jest używany tylko jeden raz, i że wszystkie znaczniki są używane, numer każdego towaru powinien mieć niepowtarzalny zestaw znaczników z własną numeracją. Dla każdego znacznika można ustawić trzy wartości stanu:

-   **Używany** — numer towaru jest zliczany dla znacznika.
-   **Unieważnione** — numer towaru jest unieważniany dla znacznika.
-   **Brakujący** — brakuje numeru towaru dla znacznika.

Po zaksięgowaniu arkusza zliczania znaczników na podstawie jego wierszy jest tworzony nowy arkusz zliczania. Aby uzyskać więcej informacji na temat zliczania znaczników, zobacz [Zliczanie znaczników zapasów](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Praca z arkuszami
Tylko jeden użytkownik może mieć w danej chwili dostęp do określonego arkusza. Jeśli kilku użytkowników musi mieć dostęp do arkuszy w tym samym czasie do tworzenia wierszy arkusza, użytkownicy muszą zaznaczyć arkusze, które nie są aktualnie używane, aby uniknąć nadpisania danych. W sytuacji, w której wiele działów używa tego samego typu arkusza warto utworzyć wiele nazw arkusza (na przykład jeden na dział). Można także podzielić arkusze tak, że każda procedura księgowania będzie wprowadzana we własnym unikatowym arkuszu magazynowym. Dla procedur księgowania powiązanych z transakcjami magazynowymi należy utworzyć jeden arkusz do okresowych korekt zasobów i jeden do zliczania zasobów.

## <a name="posting-journal-lines"></a>Wiersze arkusza księgowania
Można księgować wiersze arkusza, które można utworzyć w dowolnym momencie, dopóki towar nie zostanie zablokowany z innych transakcji. Wpisane w arkuszu dane pozostają w arkuszu nawet po zamknięciu go bez księgowania wierszy arkusza.

## <a name="data-entity-support-for-inventory-journals"></a>Obsługa jednostek danych w arkuszach magazynowych

Jednostki danych obsługują następujące typy scenariuszy integracji:
-    Usługa synchroniczna (OData)
-  Integracja asynchroniczna

Aby uzyskać więcej informacji, zobacz [Jednostki danych](../../dev-itpro/data-entities/data-entities.md).

> [!NOTE]
> Nie wszystkie arkusze magazynowe obsługują usługę OData, dlatego nie można używać aplikacji łącznika danych programu Excel do publikowania, aktualizowania i importowania danych z powrotem do Supply Chain Management. 

Kolejna różnica między jednostkami danych arkusza dotyczy możliwości używania jednostek złożonych, które zawierają zarówno dane nagłówka, jak i dane wiersza. Obecnie jednostek złożonych można używać dla następujących arkuszy:
-   Arkusz korekt zapasów
-   Arkusz przesunięcia magazynowego

Te dwa arkusze magazynowe obsługują scenariusz *Inicjowanie zapasów* tylko w ramach projektu importu w zarządzaniu danymi:
-  Jeśli nie określono numeru nagłówka arkusza, ale określono numerację dla typu arkusza, zadanie importu automatycznie utworzy nagłówki arkuszy na 1000 wierszy. Na przykład zaimportowanie 2020 wierszy spowoduje utworzenie następujących trzech nagłówków arkuszy:
    -  Nagłówek 1: będzie zawierał 1000 wierszy
    -  Nagłówek 2: będzie zawierał 1000 wierszy
    -  Nagłówek 3: będzie zawierał 20 wierszy
-  Zakłada się istnienie unikatowych danych wierszy dla każdego wymiaru zapasów, którym może być wymiar produktu, magazynowania lub śledzenia. Z tego względu nie jest możliwe zaimportowanie wierszy arkusza, gdzie w tym samym projekcie importu różni się tylko zawartość pola daty w wierszach.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Jednostki danych](../../dev-itpro/data-entities/data-entities.md)
