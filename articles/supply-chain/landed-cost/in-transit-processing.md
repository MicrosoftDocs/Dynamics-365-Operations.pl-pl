---
title: Przetwarzanie towarów w transporcie
description: W tym temacie opisano, jak pracować z zamówieniami towarów w drodze. Jeśli dla zamówienia lub podróży zostanie ustawione użycie przetwarzania towarów w drodze, towary mogą zostać zafakturowane przed ich otrzymaniem do magazynu w celu zużycia.
author: Weijiesa
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DeliveryTerms, InventLocation, InventPosting, ITMGoodsInTransitOrder, ITMTableListPage, ITMTable, ITMContainersListPage, ITMContainers, ITMFolioTableListPage, ITMFolioTable, ITMGoodsInTransitOrderEditLines, SysOperationTemplateForm, WHSRFMenuItem, WHSLocDirTable, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8df07c7c94cf64b0e4cf1def794270e176241b5f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694663"
---
# <a name="goods-in-transit-processing"></a>Przetwarzanie towarów w transporcie

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, jak pracować z zamówieniami towarów w drodze. Ten typ zamówienia jest używany tylko przez moduł **Koszt z wyładunkiem**. Gdy zamówienie lub podróż są skonfigurowane do przetwarzania towarów w tranzycie, nie musisz czekać, aż towary znajdą się w magazynie, zanim będzie można je zafakturować. Natomiast towary są fakturowane, gdy opuszczają magazyn lub port pochodzenia dostawcy i koszty finansowe są uznawane w momencie rozpoczynania podróży. Ta funkcja umożliwia prawidłowe przenoszenie własności zapasów, ponieważ towary często stają się właściwością organizacji użytkownika, gdy opuszczają port wysyłki.

W przypadku korzystania z zamówień tranzytu towary zaktualizowane finansowo są odbierane w magazynie tymczasowym, który jest nazywany magazynem towarów w drodze. Towary pozostają wówczas w tym magazynie, dopóki nie zostaną odebrane w ostatecznym magazynie docelowym (to jest magazynie określonym w wierszu zakupu). Nie można ich usunąć ręcznie.

Dopóki towary są w tranzycie, nie są dostępne w magazynie i nie można ich wybrać z magazynu w celu dostarczenia. Można jednak wyświetlić towary w drodze. Możesz również użyć towarów do planowania głównego. W takim przypadku należy użyć potwierdzonej daty dostawy w wierszu zamówienia zakupu jako przewidywanej daty, kiedy zapasy będą dostępne do użycia.

W poniższych sekcjach opisano konfigurację wymaganą do przetwarzania zapasów i podróży przy użyciu koncepcji i funkcji towarów w drodze.

## <a name="terms-of-delivery"></a>Warunki dostawy

Włączenie modułu **Koszt z wyładunkiem** pozwala na obsługę funkcji *towarów w drodze*, dzięki którym są realizowane standardowe warunki dostawy.

Jeśli dla odpowiednich rekordów warunków dostawy dla opcji **Zarządzania towarami w drodze** jest ustawiona wartość *Tak*, towary są umieszczane w magazynie towarów w drodze. Ta akcja jest wyzwalana tylko wtedy, gdy przyjęcie na magazyn nie jest przetwarzane przed przetworzeniem faktury. Gdy warunki dostawy zamówienia są ustawione na używanie towarów w tranzycie, użytkownicy nie mogą już księgować dokumentu przyjęcia produktów dla zamówienia zakupu. W razie próby wystąpi błąd. Komunikat o błędzie oznacza, że muszą korzystać z funkcji towarów w drodze, aby kontynuować.

Aby pracować z informacjami o warunkach dostawy dla towarów w drodze, przejdź do **Zaopatrzenie i sourcing \> Konfiguracja \> Dystrybucja \> Warunki dostawy**. W poniższej tabeli opisano pola, które moduł **Koszt z wyładunkiem** dodaje do strony **Warunki dostawy** w celu obsługi funkcji towarów w drodze. Oba pola znajdują się na skróconej karcie **Ogólne**. Aby uzyskać więcej informacji o innych polach na tej stronie, zobacz [Warunki dostawy (formularz)](/dynamicsax-2012//terms-of-delivery-form).

| Pole | opis |
|---|---|
| Obowiązkowy port wysyłki | Ustaw tę opcję na wartość *Tak*, jeśli port wysyłki jest wymagany, gdy mają zastosowanie warunki dostawy. |
| Zarządzanie towarem w drodze | Ustaw tę opcję na wartość *Tak*, aby używać zarządzania towarami w drodze, gdy mają zastosowanie warunki dostawy. |

## <a name="warehouses-for-goods-in-transit-and-under-delivery"></a>Magazyny towarów w drodze i niedoborów

Włączenie modułu **Koszt z wyładunkiem** pozwala na fakturowanie zamówień zakupu w *magazynie* towarów w drodze.

Koszt ziemny powoduje dodanie dwóch nowych typów magazynu: *towarów w drodze* i *niedoboru w dostawie*. Magazyny obu typów można wybrać jako magazyny domyślne. Pomyślne przetworzenie zamówień na towary w drodze wymaga skonfigurowania magazynu towarów w drodze oraz magazynu pod dostawy na stronie **Magazyny**. Następnie dla każdego magazynu domyślnego, który będzie używany z kosztami z wyładunkiem i towarami w drodze, dla dostępnych magazynów każdego typu muszą być wybrane magazyny towarów w drodze oraz niedobory w dostawie.

Magazyn towarów w drodze będzie powiązany z magazynem *towarów w drodze*, a ten magazyn będzie używany do przetwarzania towarów na zamówieniach towarów w drodze przed ich otrzymaniem w magazynie docelowym. Na ogół wystarczy jeden magazyn towarów w drodze do każdego z nich, jeśli jedynymi wymiarami magazynowymi używanymi do zarządzania zapasami są: Miejsce i Magazyn. Jeśli używany jest również wymiar magazynowy Lokalizacja, należy skonfigurować magazyn towarów w tranzycie dla każdej kombinacji oddziału i magazynu, aby można było również określić domyślną lokalizację.

Aby pracować z ustawieniami towarów w drodze dla magazynów, przejdź do **Zarządzanie zapasami \> Konfiguracja \> Podział magazynu \> Magazyny**. W poniższej tabeli opisano pola, które moduł **Koszt z wyładunkiem** dodaje do strony **Magazyny** w celu obsługi funkcji towarów w drodze. Oba pola znajdują się na skróconej karcie **Ogólne**. Aby uzyskać informacje o innych polach na stronie, zobacz [Magazyny (formularz)](/dynamicsax-2012//warehouses-form).

| Pole | opis |
|---|---|
| Magazyn towaru w drodze | Określ magazyn towarów w drodze, który jest powiązany z magazynem głównym. |
| Magazyn dostawy z niedoborem | Określ magazyn towarów z niedoborem w dostawie, który jest powiązany z magazynem głównym. |

## <a name="posting-rules-for-landed-cost"></a>Reguły księgowania kosztu z wyładunkiem

Koszt z wyładunkiem powoduje dodanie dwóch nowych reguł księgowania, które można konfigurować. Te reguły księgowania są używane do finansowego księgowania kwot faktur zamówień zakupu w celu określenia własności towarów po opuszczeniu punktu pochodzenia. Ten proces zastępuje pojęcie *towarów odebranych, ale niezafakturowanych*, ponieważ towary są fakturowane przed ich otrzymaniem. <!-- KFM: Add a link to the related scenario when available. -->

Aby pracować z profilami księgowania, przejdź **Zarządzanie zapasami \> Konfiguracja \> Księgowanie \> Księgowanie**. Na karcie **Zamówienie zakupu** są dostępne następujące nowe reguły księgowania:

- **Koszt z wyładunkiem, towary w drodze** — umożliwia określenie reguł księgowania zarządzania towarami w drodze.
- **Koszt z wyładunkiem, naliczenie opłat kosztowych** — umożliwia określenie reguł księgowania naliczania na koncie opłat.

## <a name="goods-in-transit-orders"></a>Zamówienia towaru w drodze

Zamówienia towarów w drodze można przeglądać bezpośrednio w module **Koszty z wyładunkiem**. Zamówienia towarów w drodze można przetwarzać bezpośrednio ze strony **Zamówienia towarów w drodze**. Można również przejść w podróż, która jest skojarzona z zamówieniami na towary w drodze, i przetworzyć całą podróż, kontener wysyłkowy lub folio. Podczas fakturowania podróży i tworzenia zamówień towarów w tranzycie dla każdej kombinacji zapasów i wymiarów magazynowych skojarzonych z wierszem zamówienia zakupu tworzone jest nowe zamówienie towarów w drodze.

Aby zarządzać towarami w tranzycie, Koszt wyładunku wykorzystuje dwuetapową procedurę:

1. Pozycja jest odbierana podczas przetwarzania faktury magazynowej i ma stan *W drodz* e.
1. Zamówienie towarów w drodze jest przetwarzane na stronie **Zamówienia towarów w drodze**, a następnie odbierane w magazynie określonym w zamówieniu zakupu. W tym momencie stan jest zmieniany na *Odebrano*.

Aby pracować z zamówieniami na towary w drodze, przejdź do **Koszt z wyładunkiem \> Zadania okresowe \> Zamówienia towarów w drodze**.

## <a name="receiving-stock-from-the-goods-in-transit-warehouse"></a>Zapasy odbierane z magazynu towarów w drodze

W zależności od konfiguracji systemu towary mogą być odbierane z zamówienia w drodze na wiele sposobów.

### <a name="in-transit-receiving"></a>Przyjęcie w drodze

Odbiór w drodze można wykonać na dowolnej z następujących stron:

- Na stronie **Zamówienia na towary w drodze** zaznacz wiersz, a następnie w okienku akcji wybierz opcję **Odbierz**.
- Na stronie **Wszystkie podróży** wybierz lub otwórz podróż. Następnie w okienku akcji, na karcie **Zarządzaj**, w grupie **Towary w drodze** wybierz pozycję **Odbierz towary w drodze**.
- Na stronie **Wszystkie kontenery wysyłkowe** wybierz lub otwórz kontener wysyłkowy. Następnie w okienku akcji, na karcie **Zarządzaj**, w grupie **Towary w drodze** wybierz pozycję **Odbierz towary w drodze**.
- Na stronie **Wszystkie folio** wybierz lub otwórz folio. Następnie w okienku akcji, na karcie **Zarządzaj**, w grupie **Towary w drodze** wybierz pozycję **Odbierz towary w drodze**.

> [!NOTE]
> Odbiór w drodze jest zwykle używany w sytuacjach, gdy lokalizacje i śledzenie partii / serii nie są używane.

### <a name="arrival-journal"></a>Arkusz przyjęcia

Towary można również odbierać, tworząc arkusz przybycia. Arkusz przybycia można utworzyć bezpośrednio ze strony podróży. Najlepsze rozwiązania określone przez organizację określają, czy arkusz przybycia jest używany do odbierania towarów.

1. Otwórz podróż, kontener lub folio.
1. W okienku akcji na karcie **Zarządzaj** w grupie **Funkcje** wybierz opcję **Utwórz arkusz przybycia**.
1. W wyświetlonym oknie dialogowym **Utwórz arkusz przybycia** można ustawić następujące wartości:

    - **Zaiicjuj ilość** – Ustaw dla tej opcji wartość *Tak*, aby ustawić ilość z ilości w drodze. Jeśli ta opcja ma wartość *Nie*, z wierszy towarów w drodze nie jest ustawiana żadna domyślna ilość.
    - **Utwórz z towarów w drodze** — Ustaw dla tej opcji wartość *Tak*, aby dla wybranej podróży, kontenera lub folio pobrane zostały ilości z wybranych wierszy w drodze.
    - **Utwórz z wierszy zamówienia** – Ustaw tę opcję na wartość *Tak*, aby ustawić domyślną ilość w arkuszu przybycia z wierszy zamówienia zakupu. Domyślną ilość w arkuszu przybycia można ustawić w ten sposób tylko wtedy, gdy ilość w wierszu zamówienia zakupu odpowiada ilości w zamówieniu towarów w drodze.

1. Przetwarzaj arkusz przyjęcia towaru zgodnie z opisem w [Rejestrowanie przychodów towaru na arkuszu przyjęć towarów](/dynamicsax-2012/appuser-itpro/register-item-receipts-with-an-item-arrival-journal).

> [!NOTE]
> Arkusz przyjęć jest zwykle używany w sytuacjach, w których używane są lokalizacje i śledzenie partii / serii, ale zarządzanie magazynem nie jest używane.
>
> Jeśli lokalizacja odłoży zostanie określona w arkuszu przyjęcia, w wierszach zamówienia nie należy określać domyślnych lokalizacji przyjęcia.

## <a name="warehouse-management"></a>Zarządzanie magazynem

Po włączeniu modułu **Koszty z wyładunkiem** kilka stron modułu **Zarządzanie magazynem** jest modyfikowanych w taki sposób, aby przetwarzanie zamówień (w szczególności przetwarzanie towarów w drodze) było wykonywane za pośrednictwem modułu **Koszty z wyładunkiem**. W tej sekcji przedstawiono pola i procesy dodane do modułu **Zarządzanie magazynem**.

### <a name="mobile-device-menu-items"></a>Elementy menu urządzenia przenośnego

Towary można odbierać za pomocą urządzenia przenośnego, pod warunkiem że menu urządzeń przenośnych i moduł **Zarządzania magazynem** zostały tak ustawione, aby odbierać towary na zamówieniu w drodze. W tej sekcji opisano konfigurację skojarzoną z odbieraniem towarów w drodze.

Aby skonfigurować urządzenia przenośne do przetwarzania towarów w drodze, przejdź do **Zarządzanie magazynem \> Konfiguracja \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.

Koszt z wyładunkiem powoduje dodanie do elementów menu urządzenia przenośnego następujących procesów tworzenia pracy w celu obsługi przetwarzania towarów w drodze:

- Przyjmowanie pozycji towaru w drodze
- Odbieranie i odkładanie pozycji w drodze

Ustawienia konfiguracyjne dla tych procesów są podobne do ustawień dla [procesów przyjmowania zamówień zakupu i odkładania pracy](/dynamicsax-2012/appuser-itpro/configure-mobile-devices-for-warehouse-work). Jednak w procesie *Odbierania i odłożenia towarów w drodze* jest również dodano następujące pole.

- **Włącz zakończenie kontenera wysyłkowego** — jeśli ta opcja ma wartość *Tak*, po zakończeniu pracy odłożenia aplikacja Warehouse Management udostępni dodatkową opcję o nazwie **Kontener wysyłkowy zakończony**. Po wybraniu tej opcji pracownik zostanie poproszony o potwierdzenie zakończenia kontenera. W tym momencie wszystkie krótkie przychody będą przetwarzane jako transakcje.

### <a name="location-directives"></a>Dyrektywy lokalizacji

Koszt z wyładunkiem powoduje dodanie nowego typu zlecenia pracy o nazwie *Towary w drodze* do strony **Dyrektywy lokalizacji**. Ten typ zlecenia należy konfigurować w taki sam sposób, jak [typy zlecenia dla zamówienia zakupu](/dynamicsax-2012/appuser-itpro/create-a-work-template).

### <a name="work-templates"></a>Szablony pracy

W tej sekcji opisano funkcje, które moduł **Koszt z wyładunkiem** dodaje do szablonów pracy.

#### <a name="goods-in-transit-work-order-type"></a>Zlecenie pracy typu Towary w tranzycie

Koszt z wyładunkiem powoduje dodanie nowego typu zlecenia pracy o nazwie *Towary w drodze* do strony **Szablony pracy**. Ten typ zlecenia należy konfigurować w taki sam sposób, jak [szablony pracy dla zamówienia zakupu](/dynamicsax-2012/appuser-itpro/create-a-work-template).

#### <a name="work-header-breaks"></a>Podziały nagłówka pracy

Szablony pracy, które mają typ zlecenia pracy *Towary w tranzycie* można skonfigurować do podziału nagłówków pracy. Na stronie **Szablony pracy** wykonaj jedną z następujących czynności:

- Na karcie **Ogólne** dla szablonu ustaw maksymalne wartości nagłówka pracy. Te wartości maksymalne działają w taki sam sposób, jak w przypadku szablonów pracy zamówienia zakupu. (Aby uzyskać więcej informacji, zobacz [Szablony pracy zamówienia zakupu](/dynamicsax-2012/appuser-itpro/create-a-work-template)).
- Przycisk **Podziały nagłówka pracy** umożliwia definiowanie czasu, w którym system powinien tworzyć nowe nagłówki pracy, w oparciu o pola używane do sortowania. Na przykład, aby utworzyć nagłówek pracy dla każdego identyfikatora kontenera, w okienku akcji wybierz opcję **Edytuj zapytanie**, a następnie dodaj pole **Identyfikator zamówienia** na karcie **Sortowanie** w Edytorze zapytań. Pola dodawane do karty **sortowania** są dostępne do wyboru jako *pola grupowania*. Aby skonfigurować pola grupowania, wybierz opcję **Podział nagłówka pracy** w okienku akcji, a następnie w przypadku każdego pola, które ma być używane jako pole grupowania, zaznacz pole wyboru w kolumnie **Grupuj według tego pola**.

Koszt z wyładunkiem [tworzy transakcję nadmiarową](over-under-transactions.md), jeśli zarejestrowana ilość przekracza oryginalną ilość zamówienia. Po zakończeniu nagłówka pracy system aktualizuje stan transakcji magazynowych dla ilości zamówienia głównego. Jednak najpierw aktualizuje ilość, która jest połączona z transakcją nadmiarową po zakończeniu zakupu zamówienia głównego.

Jeśli anulujesz nagłówek pracy dla transakcji nadmiarowej, która została już zarejestrowana, transakcja nadmiarowa zostanie najpierw zredukowana o anulowaną ilość. Po zmniejszeniu transakcji nadmiarowej do ilości 0 (zero), rekord jest usuwany, a wszelkie dodatkowe ilości są wyrejestrowane względem kwoty zamówienia głównego.
