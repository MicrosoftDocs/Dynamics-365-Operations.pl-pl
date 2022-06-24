---
title: Przegląd przyjęć
description: Ten artykuł zawiera informacje dotyczące funkcji przeglądu przyjęć. Strona Przegląd przyjęć jest częścią tej funkcji i zawiera przegląd wszystkich towarów, których przybycia oczekuje się jako towary przychodzące.
author: yufeihuang
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, WMSArrivalOverviewProfile, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "274363"
- intro-internal
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 8118db9469c01c43b23c64ee383ac1d383a0ba7a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874080"
---
# <a name="arrival-overview"></a>Przegląd przyjęć

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące funkcji przeglądu przyjęć. Strona Przegląd przyjęć jest częścią tej funkcji i zawiera przegląd wszystkich towarów, których przybycia oczekuje się jako towary przychodzące.

Strona **Przegląd przyjęć** strona zawiera przegląd wszystkich oczekiwanych towarów przychodzących. Pokazuje również przybycia, które można inicjować w oparciu o przegląd. Ten artykuł koncentruje się na procesie przyjęcia.

## <a name="business-scenario"></a>Scenariusz biznesowy
Rozważmy następujący scenariusz w procesach przychodzących.

[![Scenariusz biznesowy.](./media/arrival-overview-scenario.png)](./media/arrival-overview-scenario.png)

Zbyszek, pracownik przyjmujący, chce wiedzieć, jakie towary mają zostać dzisiaj przyjęte. Na stronie **Przegląd przyjęć** Zbyszek może uzyskać obraz bieżących zadań oraz oszacowanie ilości, objętości i masy, obejrzeć różne typy zamówień itd. Później do jednego z doków rozładunkowych dociera dostawa i Zbyszek otrzymuje spis zawartości dostawy. Na stronie **Przegląd przyjęć** Zbyszek wykonać następujące zadania:

-   Identyfikacja pasującego zlecenia przyjęcia i zarejestrowanie przyjęcia jako **W toku**. Wiersze wymagane dla rejestracji są generowane automatycznie i można wtedy monitorować przyjęcie, nawet jeśli transakcje nie zostały jeszcze zaksięgowane jako **Zarejestrowane**.
-   Przejście do odpowiedniego referencyjnego arkusza przyjęć (tzn. arkusza **Przyjęcie pozycji** lub **Przyjęcie z produkcji**) oraz zidentyfikowanie arkuszy gotowych na aktualizację przyjęcia produktów.

## <a name="arrival-overview-page"></a>Strona Przegląd przyjęć
Aby otworzyć stronę **Przegląd przyjęć**, kliknij kolejno opcje **Zarządzanie zapasami** &gt; **Zamówienia przychodzące** &gt; **Przegląd przyjęć**. Możesz wyświetlić listę zamówień, których przyjęcie jest oczekiwane. Przegląd jest podzielony na nagłówek i wiersze. Informacje nagłówka są pogrupowane według typu zamówienia, oczekiwanej daty przyjęcia i miejsca przeznaczenia dostawy. Gdy zostanie zaznaczony wiersz nagłówka przybycia, w części szczegółów wierszy na stronie zostaną wybrane dla przybycia wszystkie wiersze szczegółów związane z przyjęciem. Po zaksięgowaniu wszystkich odnośnych wierszy arkusza informacje te nie są wyświetlane.

### <a name="arrival-overview-profiles"></a>Profile przeglądu przyjęć

Strona **Przegląd przyjęć** zawiera przegląd towarów, których przybycie jest oczekiwane, oraz datę oczekiwanego przybycia. W procesie przyjęcia można używać wielu zestawów ustawień osobistych. Poszczególni użytkownicy mogą definiować swoje osobiste ustawienia na stronie **Profile przeglądu przyjęć**.

### <a name="set-up-item-arrival"></a>Konfigurowanie przybycia towaru

W omawianym przykładzie Zbyszek chce skonfigurować nowy komputer w lokalizacji, która będzie używana do przyjmowania wyrobów gotowych pochodzących z produkcji w oddziale 1. Na stronie **Profile przeglądu przyjęć** Zbyszek tworzy nową konfigurację o nazwie **Oddział 1 produkcja** i określa następujące ustawienia:

1.  Na skróconej karcie **Opcje przyjęcia** w grupie pól **Zakres** wprowadza informacje dotyczące zakresu dni i magazynów, które mają być uwzględnienie w przeglądzie.
2.  Na skróconej karcie **Opcje przyjęcia** w grupie pól **Arkusz** wprowadza magazyn przyjmujący, lokalizację i nazwę arkusza (przybycia towaru/przyjęcia z produkcji).
3.  Na skróconej karcie **Szczegóły zapytania dotyczącego przyjęcia** w grupie pól **Oddział** w polu **Ogranicz do oddziału** wprowadza oddział, aby ograniczyć widok w obszarze przeglądu.
4.  Na skróconej karcie **Szczegóły zapytania dotyczącego przyjęcia** w grupie pól **Wyświetlane typy transakcji** ustawia opcję **Zlecenia produkcyjne** na **Tak**.
5.  Na skróconej karcie **Szczegóły zapytania dotyczącego przyjęcia** w grupie **Różne** ustawia opcję **Aktualizuj przy uruchomieniu** na **Tak**, jeśli widok ma być automatycznie aktualizowany podczas uruchamiania systemu. Jeśli widok powinien być automatycznie aktualizowany po zmianie wartości zakresu, należy ustawić opcję **Aktualizuj dane po zmianie zakresu** na **Tak**.

W tym przykładzie pole **Nazwa profilu przeglądu przyjęć** na skróconej karcie **Opcje przyjęcia** na stronie **Przegląd przyjęć** jest ustawione na **Oddział 1 produkcja**.

### <a name="prerequisites-for-arrival-journals"></a>Wymagania wstępne dotyczące arkuszy przyjęć

Aby automatycznie tworzyć arkusze przyjęć ze strony **Przegląd przyjęć**, należy zdefiniować odpowiednie informacje w grupie pól **Arkusz** na skróconej karcie **Opcje przyjęcia**.

-   Aby utworzyć arkusz, należy określić nazwę arkusza.

[![Określanie nazwy arkusza.](./media/arrival-overview-journal.png)](./media/arrival-overview-journal.png)

-   Po określeniu wartości w polach **Magazyn** i **Lokalizacja** wartości te są stosowane w wierszach arkusza. Jeśli nie określisz wartości, system używa wartości z wymiaru określonego w transakcjach magazynowych.

#### <a name="items-that-are-received-from-one-expected-receipt-order"></a>Towary przyjmowane z jednego zlecenia oczekiwanego przyjęcia

Na skróconej karcie **Przyjęcia** Zbyszek zaznacza wiersz, a następnie klika opcję **Rozpocznij przyjęcie**. Wszystkie powiązane wiersze, które znajdują się w podanym zakresie i mają ilości do zarejestrowania, są automatycznie zaznaczane. Jest generowany arkusz przyjęcia towaru zawierający uzgodnienie między zleceniem oczekiwanego przyjęcia a arkuszem. Ilość jest inicjowana automatycznie we wszystkich utworzonych wierszach.

#### <a name="items-that-are-received-from-more-than-one-expected-receipt-order"></a>Towary przyjmowane z więcej niż jednego zlecenia oczekiwanego przyjęcia

Na skróconej karcie **Przyjęcia** Zbyszek zaznacza wiele wierszy, a następnie klika opcję **Rozpocznij przyjęcie**. Jest generowany arkusz przyjęcia towaru zawierający uzgodnienie między wszystkimi zleceniami oczekiwanego przyjęcia a arkuszem. Wszystkie wiersze są tworzone w jednym nagłówku arkusza przyjęcia towaru, a ilość jest automatycznie inicjowana.

### <a name="receive-items-from-one-or-more-expected-receipt-orders"></a>Przyjmowanie towarów z jednego lub więcej zleceń oczekiwanego przyjęcia

#### <a name="view-information"></a>Wyświetl informacje

Aby wyświetlić przegląd oczekiwanych przyjęć w przedziale dat, Zbyszek wprowadza następujące informacje w polach na skróconej karcie **Opcje przyjęcia** na stronie **Przegląd przyjęć**, a następnie klika przycisk **Aktualizuj** w celu zaktualizowania widoku:

-   Nazwa profilu przeglądu przyjęć: **Informacje**
-   Pokaż wiersze: **Wszystko**
-   Dni wstecz: (puste)
-   Dni do przodu: **0**
-   Magazyny: **GW, MW**

Zbyszek może wyświetlić następujące informacje:

-   Wszystkie powiązane zlecenia przyjęć dla daty systemowej i na nieograniczoną liczbę dni wstecz od niej (zakres **InventTrans.StatusDate**) oraz przyjęcia do magazynów GW i MW, niezależnie od ich stanu.
-   Szczegółowe informacje o wierszach dla więcej niż jednego zamówienia. Zbyszek może wybrać wiele wierszy nagłówków w przeglądzie, a następnie kliknąć przycisk **Pokaż wszystkie zaznaczone**, aby wyświetlić wszystkie szczegółowe informacje o odnośnych wierszach dla wszystkich wybranych zamówień.
-   Informacje o konkretnym zamówieniu zakupu. Aby wyświetlić tylko informacje dotyczące określonego numeru odwołania w przeglądzie, Zbyszek może wprowadzić numer konta w polu **Numer konta** oraz numer zamówienia w polu **Numer odwołania**.
-   Przegląd zadań rejestracji wymaganych dla wszystkich wierszy zamówienia, dla których utworzono arkusz przyjęcia towaru, ale jeszcze go nie zaksięgowano. Aby wyświetlić te informacje, Zbyszek może wybrać opcję **W toku** w polu **Pokaż wiersze**.

### <a name="update-journals"></a>Aktualizowanie arkuszy

Aby zarejestrować jeden lub więcej wierszy zamówienia, które mają być przetwarzane, Zbyszek może zaznaczyć wiersze w siatce przeglądu lub w siatce wierszy, a następnie kliknąć kolejno opcje **Arkusze** &gt; **Pokaż arkusze przyjęcia**. Zostaną wyświetlone nagłówki przybycia towarów pasujące do wierszy. Aby zaktualizować przyjęcie produktu określonego w zamówieniu zakupu dla zarejestrowanych pozycji, Zbyszek może przejść do nagłówków arkuszy przyjęcia towaru, które są gotowe do aktualizacji. W celu przejścia do tych nagłówków arkuszy przyjęcia towaru klika kolejno opcje **Arkusze** &gt; **Gotowe arkusze dokumentów przyjęcia produktów**. Zostaną wyświetlone wszystkie wiersze nagłówków gotowe na aktualizację przyjęcia produktów w podanym zakresie magazynów. (Wyświetlane wiersze nagłówków nie są związane z zakresem dni).

### <a name="start-an-arrival-registration"></a>Rozpoczynanie rejestracji przybycia

Zaznaczając wiele wierszy na stronie **Przegląd przyjęć**, Zbyszek może uruchomić proces przybycia dla więcej niż jednego przyjęcia. Gdy zaznaczy wiersz w przeglądzie przyjęć, są zaznaczane odpowiednie szczegóły wiersza. Jeśli istnieje ilość do rejestracji, jest dostępny przycisk **Rozpocznij przyjęcie**. Zbyszek może rozpocząć rejestrację przybycia dwoma metodami:

-   Aby wyfiltrować stronę w celu pokazania tylko rekordów spełniających określone kryteria, w polu **Odwołanie do dostawcy** zeskanowanie numeru odwołania od dostawcy, na przykład kodu kreskowego z dokumentu dostawy.
-   Na stronie **Przegląd przyjęć** w części dotyczącej przeglądu lub szczegółów ręczne wybranie lub anulowanie wyboru rekordów do rejestracji przybycia. Gdy następnie Zbyszek kliknie przycisk **Rozpocznij przyjęcie**, wybrane rekordy zostaną utworzone automatycznie w arkuszu przyjęcia towaru. Rekordy zawierają informacje o wierszach, a wszystkie unikatowe informacje pól są przypisane.

## <a name="update-arrival-information-and-process-a-product-receipt"></a>Aktualizowanie informacji o przybyciu i przetwarzanie przyjęcia produktów
Gdy wszystkie towary są zarejestrowane, kierownik magazynu lub kierownik ds. zakupów może zaktualizować otrzymane towary za pomocą dokumentu przyjęcia produktów, aby dodać fizyczny koszt. Aby zaktualizować informacje o przybyciu i zaksięgować przyjęcie produktów, wykonaj następujące kroki:

1.  Kliknij kolejno opcje **Zarządzanie zapasami** &gt; **Zamówienia przychodzące** &gt; **Przegląd przyjęć**.
2.  Na stronie **Przegląd przyjęć** kliknij kolejno opcje **Arkusze** &gt; **Gotowe arkusze dokumentów przyjęcia produktów**, aby wyświetlić listę arkuszy gotowych na aktualizację przyjęcia produktów.
3.  Zaznacz arkusze, które muszą zostać zaktualizowane, a następnie kliknij kolejno opcje **Funkcje** &gt; **Dokument przyjęcia produktów**.
4.  Na stronie **Księgowanie** wprowadź numer przyjęcia produktów, jeśli nie jest jeszcze umieszczony w arkuszu, a następnie kliknij przycisk **OK**, aby wykonać przetwarzanie przyjęcia produktów.

## <a name="summary"></a>Sumarycznie
Strona **Przegląd przyjęć** może pomóc kierownikowi magazynu i pracownikom magazynu uzyskać obraz oczekiwanej pracy, którą należy wykonać w ramach procesu przychodzącego. Strona może również służyć do rozpoczęcia procesu przybycia towaru, ponieważ można wtedy śledzić towary od chwili ich pierwszego wejścia do magazynu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]