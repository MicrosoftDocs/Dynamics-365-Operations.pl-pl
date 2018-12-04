---
title: "Przeładunek kompletacyjny ze zleceń produkcyjnych do doków załadunkowych"
description: "W tym temacie opisano sposób zarządzania procesem przeładunku kompletacyjnego materiału, który jest zgłaszany jako gotowy z linii produkcyjnej do doku transportu wychodzącego."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCrossDockOpportunityPolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 62194012cfbe101d19e9de3254afb004da79a562
ms.contentlocale: pl-pl
ms.lasthandoff: 03/08/2018

---

# <a name="cross-docking-from-production-orders-to-outbound-docks"></a>Przeładunek kompletacyjny ze zleceń produkcyjnych do doków załadunkowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób zarządzania procesem przeładunku kompletacyjnego materiału, który jest zgłaszany jako gotowy z linii produkcyjnej do doku transportu wychodzącego.

<a name="introduction"></a>Wprowadzenie
------------

Przeładunek kompletacyjny z produkcji do lokalizacji załadunkowej ma zastosowanie do producentów, którzy wytwarzają duże ilości i w najbardziej korzystnym scenariuszu chcieliby wysyłać wyroby gotowe natychmiast po ich zgłoszeniu jako gotowe z linii produkcyjnych. Celem tego procesu jest wysyłanie produktów do centrów dystrybucji, które fizycznie znajdują się blisko miejsc zapotrzebowania odbiorców, zamiast kumulować zapasy w zakładzie produkcyjnym.

W przypadku, gdy na produkty nie istnieje natychmiastowe zapotrzebowanie, należy je odłożyć do lokalizacji w magazynie w zakładzie produkcyjnym. Proces ten jest znany jako *oportunistyczny przeładunek kompletacyjny*. Wskazuje on, że w przypadku istnienia zapotrzebowania na dostawę produktu należy skorzystać z tej szansy, zamiast odkładać produkt do wewnętrznego składowania.

W poniższym przykładzie pokazano trzy odmiany przepływu, która zaczyna się na końcu linii produkcyjnej (2).

Produkt jest zgłaszany jako gotowy do lokalizacji wyjściowej produkcji (3) i operator wózka widłowego pobiera paletę w tej lokalizacji (3).

-   Jeśli istnieje zaplanowane działanie (6) na przeniesie produktu z produkcji (1) do centrum dystrybucji (7), kierowca ciężarówki zostanie poinstruowany przez system, aby odłożył paletę do lokalizacji przy bramie dokowej (4).
-   Jeśli przyczepa jest już przypisana do bramy dokowej, kierowca ciężarówki zostanie poinstruowany, aby załadował produkt bezpośrednio na przyczepę.
-   Jeśli nie istnieje zaplanowane działanie przeniesienia produktu, operator wózka widłowego zostanie poinstruowany, aby odłożył produkt do lokalizacji w wewnętrznym magazynie (5).

[![oportunistyczny przeładunek kompletacyjny](./media/scenario1.png)](./media/scenario1.png)

## <a name="configure-cross-docking"></a>Konfigurowanie przeładunku kompletacyjnego
Proces przeładunku kompletacyjnego konfiguruje się w **zasadach pracy**. Zasada pracy określa typ zlecenia pracy, lokalizację i produkt. W poniższym przykładzie przeładunek kompletacyjny jest konfigurowany dla produktu X i lokalizacji Y.

#### <a name="work-order-types"></a>Typy zleceń

-   Typ zlecenia pracy: Odłożenie wyrobów gotowych
-   Metoda tworzenia pracy: Przeładunek kompletacyjny
-   Nazwa zasady przeładunku kompletacyjnego: Zamówienia przeniesienia

#### <a name="inventory-locations"></a>Magazyny

-   Magazyn: 51
-   Lokalizacja: Y

#### <a name="products"></a>Produkty

-   Numer towaru: X

Obecnie przeładunek kompletacyjny można konfigurować tylko dla dwóch typów zleceń pracy:

-   Ukończono odkładanie wyrobów
-   Odłożenie produktu ubocznego i produktu towarzyszącego

W **zasadzie przeładunku kompletacyjnego** określasz, które typy dokumentów są stosowane do przeładunku kompletacyjnego. Obecnie jedynym obsługiwanym typem dokumentu jest **Zamówienia przeniesienia**. Poniższy przykład pokazuje konfigurację zasady przeładunku kompletacyjnego.

### <a name="cross-docking-policy-name-transfer-order"></a>Nazwa zasady przeładunku kompletacyjnego: Zamówienie przeniesienia

- Numer kolejny: 10
  -   Typ zlecenia pracy: Wydanie przeniesienia
- Zapotrzebowanie na przeładunek kompletacyjny wymaga lokalizacji: Fałsz
- Strategia przeładunku kompletacyjnego: Data i godzina

### <a name="sequence-number"></a>Numer sekwencyjny

**Numer kolejny** wskazuje priorytet danego typu dokumentu. Obecnie jedynym obsługiwanym typem jest **Wydanie przeniesienia**. W związku z tym numer kolejny stanie się istotny dopiero wtedy, gdy system będzie obsługiwał więcej typów zleceń pracy.

### <a name="cross-docking-policy"></a>Zasada przeładunku kompletacyjnego

Zasada przeładunku kompletacyjnego ustawia także zasadę priorytetyzacji zapotrzebowania na zamówienie przeniesienia. Na przykład jeśli istnieje wiele zamówień przeniesienia na ten sam produkt, planowana data i godzina ustawiona dla ładunku oraz skojarzona z zamówieniem przeniesienia decydują o priorytetach między zamówieniami. Zaplanowaną datę i godzinę można ustawić bezpośrednio w ładunku albo w **harmonogramie terminów** skojarzonym z ładunkiem. Priorytety zależą od strategii przeładunku kompletacyjnego. Obecnie istnieje tylko jedna strategia: **Data i godzina**.

### <a name="cross-docking-demand-requires-location"></a>Zapotrzebowanie na przeładunek kompletacyjny wymaga lokalizacji

W zasadzie przeładunku kompletacyjnego można skonfigurować kryterium powodujące wymóg, aby zamówienia przeniesienia miały przypisaną lokalizację, jeśli mają się kwalifikować do przeładunku kompletacyjnego. To kryterium jest ustawiane w polu **Zapotrzebowanie na przeładunek kompletacyjny wymaga lokalizacji**. Lokalizacja w harmonogramie terminów skojarzonym z ładunkiem służy jako lokalizacja końcowa dla towarów objętych przeładunkiem kompletacyjnym. Lokalizacja końcowa towarów objętych tym przeładunkiem zależy od dyrektywy lokalizacji dla zlecenia pracy **Wydanie przeniesienia** o typie **Odłożenie**. W scenariuszu, gdzie wyroby gotowe powinny być objęte przeładunkiem kompletacyjnym tylko wtedy, gdy przyczepa jest przypisana bramy dokowej, może być przydatne ustawienie opcji **Zapotrzebowanie na przeładunek kompletacyjny wymaga lokalizacji** . W tym scenariuszu towary są przesuwane bezpośrednio z linii produkcyjnej do przyczepy. Podczas przypisywania przyczepy do bramy dokowej użytkownik przypisze lokalizację do harmonogramu terminów, w związku z czym aktywuje lokalizację dla przeładunków kompletacyjnych. W poniższych sekcjach omówiono dwa przykłady.

#### <a name="scenario-1--cross-docking-from-production-to-transfer-orders"></a>Scenariusz 1 — Przeładunek kompletacyjny z produkcji do zamówień przeniesienia

Po zgłoszeniu produktu jako gotowego na linii produkcyjnej jest on przenoszony do lokalizacji przy bramie dokowej, skąd jest ładowany na ciężarówkę i następnie przenoszony do centrum dystrybucji. Użyj danych firmy USMF.

1.  Włączanie nowej numeracji dla przeładunków kompletacyjnych. Przejdź do strony **Sekwencje numerów** i naciśnij przycisk **Generuj**. Kreator poprowadzi Cię przez proces.
2.  Tworzenie zasady przeładunku kompletacyjnego. Przejdź do strony **Zasady przeładunku kompletacyjnego** i utwórz nową zasadę o nazwie **Przeładunek kompletacyjny do zamówienia przeniesienia**. Zwróć uwagę, że można wybrać tylko typ zlecenia pracy **Wydanie przeniesienia**, a jedyna dostępna strategia przeładunku kompletacyjnego to **Data i godzina**.
3.  Tworzenie zasady pracy. Przejdź do strony **Zasady pracy** i utwórz nową zasadę pracy o nazwie **Przeładunek kompletacyjny L0101**.
4.  Konfigurowanie ładunków, tak aby były tworzone automatycznie dla zamówień przeniesienia. W parametrach magazynu skonfiguruj automatyczne tworzenie ładunków podczas tworzenia zamówień przeniesienia. Ładunek jest warunkiem niezbędnym, aby zamówienia przeniesienia mogły być objęte przeładunkiem kompletacyjnym.
5.  Skonfiguruj mapowanie ładunku towarów. Przejdź do strony **Mapowanie ładunku pozycji** i skonfiguruj standardowy szablon ładunku dla grupy towarów **CarAudio**. To mapowanie będzie powodowało automatyczne wstawianie szablonu ładunku do ładunku podczas tworzenia zamówienia przeniesienia.
6.  Tworzenie zamówienia przeniesienia. Utwórz zamówienie przeniesienia towaru o numerze L0101. Ilość = 20.
7.  Zwalnianie zamówienia przeniesienia z pulpitu planowania wysyłki ładunku. Na karcie **Wysyłka** wybierz element menu dotyczący pulpitu planowania wysyłki ładunku, a następnie w menu **Zwolnienie** dla wiersza ładunku wybierz opcję **Zwolnij do magazynu**. Teraz dla zamówienia przeniesienia pojawi się wiersz otwartej grupy czynności typu **Wydanie przeniesienia**.
8.  Utwórz zlecenie produkcyjne. Przejdź do strony listy **Zlecenie produkcyjne** i utwórz zlecenie produkcyjne dla produktu L0101. Ilość = 20. Oszacuj i uruchom zlecenie produkcyjne. Należy zauważyć, że pole **Księgowanie listy pobrania** pozostaje ustawione na **Nie**.
9.  Zgłaszanie jako gotowych z urządzenia komórkowego. Przejdź do portalu urządzeń przenośnych i wybierz pozycję menu **Zgłoszenie i odłożenie wyrobów gotowych**. Teraz z urządzenia przenośnego zgłoś produkt L0101 jako gotowy. Ilość = 10. Zauważ, że lokalizacją odłożenia jest **BAYDOOR**. Ta lokalizacja jest pobierana z dyrektywy lokalizacji **Wydanie przeniesienia** dla typu zlecenia pracy **Odłożenie**. Zwróć również uwagę, że praca typu **Wydanie przeniesienia** została utworzona i wykonana. Przejdź do szczegółów pracy zamówienia przeniesienia i zweryfikuj pracę.
10. Teraz utwórz raporty dla dodatkowych 10 sztuk za pomocą urządzenia przenośnego. Zauważ, że lokalizacją odłożenia ponownie jest **BAYDOOR**. Zwróć również uwagę, że nowa praca typu **Wydanie przeniesienia** została utworzona dla 10 sztuk.
11. Teraz spróbuj uruchomić produkcję kolejnych 20 sztuk w zleceniu produkcyjnym, a następnie zgłosić 20 sztuk jako wyroby gotowe z urządzenia przenośnego. Tym razem jako lokalizacja odłożenia będzie sugerowana lokalizacja **LP-001**. Ta lokalizacja jest pobierana z dyrektywy lokalizacji dla typu zlecenia **Odłożenie wyrobów gotowych**. Jest używana ta dyrektywa lokalizacji, ponieważ nie istnieje żadna możliwość przeładunku kompletacyjnego. Zamówienie przeniesienia dla lokalizacji LP-001 zostało całkowicie wypełnione przez dwa działania przeładunku kompletacyjnego w krokach 9 i 10. Zwróć uwagę, że praca typu **Odłożenie wyrobów gotowych** została utworzona i przetworzona.

#### <a name="scenario-2---cross-docking-from-production-to-transfer-orders-with-an-appointment-schedule"></a>Scenariusz 2 — Przeładunek kompletacyjny z produkcji do zamówień przeniesienia z harmonogramem terminów

Po zgłoszeniu produktu jako gotowego na linii produkcyjnej jest on przenoszony do lokalizacji przy bramie dokowej, która jest identyfikowana przez harmonogram terminów dla lokalizacji przy bramach dokowych. Użyj danych firmy USMF.

1.  Modyfikacja zasady przeładunku kompletacyjnego. Zmodyfikuj zasadę przeładunku kompletacyjnego utworzoną w scenariuszu 1, zaznaczając pole wyboru **Zapotrzebowanie na przeładunek kompletacyjny wymaga lokalizacji**.
2.  Tworzenie nowego zamówienia przeniesienia.
3.  Otwórz **pulpit planowania wysyłki ładunku**.
4.  Z pulpitu planowania wysyłki ładunku przejdź do sekcji **Ładunek**, a następnie z menu **Transport** wybierz polecenie **Harmonogram terminów** i utwórz nowy harmonogram terminów. Należy zauważyć, że harmonogram terminów odwołuje się do zamówienia przeniesienia za pomocą pola **Numer zamówienia**. W polu **Planowana data/godzina rozpoczęcia w lokalizacji** można ustawić datę i godzinę terminu. Ta data i godzina będą używane podczas ustalania priorytetów przeładunku kompletacyjnego w procesie przeładunku kompletacyjnego. Data i godzina ustawione tym polu spowodują aktualizację pola **Data i godzina zaplanowanej wysyłki ładunku** w odnośnym ładunku. Lokalizacja na skróconej karcie **Szczegóły wysyłki** wskazuje lokalizację, z której zostaną wysłane towary zamówienia przeniesienia.
5.  W **pulpicie planowania wysyłki ładunku** przeprowadź zwolnienie do magazynu.
6.  Utwórz zlecenie produkcyjne na towar o numerze **L0101** i ustaw jego stan na **Rozpoczęte**, z ilością równą 20.
7.  Zgłaszanie jako gotowych z urządzenia komórkowego.
8.  Przejdź do portalu urządzeń przenośnych i wybierz pozycję menu **Zgłoszenie i odłożenie wyrobów gotowych**.
9.  Z urządzenia przenośnego zgłoś towar o numerze **L0101** jako produkt gotowy. Zauważ, że lokalizacją odłożenia jest teraz **BAYDOOR 2**. Ta lokalizacja jest pobierana z harmonogramu terminów, a nie z dyrektywy lokalizacji **Przyjęcie przeniesienia**.

### <a name="additional-information"></a>Informacje dodatkowe

-   Scenariusz przeładunku kompletacyjnego jest obsługiwany dla towarów wchodzących w skład partii i serii, gdzie wymiary partii i numeru seryjnego są zdefiniowane powyżej i poniżej lokalizacji w hierarchii rezerwacji. 



