---
title: Dodatek Widoczność magazynu — omówienie
description: W tym artykule wyjaśniono, czym jest dodatek Widoczność magazynu i jakie są jego funkcje.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dd790bcaada0c1a05e46b4edacaa31fc4e15be92
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762815"
---
# <a name="inventory-visibility-add-in-overview"></a>Dodatek Widoczność magazynu — omówienie

[!include [banner](../includes/banner.md)]

Dodatek Inventory Visibility Add-in (nazywany również *Widoczność magazynu*) zapewnia niezależną i wysoce skalowalną mikrousługę, która umożliwia księgowanie bieżących zmian w inwentarzu w czasie rzeczywistym oraz śledzenie widoczności we wszystkich źródłach danych i kanałach. Zapewnia platformę, która pozwala zarządzać magazynem globalnym za pomocą funkcji, które obejmują następującą listę (ale nie tylko):

- Centralnie śledzić ostatni stan zapasów (np. dostępne, zamówione, zakupione, w drodze, zwracane i tranzytowane) we wszystkich źródłach danych, magazynach i lokalizacjach przez połączenie Supply Chain Management lub innych źródeł danych logistyki (takich jak systemy zarządzania zamówieniami, systemy \[ERP\] planowania zasobów przedsiębiorstwa firmy, systemy punkt sprzedaży \[POS\] i systemy zarządzania magazynem) z usługą widoczności zapasów.
- Uzyskiwanie kwerend o dostępności zapasów i niedoborów w magazynie oraz uzyskiwanie natychmiastowej odpowiedzi przez bezpośrednie wywoływanie usługi widoczności zapasów.
- Unikaj nadmiernej sprzedaży, zwłaszcza gdy Twoje zapotrzebowanie pochodzi z różnych kanałów, dokonując miękkich rezerwacji w czasie rzeczywistym w usłudze widoczności magazynu.
- Lepiej zarządzać oczekiwanymi zamówieniami i oczekiwaniami klientów, zapewniając aktualne lub następne dostępne daty, tak aby funkcja dostępnych i dostępnych (ATP) funkcji obsługi zamówień umożliwiała obliczanie oczekiwanych dat realizacji zamówień.

## <a name="extensibility"></a>Możliwości rozszerzania

Usługa widoczność zapasów jest bardzo rozszerzalna, ponieważ wprowadzanie i dane wyjściowe nie są ograniczone do aplikacji firmy Microsoft. Systemy zewnętrzne mogą uzyskać dostęp do usługi za pomocą interfejsów API (RESTful application programming interfaces). Oprócz korzystania z gotowych mapowań, które są dostępne dla źródła danych i wymiarów Supply Chain Management, można zintegrować Widoczność zapasów z wieloma systemami innych firm, konfigurując dodatkowe źródła danych, miary stanów zapasów (określane jako *miary fizyczne* w usłudze widoczności magazynu) oraz wymiary zapasów za pośrednictwem aplikacji konfiguracyjnej. W ten sposób możesz elastycznie wyszukiwać i zmieniać wiele źródeł danych oraz predefiniowane wymiary zapasów.

Ponadto dzięki wbudowanemu widoczności zapasów Microsoft Dataverse jego dane mogą służyć do kompilowania i integracji z systemem Power Apps. Możesz również użyć usługi Power BI do tworzenia niestandardowych pulpitów nawigacyjnych spełniających wymagania biznesowe.

## <a name="scalability"></a>Skalowalność

Usługa Widoczność zapasów może być skalowana w górę lub w dół, w zależności od objętości danych. Interfejs skalowalności jest w większości bezproblemowy i jest wykonywany przez zespół platform firmy Microsoft w oparciu o automatyczne wykrywanie i ocenianie ilości danych transakcji.

Na poniższej ilustracji przedstawiono architekturę widoczności zapasów.

[<img src="media/inventory-visibility-architecture.png" alt="Inventory Visibility architecture." title="Architektura widoczności zasobów" width="720" />](media/inventory-visibility-architecture.png)

## <a name="feature-highlights"></a>Najważniejsze cechy

### <a name="get-a-global-view-of-real-time-inventory"></a>Uzyskiwanie widoku globalnego zapasów w czasie rzeczywistym

Widoczność zapasów zapewnia, że użytkownik ma dostęp do naj aktualnej ilości zapasów we wszystkich kanałach, lokalizacjach i magazynach. W większości przypadków korzystania z niego można korzystać w celu obsługi codziennej działalności operacyjnej w każdym momencie, gdy są konieczne rekordy zapasów. Fizyczne dostępne zapasy, sprzedane ilości oraz zakupione ilości są dostępne z pudełka. Można również skonfigurować inne miary magazynu fizycznego (takie jak zwrócone, tranzytowe i zaksięgowane dane), aby uzyskać te szczegóły w czasie rzeczywistym. Widoczność zapasów może efektywnie przetwarzać miliony wpisów zmian zapasów. Te dane można agregować i odzwierciedlać w ostatnich ilościach zapasów w usłudze natychmiast, na sekundę lub na minutę, w zależności od interwału, w który są księgowane dane. Więcej informacji zawiera temat [Publiczne interfejsy API widoczności zasobów reklamowych](inventory-visibility-api.md).

### <a name="central-inventory-adjustment"></a>Centralna korekta zapasów

Widoczność zapasów umożliwia systemom zewnętrznym wywołanie interfejsu API w celu zaksięgowania zmian w zapasach. Zmiany zostaną natychmiast wprowadzone w widoczności zapasów. W związku z tym dostępne zapasy są natychmiast odejmowane.

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Rezerwacja programowa w celu uniknięcia zbyt niskiej sprzedaży we wszystkich kanałach zamówień

Rezerwacja *programowa* umożliwia przypisywanie lub oznaczanie określonych ilości w celu realizacji zamówienia lub popytu. Rezerwacja programowa nie ma wpływu na magazyn fizyczny, ale powoduje potrącenie ilości *dostępnej do rezerwacji zapasów* i dostarcza zaktualizowaną ilość dla przyszłego realizacji zamówienia. Ta funkcja jest przydatna, jeśli żądania lub zamówienia sprzedaży wpływają do firmy z jednego lub wielu kanałów lub źródeł danych, które nie są dostępne w systemie planowania zasobów przedsiębiorstwa (ERP).

Jeśli w usłudze widoczności zapasów nie są rezerwowane rezerwacje miękkie, należy czekać na zsynchronizowanie zamówienia i przetworzenie go przez system ERP w celu uzyskania fizycznej aktualizacji ilości zapasów. Ten proces zazwyczaj ma duże opóźnienie. Rezerwacje miękkie są jednak natychmiastowe po każdym wygenerowaniu zamówienia lub zamówienia sprzedaży w kanałach sprzedaży. Dzięki temu zapobiegnie one sytuacji nadwyżek, zapewniając, że zamówienia zakupu nie będą się mieszać ze sobą podczas ostatecznie docierania do systemu ERP. Miękkie rezerwacje zapewniają również, że możesz zrealizować wszystkie obiecane zamówienia. Dzięki temu pomaga spełnić oczekiwania odbiorców i zachować lojalność odbiorców. Więcej informacji zawiera temat [Rezerwacje dodatku Widoczność magazynu](inventory-visibility-reservations.md).

### <a name="immediate-response-of-atp-quantity-and-dates"></a>Natychmiastowa odpowiedź ilości i dat ATP

Wgląd w najbliższe przyszłą prognozowane zapasy (w tym informacje dotyczące podaży, popytu i prognozowanych dostępnych zapasów) jest bardzo ważny, ponieważ pomaga firmie w osiągnięciu następujących celów:

- Zminimalizuj poziomy zapasów, aby zmniejszyć koszty zarządzania zapasami.
- Ułatwienie wewnętrznego przetwarzania zamówień, dzięki czemu sprzedawcy mogą obliczyć terminy wysyłki i dostawy na podstawie dostępności zamawianych produktów.
- Zapewnij przejrzystość, kiedy klienci mogą oczekiwać, że pozycja, której brakuje w magazynie, stanie się dostępna, podając następny dostępny termin.

Funkcja ATP jest łatwe do przyjęcia w codziennych procesach realizacji zamówień. Funkcja ATP, podobnie jak inna oferta widoczności zapasów, jest dostępna *na całym świecie i w czasie rzeczywistym*. Dlatego można skonfigurować wiele formuł obliczania ATP, tak aby zawierały kwerendy dotyczące pełnej dostępności zapasów, które obejmują wszystkie kanały biznesowe i źródła danych. Aby uzyskać więcej informacji, zobacz [Widoczność zapasów — harmonogramy i zmiany dostępnych zapasów oraz dostępność zapasów](inventory-visibility-available-to-promise.md).

### <a name="preallocate-your-stock-to-important-channels-or-customers-with-inventory-allocation"></a>Wstępne przydzielanie zapasów do ważnych kanałów sprzedaży lub odbiorców za pomocą alokacji zapasów

Funkcja alokacji widoczności zapasów umożliwia ochronę i tworzenie charakterystycznych dla zapasów wartościowych zapasów w ważnych kanałach, grupach klientów i lokalizacjach. Po przydzieleniu zapasów zużycie zapasów jest ograniczone do przydzielonej puli, a ilości pozostawione w puli są odejmowane w czasie najbliższym rzeczywistym, tak aby odzwierciedlały ilość wciąż dostępną do zużycia. Więcej informacji zawiera temat [Alokacja zapasów dodatku Widoczność magazynu](inventory-visibility-allocation.md).

### <a name="compatibility-with-wms-items"></a>Zgodność z pozycjami WMS

Firma Microsoft zamierza zintegrować ją z procesami zarządzania magazynem (WMS), dzięki czemu pracownicy WMS mogą również korzystać z zalet usługi widoczności zapasów. Zgodnie z wydaniem 2022 grupy czynności 1 (wersja publiczna w marcu) usługa magazynowa obsługuje kwerendy dostępnych zapasów dla pozycji WMS i ATP. Funkcja rezerwacji programowej i alokacji będzie obsługiwana dla odbiorców WMS w następnej grupy czynności. Więcej informacji zawiera temat [Obsługa widoczności inwentarza dla pozycji WMS](inventory-visibility-whs-support.md).

Na poniższej ilustracji przedstawiono podsumowanie istniejących funkcji wysokiego poziomu oraz sposób ich pozycji w przepływie danych.

[<img src="media/inventory-visibility-feature-overview.png" alt="Inventory Visibility feature overview." title="Omówienie funkcji widoczności zapasów" width="720" />](media/inventory-visibility-feature-overview.png)

## <a name="licensing"></a>Licencjonowanie

Usługa Widoczność zapasów jest dostępna w następujących wersjach:

- **Dodatek widoczność zapasów dla firmy Microsoft Dynamics 365 Supply Chain Management** — w przypadku firm, które mają prawidłową licencję Supply Chain Management, widoczność zapasów jest dostępna bez dodatkowych kosztów. Widoczność zapasów jest oparta na Microsoft Power Platform, dlatego jest ona ograniczona możliwościami magazynowania Microsoft Power Platform i limitami interfejsu API. Twoja licencja na Supply Chain Management powinna obejmować domyślną pamięć masową i pojemność interfejsu API. Jeśli jest potrzebne więcej możliwości magazynowania i interfejsu API, można zakupić licencję zawodową. Aby uzyskać szczegółowe informacje dotyczące domyślnej alokacji interfejsu API i licencji zawodowej, zobacz temat [Limity i alokacje żądań](/power-platform/admin/api-request-limits-allocations) oraz [Omówienie licencjonowania Microsoft Power Platform](/power-platform/admin/pricing-billing-skus). Dzięki domyślnym alokacjom magazynów i interfejsów API możesz zacząć używać dodatku Widoczność zapasów już dzisiaj. Aby uzyskać szczegółowe informacje o instalacji, zobacz [Instalowanie i konfigurowanie widoczności magazynu](inventory-visibility-setup.md). Jeśli szacowane użycie interfejsu API i magazynu przekracza standardową alokację, można skontaktować się z przedstawicielem handlowym i poprosić go o kontakt z zespołem platform w sprawie wyjątku.
- **Usługa widoczności zapasów jest składnikiem narzędzia IOM** . Ta wersja jest dostępna zarówno dla odbiorców z systemu Intelligent Order Management (IOM), jak i firm, które nie używa Supply Chain Management jako ich systemu ERP. Licencja jest dołączona do pakietu Intelligent Order Management. Aby uzyskać więcej informacji, zajrzyj do omówienia [Intelligent Order Management](/dynamics365/intelligent-order-management/overview).

## <a name="inventory-visibility-terminology"></a>Terminologia dotycząca widoczności zapasów

Podczas pracy z dodatekem Widoczność zapasów ważne jest, aby poznać następujące pojęcia i terminy:

- **Źródło danych** – Źródło danych reprezentuje system, z których pochodzą dane.
- **Wymiary** — wymiary identyfikują charakterystyki produktu. Mogą to być wymiary przechowywania (takie jak miejsce lub magazyn) lub wymiary produktu (takie jak kolor, rozmiar lub styl).
- **Miary fizyczne** – Miary fizyczne to ilości, które mierzą różne stany zapasów, takie jak dostępne, zakupione, zamówione lub sprzedane.
- **Miary obliczone** – Miary obliczane są miarami ilościowymi obliczanych na podstawie zestawu miar fizycznych. Na przykład obliczona miara *Wszystkie dostępne* jest obliczana jako *Dostępne* + *Zakupione* – *Na zamówienie* – *Sprzedane*.
- **Partycja** — partycja definiuje hierarchię sposobu dystrybuowania odebranych danych przez widoczność zapasów. Obecnie domyślną partycją jest lokalizacja i lokalizacja.
- **Hierarchia indeksów** – Hierarchia indeksów dodatkowo definiuje sposób kwerendy zapasów i uzyskiwać wyniki o większej szczegółowości.

Aby uzyskać więcej informacji na temat tych terminów i pojęć, zobacz [Konfiguracja dodatku Widoczność magazynu](inventory-visibility-configuration.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
