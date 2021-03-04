---
title: Zasady konsolidacji wysyłki
description: Ten temat zawiera omówienie funkcji, która zapewnia elastyczną konfigurację zasad konsolidacji wysyłki.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationError, WHSShipConsolidationSetShipment, WHSShipConsolidationPolicySelect, WHSShipPlanningListPage, TMSCarrierGroup, WHSShipConsolidationTemplate, WHSShipConsolidationTemplateApply, WHSShipConsolidationTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: f895b13b2e11d4cb341f80b3cfeb40ed998ccfc4
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654227"
---
# <a name="shipment-consolidation-policies"></a>Zasady konsolidacji wysyłki

Proces konsolidacji wysyłki, który korzysta z zasad konsolidacji wysyłki umożliwia na automatyczną konsolidację wysyłki automatycznego i ręcznego zwalniania do magazynu. Automatyczna konsolidacja, która była dostępna przed wprowadzeniem tej funkcji, miała kodowane pola i opierała się na wartości pola **Konsolidowanie wysyłki podczas zwalniania do magazynu** ustawionej dla magazynu.

Zasady konsolidacji wysyłki są używane dla następujących funkcji:

- Automatyczne zadanie wsadowe typu „zwolnienie do magazynu”
- Polecenie **Zwolnij do magazynu** w zamówieniu sprzedaży lub w zamówieniu przeniesienia
- Dedykowana strona **Zwalnianie do magazynu**
- Polecenie **Zwolnij do magazynu** na stronie **Pulpit planowania wysyłki ładunku**
- Ręczna konsolidacja wysyłki na stronach **konsolidowania wysyłek** i **pulpitu konsolidacji wysyłki**

Przed wprowadzeniem zasad konsolidacji wysyłki funkcja konsolidacji istniała jako ustawienie na poziomie magazynu. Wszystkie zamówienia wszystkich odbiorców z jednego magazynu były traktowane tak, jakby miały takie same wymagania dotyczące konsolidacji. Zasady konsolidacji wysyłki dodają obsługę scenariuszy, w których różne organizacje mają różne wymagania dotyczące konsolidacji wysyłek.

Zapytania służą do identyfikowania zasad konsolidacji wysyłek, które są stosowane, a następnie edytowalny zestaw pól określa sposób grupowania wierszy ładunku na poziomie wysyłki. (Ten wzorzec przypomina wzorzec stosowany przez szablony grupy czynności). Ponadto opcja **Konsoliduj z istniejącymi wysyłkami** została dodana do wszystkich zasad. Jeśli ta opcja jest włączona, procedura *zwalniania do magazynu* wyszukuje wysyłki do konsolidacji, wyszukując je wśród istniejących wysyłek, które zostały utworzone na podstawie tych samych zasad konsolidacji. W takim przypadku system wybierze istniejącą wysyłkę lub ładunek, zamiast tworzyć nowy. System będzie jednak konsolidować tylko z istniejącymi wysyłkami, które mają stan *Otwarte*; wysyłki należące do wydania z użyciem grupy czynności o stanie *Zwolnione* lub wyższym nie będą traktowane jako cele konsolidacji.

Po udostępnieniu zasad konsolidacji wysyłek ustawienie **Konsolidowanie wysyłki podczas zwalniania do magazynu**, które było poprzednio dostępne na stronie konfiguracji **Magazyny**. Aby ułatwić przejście do nowej funkcji konsolidacji wysyłki, funkcja na stronie **Zasady konsolidacji wysyłki** tworzy zasady domyślne, która automatycznie uwzględniają stare ustawienie dla istniejących magazynów. Po utworzeniu zasad domyślnych ustawienie **Konsolidowanie wysyłki podczas zwalniania do magazynu** na stronie konfiguracji **Magazyny** nie będzie już brane pod uwagę.

Za pomocą strony **zwalniania do magazynu** można ręcznie zastępować odpowiednie zasady konsolidacji w taki sam sposób jak w przypadku zastępowania zasad realizacji.

Można korzystać z polecenia **Zwolnij \> Zwolnij do magazynu** na stronie **Pulpit planowania wysyłki ładunku**, aby tworzyć ładunki wychodzące oparte na wierszach zamówień sprzedaży i zamówień przeniesienia przed dokonaniem zwolnienia do magazynu. Te ładunki używają tej samej logiki konsolidacji, która została wprowadzona razem z konsolidacją zasad wysyłki.

Strona **pulpitu konsolidacji wysyłki** służy do konsolidowania istniejących wysyłek, które nie zostały jeszcze potwierdzone, ale zostały już zwolnione do magazynu. Ta funkcja obsługuje scenariusze, w których proces automatycznego zwalniania z własną konsolidacją wysyłek jest uruchamiany wiele razy dziennie, ale potencjalne dodatkowe konsolidacje są określane ręcznie, zanim wysyłka do przewoźników zakończy się w trakcie procesu potwierdzania. Ta funkcja umożliwia konsolidowanie wysyłek wychodzących, które są tworzone na podstawie wierszy zamówień sprzedaży lub zamówień przeniesienia, w dowolnym momencie po zwolnieniu wysyłek do magazynu, ale przed ich potwierdzeniem.

Strona **pulpitu konsolidacji wysyłki** działa jak pulpit kompilowania ładunku, na którym można jednocześnie ocenić wiele wysyłek i przypisać zamówienie nieskonsolidowane do konkretnej wysyłki. Szablony konsolidacji wysyłki można stosować w celu wielokrotnego oceniania proponowanych konsolidacji i ich potwierdzania. Niektóre reguły są implementowane w celu zapobiegania nieautoryzowanej konsolidacji i ostrzegania o możliwych błędach.

## <a name="overview-of-new-functionality"></a>Omówienie nowych funkcji

W tej sekcji opisano strony, polecenia i funkcje, które są zmieniane lub dodawane podczas włączania i używania funkcji *zasad konsolidacji wysyłki*.

### <a name="shipment-consolidation-policies-page"></a>Strona Zasady konsolidacji wysyłki

Zasady są zróżnicowane według typu zlecenia pracy. Typ **Zamówienia sprzedaży** reprezentuje wysyłki _zamówień sprzedaży_, a typ **Zamówienia przeniesienia** reprezentuje wysyłki _przeniesienia wydania_.

Każde zasady konsolidacji wysyłki mają zapytanie określające, kiedy jest stosowane, oraz identyfikator sekwencji określający kolejność wykonywania. Konsolidacja jest stosowana dla każdej unikatowej kombinacji wybranych pól. Dodatkowy podawany parametr jest używany do konsolidacji z istniejącymi (otwartymi) wysyłkami. Zasady są oceniane i stosowane przy każdym tworzeniu nowej wysyłki (przed przetworzeniem grupy czynności).

Jeśli w zasadach brakuje wymaganych pól lub jeśli zawierają one niedozwolone pola, zasady są oznaczane jako nieprawidłowe w sekcji **Wybrane**. Listy pól obowiązkowych i niedozwolonych są kodowane na stałe i mogą zostać rozszerzone.

Poniższa lista zawiera pola obowiązkowe. Ponieważ wysyłki są zawsze dzielone na podstawie tych pól, nie można grupować wielu wysyłek o różnych wartościach dla tych pól.

- Zamówienia sprzedaży:

    - **Identyfikator konta:** _WHSShipmentTable.AccountNum_
    - **Odbiorca dostawy:** _WHSShipmentTable.DeliveryName_
    - **Adres pocztowy (RecId):** _WHSShipmentTable.DeliveryPostalAddress_
    - **Magazyn:** _WHSShipmentTable.InventLocationId_

- W przypadku zamówień przeniesienia:

    - **Z magazynu:** _InventTransferTable.InventLocationIdFrom_
    - **Do magazynu:** _InventTransferTable.InventLocationIdTo_

Poniższe pola są niedostępne dla wszystkich typów dokumentów. Te pola nie są widoczne w interfejsie użytkownika i nie mogą być używane do konsolidacji.

- **Identyfikator wysyłki:** _WHSShipmentTable.ShipmentId_
- **Stan:** _WHSShipmentTable.ShipmentStatus_
- **Zasady konsolidacji wysyłki:** _WHSShipmentTable.ShipConsolidationPolicyName_
- **Typ transakcji pracy:** _WHSShipmentTable.WorkTransType_
- **Identyfikator grupy czynności:** _WHSShipmentTable.WaveId_
- **Identyfikator ładunku:** _WHSShipmentTable.LoadId_
- **Identyfikator wysyłki:** _WHSLoadLine.ShipmentId_
- **Identyfikator ładunku:** _WHSLoadLine.LoadId_

Domyślnie podczas tworzenia zasad jako pola konsolidacji jest używany zestaw pól obowiązkowych. Można jednak zmodyfikować listę, używając przycisków strzałki w lewo i strzałki w prawo. (Proces przypomina proces wybierania metod w szablonach grupy czynności).

Wartości wybrane przez użytkowników dla tych pól będą używane dla wszystkich nowo utworzonych wysyłek lub zostaną dodane do istniejących wysyłek podczas konsolidacji z tymi wysyłkami. Jeśli dwie wysyłki mają taką samą wartość dla pola wybranego do konsolidacji tych wysyłek, wysyłki są konsolidowane. Ta sama zasada dotyczy wszystkich wybranych kolejnych pól konsolidacji. Jeśli wartości różnią się, druga wysyłka jest odrzucana i zostanie wybrana dla nowej wysyłki. Zautomatyzowany proces konsolidacji składa się z tworzenia wszystkich unikatowych kombinacji wartości pól konsolidacji wysyłki, a następnie przypisywania wysyłki do odpowiedniej kombinacji.

Niewybrane pola są ignorowane podczas procesu konsolidowania. Jeśli dwie wysyłki mają różne wartości dla niezaznaczonego pola, pole jest czyszczone (czyli ustawiane na wartość pustą). Jeśli obydwie wysyłki mają tę samą wartość dla niezaznaczonego pola, pole jest wypełniane.

Lista pól konsolidacji (czyli pól, które zostaną wyczyszczone, jeśli mają inne wartości) jest zakodowana na stałe. Lista zawiera wszystkie pola, które są inicjowane z poziomu wiersza zamówienia sprzedaży lub zamówienia przeniesienia podczas tworzenia nowej wysyłki. Mówiąc, jeśli pole nie zostało zainicjowane z wiersza zamówienia sprzedaży lub zamówienia przeniesienia, jest ignorowane podczas dodawania nowych danych do istniejącej wysyłki.

### <a name="release-to-warehouse-page"></a>Strona zwalniania do magazynu

- Nowe pole w dolnej siatce pokazuje zastosowane zasady konsolidacji.
- Nowy przycisk umożliwia ręczne wybieranie i/lub zastępowanie zasad konsolidacji.

### <a name="release-to-warehouse-command-on-the-load-planning-workbench-page"></a>Polecenie Zwolnij do magazynu na stronie Pulpit planowania wysyłki ładunku

- Logika została dostosowana tak, aby korzystała z zastosowanych zasad konsolidacji.
- Wysyłki są teraz konsolidowane tylko w ramach pojedynczego ładunku.

### <a name="consolidate-shipments-page"></a>Strona konsolidowania wysyłek

- Wyszukiwanie podobnych wysyłek (czyli kandydatów do konsolidacji) zostało zmienione tak, aby były używane pola wybrane w zasadach konsolidacji wysyłki.
- Pola, które mają różne wartości w różnych wysyłkach, są teraz ustawiane jako puste. (Poprzednio były używane wartości z wybranej wysyłki „podstawowej”).

### <a name="shipment-consolidation-workbench-page"></a>Strona Pulpit konsolidacji wysyłki

- Nowa funkcja replikuje proces konsolidacji ręcznej w większej skali.
- Można teraz otworzyć tę stronę z poziomu menu **zwalniania do magazynu** w module **Zarządzanie magazynem**.
- Algorytm analizuje istniejące wysyłki, które nie zostały jeszcze wysłane. Następnie proponuje on konsolidację na podstawie pól wybranych w zasadach konsolidacji.

## <a name="comparison-of-functionality"></a>Porównanie funkcji

Poniższa tabela zawiera podsumowanie sposobu działania konsolidacji wysyłek, gdy zasady konsolidacji wysyłek są i nie są używane.

| Bez zasad konsolidacji wysyłki | Z zasadami konsolidacji wysyłki |
|---|----|
| Nie dotyczy | Wysyłki sprzedaży lub przeniesienia wybrane do konsolidacji muszą mieć takie same zasady konsolidacji jak tworzona wysyłka albo muszą być przypisane do otwartej wysyłki (jeśli opcja **konsolidowania z istniejącymi wysyłkami** została włączona). |
| Procedura *Zwolnij do magazynu* nie wyszukuje wysyłki do konsolidacji wśród istniejących wysyłek. Podczas wyszukiwania wysyłki do konsolidacji są uwzględniane tylko wysyłki utworzone przez bieżące wystąpienie procedury *zwalniania do magazynu*. | Jeśli opcja **konsolidowania z istniejącymi wysyłkami** została włączona dla aktualnie używanych zasad konsolidacji, procedura *Zwolnij do magazynu* wyszukuje między istniejącymi wysyłkami, które zostały utworzone na podstawie tych samych zasad konsolidacji, aby znaleźć wysyłkę do konsolidacji. Z tego względu, jeśli istnieją dwie zasady, wysyłka utworzona na podstawie zasad 2 nigdy nie będzie konsolidowana z wysyłką utworzoną na podstawie zasad 1. |
| Nie dotyczy | Jeśli lista pól zasad konsolidacji jest pusta lub jeśli nie można odnaleźć zasad, dla każdego wiersza zamówienia sprzedaży lub zamówienia przeniesienia zostanie utworzona nowa wysyłka. |
| W poniższym polu konsolidacji zdefiniowano unikatową kombinację wartości używanych do konsolidowania wysyłek dla *wiersza przeniesienia*. (Wszystkie pozostałe pola są ignorowane).<ul><li>Identyfikator zamówienia (OrderNum)</li></ul> | W poniższych polach konsolidacji zdefiniowano unikatową kombinację wartości używanych do konsolidowania wysyłek dla *wiersza przeniesienia*. (Wszystkie pozostałe pola są ignorowane).<ul><li>Identyfikator zamówienia (OrderNum)</li><li>Odbiorca dostawy (DeliveryName)</li><li>Adres pocztowy (DeliveryPostalAddress)</li><li>Kod kraju ISO (CountryRegionISOCode)</li><li>Adres (Address)</li><li>Oddział (InventSiteId)</li><li>Magazyn (InventLocationId)</li><li>Przewoźnik (CarrierCode)</li><li>Usługa przewozowa (CarrierServiceCode)</li><li>Metoda dostawy (ModeCode)</li><li>Grupa przewoźnika (CarrierGroupCode)</li><li>Warunki dostawy (DlvTermId)</li></ul>Te pola są jedynymi polami dostępnymi i inicjowanymi podczas tworzenia nowej wysyłki. |
| W poniższych polach konsolidacji zdefiniowano unikatową kombinację wartości używanych do konsolidowania wysyłek dla *wiersza sprzedaży*. (Wszystkie pozostałe pola są ignorowane).<ul><li>Identyfikator zamówienia (OrderNum)</li><li>Odwołanie odbiorcy (CustomerRef)</li><li>Zapotrzebowanie odbiorcy (CustomerReq)</li><li>Warunki dostawy (DlvTermId)</li></ul> | W poniższych polach konsolidacji zdefiniowano unikatową kombinację wartości używanych do konsolidowania wysyłek dla *wiersza sprzedaży*. (Wszystkie pozostałe pola są ignorowane).<ul><li>Identyfikator zamówienia (OrderNum)</li><li>Identyfikator konta (AccountNum)</li><li>Odbiorca dostawy (DeliveryName)</li><li>Adres pocztowy (DeliveryPostalAddress)</li><li>Kod kraju ISO (CountryRegionISOCode)</li><li>Adres (Address)</li><li>Oddział (InventSiteId)</li><li>Magazyn (InventLocationId)</li><li>Przewoźnik (CarrierCode)</li><li>Usługa przewozowa (CarrierServiceCode)</li><li>Metoda dostawy (ModeCode)</li><li>Grupa przewoźnika (CarrierGroupCode)</li><li>Identyfikator brokera (BrokerCode)</li><li>Kierunek (LoadDirection)</li><li>Warunki dostawy (DlvTermId)</li><li>Odwołanie odbiorcy (CustomerRef)</li><li>Zapotrzebowanie odbiorcy (CustomerReq)</li></ul>Te pola są jedynymi polami dostępnymi i inicjowanymi podczas tworzenia nowej wysyłki. |
| Nie dotyczy | Następujące pola konsolidacji są wymagane dla *wiersza sprzedaży* i nie można ich usunąć:<ul><li>Identyfikator konta (AccountNum)</li><li>Odbiorca dostawy (DeliveryName)</li><li>Adres pocztowy (DeliveryPostalAddress)</li><li>Magazyn (InventLocationId)</li></ul>Domyślnie pola te będą przypisywane podczas tworzenia nowych zasad. Nie można ich usunąć. |
| Procedura *zwalniania ładunków do magazynu* na stronie **pulpitu planowania wysyłki ładunku** używa własnego, osobnego kodu do tworzenia wysyłek i grup czynności. | Zasady konsolidacji wysyłki są stosowane w celu określenia, które pola mają być oceniane w celu konsolidacji. Wysyłki są konsolidowane tylko w ramach pojedynczego ładunku. |
| Użytkownik ręcznie wybiera opcję **Konsoliduj wysyłki** na stronie **Wszystkie wysyłki**, a następnie wybiera docelową wysyłkę „podstawową”. Filtr zasugeruje wszystkie istniejące wysyłki, które mają odpowiadające wartości w kilku polach kluczy. | Użytkownik ręcznie wybiera opcję **Konsoliduj wysyłki** na stronie **Wszystkie wysyłki**, a następnie wybiera docelową wysyłkę „podstawową”. System będzie sugerować inne istniejące wysyłki, dopasowując wartości kilku pól klucza skonfigurowane dla odpowiednich zasad konsolidacji wysyłki. |
| Za pomocą polecenia **Konsoliduj wysyłki** na stronie **Wszystkie wysyłki** można wybrać tylko jedną wysyłkę. | Strona **pulpitu konsolidacji wysyłki** ułatwia znajdowanie zestawu wysyłek, które nie są jeszcze w stanie oznaczającym wysłanie. Wysyłki te są analizowane na podstawie kilku pól klucza skonfigurowanych w zasadach konsolidacji wysyłki. Wszystkie wysyłki, dla których wartości tych pól są zgodne, są sugerowane do konsolidacji.<p>Konsolidację można obsługiwać ręcznie, usuwając wysyłki z sugerowanych konsolidacji i/lub dodając do nich wysyłki. Może wystąpić kilka typów błędów, ale niektóre z nich można nadpisać.</p> |
| **Uwaga do projektu**: procedura *Automatyczne zwalnianie zamówień sprzedaży do magazynu* dzieli wiersze sprzedaży na grupy. Każda grupa ma własną unikatową wartość **ReleaseToWarehouseId** i jest przetwarzana oddzielnie w ramach procedury *zwalniania do magazynu*. Ta procedura umożliwia utworzenie nowej pracy niezależnie od konfiguracji podziału pracy. | **Uwaga do projektu**: procedura *Automatyczne zwalnianie zamówień sprzedaży do magazynu* przypisuje tę samą wartość **ReleaseToWarehouseId** do wszystkich przetwarzanych wierszy sprzedaży. Wszystkie wiersze sprzedaży są jednocześnie przetwarzane w ramach procedury *zwalniania do magazynu*. Aby zagwarantować wcześniejsze zachowanie, należy skonfigurować podział pracy dla każdego identyfikatora wysyłki. |

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]