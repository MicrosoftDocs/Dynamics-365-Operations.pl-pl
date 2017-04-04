---
title: Konfiguracja magazynu
description: "W tym artykule wyjaśniono sposób konfigurowania magazynu. Artykuł zawiera informacje o włączaniu układu magazynu i procesów magazynowych."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-10-30 12 - 52 - 43
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, WHSLocation, WHSLocationBuild, WHSLocationProfile, WHSLocationType, WHSLocDirTable, WHSParameters, WHSWaveTemplateTable, WHSWorkPool, WHSWorkTemplateTable, WHSZone, WHSZoneGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11554
ms.assetid: 262b7b88-2cce-44f7-9a5b-77c12af1be20
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 437f2348603db432df6d7589e4043d8145c52a1e
ms.lasthandoff: 03/30/2017


---

# <a name="warehouse-configuration"></a>Konfiguracja magazynu

W tym artykule wyjaśniono sposób konfigurowania magazynu. Artykuł zawiera informacje o włączaniu układu magazynu i procesów magazynowych.

**Uwaga:** Ten artykuł dotyczy funkcji zaawansowanego zarządzania magazynem w module **Zarządzanie magazynem**. Nie ma zastosowania do funkcji w module **Zarządzanie zapasami**.

## <a name="warehouse-layout"></a>Układ magazynu
System zarządzania magazynem w programie Microsoft Dynamics 365 for Operations zapewnia elastyczne metody definiowania układu magazynu do zaspokojenia zmieniających się potrzeb, dzięki czemu można uzyskać optymalną wydajność magazynu.

-   Istnieje możliwość ustalenia obszarów magazynowych o wysokim priorytecie i niskim priorytecie dla optymalnego umieszczenia towarów.
-   Magazyn można podzielić na strefy, aby spełniał różne wymagania przechowywania, takie jak wymagania w zakresie temperatury lub różnych współczynników obrotu dla towarów.
-   Można określić lokalizacje w magazynie na dowolnym poziomie (na przykład oddział, magazyn, korytarz, regał, półka i pojemnik).
-   Lokalizacje można grupować przy użyciu ustawień ograniczenia fizycznych możliwości.
-   Można kontrolować sposób przechowywania i pobierania towarów na podstawie reguł zdefiniowanych w kwerendzie.

Aby użyć zarządzania magazynem w programie Microsoft Dynamics 365 for Operations, należy utworzyć magazyn i uaktywnić bardziej zaawansowane lub wyspecjalizowane działania związane z obsługą magazynu. Na stronie **Magazyny** wybierz opcję **Użyj procesów zarządzania magazynami**.

### <a name="zone-groups-zones-location-types-and-locations"></a>Grupy stref, strefy, typy lokalizacji i lokalizacje

W ramach procesu włączania układu magazynu należy zdefiniować grupy strefy magazynowej, strefy, profile lokalizacji, typy lokalizacji i lokalizacje.

-   **Grupy stref** — logiczne lub fizyczne grupowanie stref w magazynie.
-   **Strefy** — logiczne lub fizyczne grupowanie lokalizacji w magazynie.
-   **Profile lokalizacji** — logiczne lub fizyczne grupowanie lokalizacji, które mają te same zasady procesów lokalizacji magazynu (np. można przechowywać różne numery towarów i obowiązują te same ograniczenia pojemności fizycznej).
-   **Typy lokalizacji** — logiczne lub fizyczne grupowanie lokalizacji magazynu. Na przykład, można utworzyć typ lokalizacji dla wszystkich lokalizacji tymczasowych. Wymagane ustawienia na stronie **Parametry zarządzania magazynem** ułatwiają proces definiowania typów lokalizacji pośredniej i typów lokalizacji końcowej.
-   **Lokalizacje** — najniższy poziom informacji o lokalizacji. Lokalizacje są używane do śledzenia, które dostępne zapasy są przechowywane i pobierane w magazynie.

Jednostki utworzone w celu zdefiniowania układu magazynu są używane w kwerendach ustawionych w szablonach pracy w celu uruchomienia zleceń w magazynie. Dlatego podczas definiowania stref, typów lokalizacji itd. należy wziąć pod uwagę jak różne obszary w magazynie są używane dla różnych procesów. Ponadto należy wziąć pod uwagę czynniki, takie jak fizyczne charakterystyki określonego obszaru. Na przykład może być obszarów, gdzie można użyć tylko pewnego rodzaju wózka widłowego. Lub, jeżeli firma posiada zarówno produkcji, jak i wyroby gotowe w tym samym miejscu, warto utworzyć pojedynczy magazyn w usłudze Dynamics 365 dla operacji, ale następnie oddzielić dwie operacje, tworząc dwie grupy strefy. Dać obiekty opisowe nazwy, tak, że jest łatwo zidentyfikować je podczas korzystania z nich w kwerendach szablonu.

### <a name="location-stocking-limits-location-profiles-and-fixed-picking-locations"></a>Limity składowania w lokalizacji, profile lokalizacji i stałe lokalizacje pobrania

Należy pamiętać o fizycznym układzie magazynu, zarówno do określenia pojemności magazynów (limity składowania w lokalizacji i profile lokalizacji), jak i w celu wypracowania optymalnych procesów magazynowych. 

Lokalizacja obsady zwierząt limity pomóc w zagwarantowaniu, że praca nie jest tworzony do żądania spis umieścić w lokalizacji, która nie ma fizycznych zdolności produkcyjnych do przewozu zapasów. Na przykład jeśli niektórych lokalizacji w magazynie można przechowywać tylko jedna paleta według lokalizacji, można włączyć limity składowania w lokalizacji. ** Ilość ** wartość może być równa **1**i ** jednostki ** wartość może być równa **PL** grupie, profil użytkownika do określonej lokalizacji. 

Jeśli są wymagane bardziej zaawansowane obliczenia do kontrolowania ograniczeń pojemności lokalizacji, można użyć ustawień profili lokalizacji. W tym przypadku waga i objętość są brane pod uwagę przy obliczaniu pojemności. 

Aby uzyskać optymalne procesy wychodzące, oceń, czy należy używać stałych lokalizacji pobrania i/lub lokalizacji pakowania. Często uzupełnienia minimum/maksimum służy do procesu uzupełniania zapasów z lokalizacji zbiorczej do ustalonych lokalizacji pobrania, a wiele stałych lokalizacji pobrania można włączyć w jednym magazynie i dla wariantów produktów. Należy wziąć pod uwagę elastyczność, którą można osiągnąć włączając lokalizacje przepełnienia uzupełnienia zapasów dla popytu dedykowanego, które są używane tylko do przetwarzania uzupełnienia fali/ładunku.

### <a name="location-setup-wizard"></a>Kreator konfiguracji lokalizacji

Aby szybko utworzyć lokalizacji w magazynie, można użyć ** ustawienia lokalizacji ** kreatora. W ramach tego procesu możesz łatwo zachować format nazwy lokalizacji.

## <a name="warehouse-processes"></a>Procesy magazynu
W ramach konfiguracji magazynu ważne jest włączanie procesów magazynowych zgodnie z wymaganiami firmy. Najważniejsze składniki, które należy skonfigurować to szablony grupy czynności, szablony pracy, pule pracy i dyrektywy lokalizacji.

### <a name="wave-templates"></a>Szablony grupy czynności

Szablony grupy czynności pomagają włączyć proces wychodzący "Zwalniania do magazynu". Jak tylko wiersze zamówienia są zwalniane (albo bezpośrednio z dokumentów źródłowych, poprzez procesy zadań wsadowych lub za pośrednictwem ładunków, które już zostały utworzone), jest używana funkcja szablonu grupy czynności. 

Można utworzyć trzy typy szablonów wave: **wysyłki**, **zlecenia produkcyjnego**, i **Kanban**. Parametry są używane do definiowania jak daleko system automatycznie powinien iść w przetwarzaniu ruchu wychodzącego pracy. Szablon grupy czynności jest wybierany na podstawie sekwencja szablonu grupy czynności i kryteriów określonych w szablonie. Jeśli szablon jest wyświetlany u góry sekwencji, najpierw sprawdza się kryteria w tym szablonie. Jeśli kryteria mogą być spełnione, szablon grupy czynności jest przetwarzany. W przeciwnym razie sprawdzane są kryteria w następnym szablonie itd. Z tego względu dobrze jest umieścić szablon, który ma u góry listy sekwencji szablonu grupy czynności najlepiej określone kryteria, aby był przetwarzany jako pierwszy. Na przykład chcesz przetworzyć wszystkie prace dla określonego przewoźnika dzisiaj i tymczasowo opóźnić przetwarzanie pracy innych przewoźników. W takim przypadku szablon grupy czynności, który wybiera kryteria pracy dla tego przewoźnika powinien się znaleźć wyżej w sekwencji niż inne szablony. W przeciwnym razie praca innych przewoźników może być przetworzona przed ukończeniem pracy dla tego przewoźnika. 

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

<a name="see-also"></a>Informacje dodatkowe
--------

[Konfigurowanie lokalizacji w magazynie włączone WMS (Przewodnik zadania)](https://ax.help.dynamics.com/en/wiki/configure-locations-in-a-wms-enabled-warehousing/)


