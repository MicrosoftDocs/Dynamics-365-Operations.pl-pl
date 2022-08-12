---
title: Omówienie konfiguracji magazynu
description: W tym artykule wyjaśniono sposób konfigurowania magazynu. Artykuł zawiera informacje o włączaniu układu magazynu i procesów magazynowych.
author: perlynne
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, WHSLocation, WHSLocationBuild, WHSLocationProfile, WHSLocationType, WHSLocDirTable, WHSParameters, WHSWaveTemplateTable, WHSWorkPool, WHSWorkTemplateTable, WHSZone, WHSZoneGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11554"
- intro-internal
ms.assetid: 262b7b88-2cce-44f7-9a5b-77c12af1be20
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7643a333c269a7e1976563ff0f10b89c1fb91674
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065196"
---
# <a name="warehouse-configuration-overview"></a>Omówienie konfiguracji magazynu

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono sposób konfigurowania magazynu. Artykuł zawiera informacje o włączaniu układu magazynu i procesów magazynowych.

> [!NOTE]
> Ten artykuł dotyczy funkcji w module **Zarządzanie magazynem**. Nie ma zastosowania do funkcji w module **Zarządzanie zapasami**.

## <a name="warehouse-layout"></a>Układ magazynu
Procesy zarządzania magazynem (WMS) w Supply Chain Management zapewnia elastyczne metody definiowania układu magazynu do zaspokojenia zmieniających się potrzeb, dzięki czemu można uzyskać optymalną wydajność magazynu.

-   Istnieje możliwość ustalenia obszarów magazynowych o wysokim priorytecie i niskim priorytecie dla optymalnego umieszczenia towarów.
-   Magazyn można podzielić na strefy, aby spełniał różne wymagania przechowywania, takie jak wymagania w zakresie temperatury lub różnych współczynników obrotu dla towarów.
-   Można określić lokalizacje w magazynie na dowolnym poziomie (na przykład oddział, magazyn, korytarz, regał, półka i pojemnik).
-   Lokalizacje można grupować przy użyciu ustawień ograniczenia fizycznych możliwości.
-   Można kontrolować sposób przechowywania i pobierania towarów na podstawie reguł zdefiniowanych w kwerendzie.

Aby używać WMS w Supply Chain Management, musisz utworzyć magazyn i włączyć go do systemu WMS. Na stronie **Magazyny** wybierz opcję **Użyj procesów zarządzania magazynami**.

### <a name="zone-groups-zones-location-types-and-locations"></a>Grupy stref, strefy, typy lokalizacji i lokalizacje

W ramach procesu włączania układu magazynu należy zdefiniować grupy strefy magazynowej, strefy, profile lokalizacji, typy lokalizacji i lokalizacje.

-   **Grupy stref** — logiczne lub fizyczne grupowanie stref w magazynie.
-   **Strefy** — logiczne lub fizyczne grupowanie lokalizacji w magazynie.
-   **Profile lokalizacji** — logiczne lub fizyczne grupowanie lokalizacji, które mają te same zasady procesów lokalizacji magazynu (np. można przechowywać różne numery towarów i obowiązują te same ograniczenia pojemności fizycznej).
-   **Typy lokalizacji** — logiczne lub fizyczne grupowanie lokalizacji magazynu. Na przykład, można utworzyć typ lokalizacji dla wszystkich lokalizacji tymczasowych. Wymagane ustawienia na stronie **Parametry zarządzania magazynem** ułatwiają proces definiowania typów lokalizacji pośredniej i typów lokalizacji końcowej.
-   **Lokalizacje** — najniższy poziom informacji o lokalizacji. Lokalizacje są używane do śledzenia, które dostępne zapasy są przechowywane i pobierane w magazynie.

Jednostki utworzone w celu zdefiniowania układu magazynu są używane w kwerendach ustawionych w szablonach pracy w celu uruchomienia zleceń w magazynie. Dlatego podczas definiowania stref, typów lokalizacji itd. należy wziąć pod uwagę jak różne obszary w magazynie są używane dla różnych procesów. Ponadto należy wziąć pod uwagę czynniki, takie jak fizyczne charakterystyki określonego obszaru. Na przykład mogą być obszary, w których można używać tylko określonego typu wózków widłowych. Lub jeśli firma ma zarówno produkcję, jak i wyroby gotowe w obrębie tego samego obiektu, może być pomocne utworzenie jednego magazynu w Supply Chain Management, ale następnie oddzielenie tych dwóch funkcji poprzez utworzenie dwóch grup stref. Nadaj jednostkom opisowe nazwy, aby łatwo je identyfikować, gdy będzie trzeba ich użyć w zapytaniach szablonu.

### <a name="location-stocking-limits-location-profiles-and-fixed-picking-locations"></a>Limity składowania w lokalizacji, profile lokalizacji i stałe lokalizacje pobrania

Należy pamiętać o fizycznym układzie magazynu, zarówno do określenia pojemności magazynów (limity składowania w lokalizacji i profile lokalizacji), jak i w celu wypracowania optymalnych procesów magazynowych. 

Limity składowania w lokalizacji gwarantują, że nie zostanie utworzona praca żądania przyjęcia w lokalizacji, która nie ma fizycznej pojemności, by pomieścić towar. Na przykład jeśli niektóre lokalizacje magazynu mogą zawierać tylko po jednej palecie, można włączyć limit składowania w lokalizacji. Wartość **Ilość** może być ustawiona jako **1** a wartość **jednostek** jako **PL** w ramach określonego grupowania profilu lokalizacji. 

Jeśli są wymagane bardziej zaawansowane obliczenia do kontrolowania ograniczeń pojemności lokalizacji, można użyć ustawień profili lokalizacji. W tym przypadku waga i objętość są brane pod uwagę przy obliczaniu pojemności. 

Aby uzyskać optymalne procesy wychodzące, oceń, czy należy używać stałych lokalizacji pobrania i/lub lokalizacji pakowania. Często uzupełnienia minimum/maksimum służy do procesu uzupełniania zapasów z lokalizacji zbiorczej do ustalonych lokalizacji pobrania, a wiele stałych lokalizacji pobrania można włączyć w jednym magazynie i dla wariantów produktów. Należy wziąć pod uwagę elastyczność, którą można osiągnąć włączając lokalizacje przepełnienia uzupełnienia zapasów dla popytu dedykowanego, które są używane tylko do przetwarzania uzupełnienia fali/ładunku.

### <a name="location-setup-wizard"></a>Kreator konfiguracji lokalizacji

Aby szybko utworzyć lokalizacji magazynu, można użyć kreatora **ustawienia lokalizacji**. W ramach tego procesu możesz łatwo zachować format nazwy lokalizacji.

## <a name="warehouse-processes"></a>Procesy magazynu
W ramach konfiguracji magazynu ważne jest włączanie procesów magazynowych zgodnie z wymaganiami firmy. Najważniejsze składniki, które należy skonfigurować to szablony grupy czynności, szablony pracy, pule pracy i dyrektywy lokalizacji.

### <a name="wave-templates"></a>Szablony grupy czynności

Szablony grupy czynności pomagają włączyć proces wychodzący "Zwalniania do magazynu". Jak tylko wiersze zamówienia są zwalniane (albo bezpośrednio z dokumentów źródłowych, poprzez procesy zadań wsadowych lub za pośrednictwem ładunków, które już zostały utworzone), jest używana funkcja szablonu grupy czynności. 

Możliwe jest tworzenie trzech rodzajów szablonów grupy czynności: 
-   **Wysyłka**
-   **Zlecenie produkcyjne**
-   **Kanban** 

Parametry służą do określania, jak daleko system powinien automatycznie dojść podczas przetwarzania pracy wychodzącej. Szablon grupy czynności jest wybierany na podstawie sekwencja szablonu grupy czynności i kryteriów określonych w szablonie. Jeśli szablon jest wyświetlany u góry sekwencji, najpierw sprawdza się kryteria w tym szablonie. Jeśli kryteria mogą być spełnione, szablon grupy czynności jest przetwarzany. W przeciwnym razie sprawdzane są kryteria w następnym szablonie itd. Z tego względu dobrze jest umieścić szablon, który ma u góry listy sekwencji szablonu grupy czynności najlepiej określone kryteria, aby był przetwarzany jako pierwszy. Na przykład chcesz przetworzyć wszystkie prace dla określonego przewoźnika dzisiaj i tymczasowo opóźnić przetwarzanie pracy innych przewoźników. W takim przypadku szablon grupy czynności, który wybiera kryteria pracy dla tego przewoźnika powinien się znaleźć wyżej w sekwencji niż inne szablony. W przeciwnym razie praca innych przewoźników może być przetworzona przed ukończeniem pracy dla tego przewoźnika. 

Należy określić metody przetwarzania grupy czynności w poszczególnych szablonach grupy czynności. Dostępne metody zależą od typu szablonu grupy czynności.

### <a name="work-templates"></a>Szablony pracy

Definicje szablonów pracy odgrywają ważną rolę w definicji procesów pracy zarządzania magazynem. Określają one, jaka praca jest wykonywana i sposób wykonywania pracy. Szablony mogą zawierać również kod dyrektywy łączący dyrektywy lokalizacji do określenia, gdzie praca jest wykonywana. Szablony pracy zawierają kwerendy, które określają kryteria dla pracy. Każdy szablon musi zawierać co najmniej jedną operację pobrania i jednej operację odłożenia do uruchomienia podstawowej operacji pracy w postaci przeniesienia dostępnych zapasów z jednej lokalizacji do innej. 

Jeśli kilku pracowników musi mieć możliwość przetworzenia pracy dla niektórych operacji magazynowych, warto używać koncepcji *etapów* dla zapasów i rozdzielić wykonanie pracy na różne klasy pracy.

### <a name="work-pools"></a>Pula pracy

Można używać puli prac do organizacji pracy w grupy. Można na przykład utworzyć pulę pracy do sklasyfikowania pracy, która występuje w określonej lokalizacji magazynu. Dla wszystkich typów prac, z wyjątkiem zliczania można przypisać pulę pracy do szablonu pracy. Do inwentaryzacji ciągłej można przypisać pulę pracy na następujących stronach:

-   Plany inwentaryzacji ciągłej
-   Progi inwentaryzacji ciągłej
-   Praca inwentaryzacji ciągłej wg lokalizacji
-   Praca inwentaryzacji ciągłej wg pozycji

W przypadku korzystania z szablonów pracy przy tworzeniu pracy, pula pracy jest automatycznie przypisywana do pracy. 

Identyfikator puli pracy możne też służyć do ograniczenia typu pracy kierowanej do określonego pracownika magazynu, pod warunkiem, że ta funkcja jest skonfigurowana w menu urządzenia przenośnego.

### <a name="location-directives"></a>Dyrektywy lokalizacji

Jak sugeruje nazwa, dyrektywy lokalizacji służą do kierowania transakcji pracy do odpowiednich lokalizacji w magazynie. Innymi słowy określają lokalizacje pobrania i odłożenia. 

Aby szybciej i łatwiej określić zadania związane z wierszem dyrektywy lokalizacji, użyj jednej z wstępnie zdefiniowanych strategii. Na przykład, można użyć strategii **Pusta lokalizacja bez przychodzącej pracy** do wyszukiwania wolnej lokalizacji w magazynie, lub można użyć strategii **Rezerwacja partii FEFO** dla wychodzących pobrań sprzedaży.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie lokalizacji w magazynie z obsługą WMS](tasks/configure-locations-wms-enabled-warehouse.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]