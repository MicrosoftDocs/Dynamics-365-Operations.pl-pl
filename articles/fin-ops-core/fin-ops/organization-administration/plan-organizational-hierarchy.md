---
title: Planowanie hierarchii organizacyjnej
description: Przed skonfigurowaniem organizacji i hierarchii organizacyjnych upewnij się, że wiesz, jak najlepiej modelować firmę.
author: sericks007
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMLegalEntity, OMOperatingUnit
audience: Application User
ms.reviewer: sericks
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef906c0d60639da763f2a9c1e1adf508b0849b8978dff17cd0e7b3936fc4779e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771879"
---
# <a name="plan-your-organizational-hierarchy"></a>Planowanie hierarchii organizacyjnej

[!include [banner](../includes/banner.md)]

Przed skonfigurowaniem organizacji i hierarchii organizacyjnych upewnij się, że masz plan dotyczący modelowania firmy. Model organizacyjny ma znaczny wpływ na implementację i na procesy biznesowe.

Hierarchie organizacyjne reprezentują relacje między organizacjami, które składają się na działalność. Dlatego podczas modelowania organizacji należy zwrócić szczególną uwagę na strukturę firmy. Zaleca się określenie struktury organizacji, na podstawie informacji uzyskanych od kadry zarządzającej i menedżerów wyższego stopnia z obszarów funkcjonalnych, takich jak operacje finansowe i rachunkowość, zasoby ludzkie, zakupy, a także sprzedaż i marketing.

Podczas planowania hierarchii należy również wziąć pod uwagę relację między hierarchią organizacyjną i wymiarami finansowymi. Można skonfigurować wiele hierarchii organizacyjnych do reprezentowania różnych widoków dla prowadzonej działalności. Korzystając z wymiarów finansowych, można utworzyć raporty oparte na tych widokach. Praca z partnerem umożliwia tworzenie hierarchii organizacyjnej odpowiedniej zarówno pod względem organizacyjnym, jak i spełniającej ustawowe wymogi dotyczące raportowania.

> [!NOTE]
> Wprawdzie można używać wymiarów finansowych do reprezentowania firmy bez tworzenia firm, ale wymiary finansowe nie są przeznaczone do spełniania operacyjnych lub biznesowych potrzeb firmy. Funkcję księgowania międzyjednostkowego zaprojektowano tylko z myślą o zapisach księgowych, które są tworzone przy każdej transakcji.

> [!IMPORTANT]
> Nie należy podejmować decyzji o sposobie modelowania organizacji tylko na podstawie informacji podanych w tym artykule. Niniejsza dokumentacja jest przewodnikiem. Można podjąć współpracę z partnerem, aby uzyskać dodatkowe wskazówki. Partner ma doświadczenie w różnych branż i z różnymi klientami.

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>Podjęcie decyzji, czy modelować organizacje wewnętrzne jako firmy, czy jednostki operacyjne

Musi istnieć co najmniej jedna firma, która będzie reprezentować przedsiębiorstwo. Firma może zawierać umowy i wymaga się od niej przygotowywania zestawień finansowych na temat wydajności.

Firmy mogą służyć dla transakcji biznesowych lub konsolidacji. Oznacza to, że firma w Finance and Operations nie musi koniecznie reprezentować rzeczywistej firmy. Na przykład firma, która uczestniczy w transakcjach, może być właścicielem oddziałów firmy. W tym scenariuszu firma jest wymagana dla transakcji, a wirtualna firma jest wymagana do konsolidacji wyników i sald oddziałów firmy.

Wewnętrzne organizacje biznesowe, takie jak biura regionalne, mogą być reprezentowane jako dodatkowe firmy lub jednostki operacyjne głównej firmy. Jednostka operacyjna nie musi być prawnie zdefiniowaną organizacją. Jednostki operacyjne służą do kontrolowania zasobów ekonomicznych i procesów operacyjnych w firmie. Na przykład działy i centra kosztów są jednostkami operacyjnymi.

Niektóre funkcje różnią się w zależności od tego, czy organizacja jest podmiotem prawny czy jednostką operacyjną. Przed podjęciem decyzji dokładnie przeanalizuj funkcje opisane poniżej.

### <a name="master-data"></a>Dane główne

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Niektóre dane główne — takie jak klienci, warunki płatności, urzędy podatkowe i zamawianie zapasów właściwe dla zakładu — należy ustawić dla każdej firmy. Niektóre dane główne — takie jak użytkownicy, produktów i większość danych zasobów ludzkich — są współużytkowane przez wszystkie firmy.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Dane główne są udostępniane między jednostkami operacyjnymi.

### <a name="module-parameters"></a>Parametry modułu

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Parametry modułów, takich jak Rozrachunki z odbiorcami, Rozrachunki z dostawcami oraz Zarządzanie gotówką i bankami, należy ustawić dla każdej firmy. Ustawienie modułu dla firmy jest osobne, dla każdego oddziału zgodne z lokalnymi wymogami ustawowymi oraz praktykami handlowymi. Na przykład firma świadcząca usługi konsultingowe i firma produkcyjna mogą mieć parametry innego modułu, nawet jeśli zgłaszają do tej samej firmy nadrzędnej.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Parametry modułu są współużytkowane przez jednostki operacyjne.

### <a name="data-security"></a>Bezpieczeństwo danych

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Większość danych automatycznie jest zabezpieczona za pomocą identyfikatora firmy. Przedsiębiorstwo ma unikatowy identyfikator dla danych, które są skojarzone z firmą. Przedsiębiorstwo może być skojarzone tylko z jedną firmą, a firma może być skojarzona tylko z jednym przedsiębiorstwem. Użytkownicy mogą korzystać tylko z tych firmowych danych, do których mają dostęp. Nie trzeba dostosowywać do zabezpieczania danych według identyfikatora firmy.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Dane mogą być chronione według jednostek operacyjnych przez utworzenie niestandardowych zasad zabezpieczeń. Zasady zabezpieczeń danych służą do ograniczania dostępu do danych. Na przykład załóżmy, że użytkownik może tworzyć zamówienia zakupu tylko w określonej jednostki operacyjnej. Aby uniemożliwić użytkownikowi dostęp do danych zamówienia zakupu z innych jednostek operacyjnych, mogą być tworzone zasady zabezpieczeń danych. Ilość transakcji i liczby zasad zabezpieczeń może wpływać na wydajność. Podczas projektowania zasad zabezpieczeń należy wziąć pod uwagę efekty.

### <a name="ledgers"></a>Księgi

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Każda firma potrzebuje księgi, która zawiera plan kont, walutę rozliczeniową, walutę raportowania i kalendarz obrachunkowy. Bilans można utworzyć tylko dla firmy. Konta główne, wymiary, struktury konta, wykresy kont i reguły kont mogą być używane przez więcej niż jedną firmę.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Jednostka operacyjna nie może mieć własnych informacji finansowych. Jeśli organizacje wewnętrzne nie wymagają unikatowych ksiąg, można je modelować jako jednostki operacyjne. Informacje finansowe będą konfigurowane dla podmiotu prawnego nadrzędnego w hierarchii. Rachunki zysków i strat mogą być tworzone dla jednostek operacyjnych w ramach firmy lub w firmie nadrzędnej.

### <a name="fiscal-calendars"></a>Kalendarze obrachunkowe

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Każda firma ma własny kalendarz obrachunkowy. Jeśli organizacje wewnętrzne używają różnych lat obrachunkowych i kalendarzy obrachunkowych, należy modelować te organizacje jako firmy.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Jednostki operacyjne muszą współużytkować kalendarz obrachunkowy. Jeśli organizacje wewnętrzne mogą stosować ten sam rok obrachunkowy i te same kalendarze obrachunkowe, można modelować te organizacje jako jednostki operacyjne.

### <a name="consolidation"></a>Konsolidacja

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Wyniki finansowe dla biur regionalnych należy skonsolidować do jednej, skonsolidowanej firmy w celu przygotowania sprawozdań finansowych.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Konsolidacja nie jest wymagana, ponieważ dane już są udostępnione między jednostkami operacyjnymi.

### <a name="centralized-payments"></a>Płatności scentralizowane

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Scentralizowane płatności należy tak skonfigurować, aby dla wszystkich firm podrzędnych można było zapłacić za faktury do lub z jednej nadrzędnej firmy.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Scentralizowane płatności nie są wymagane, ponieważ wszystkie faktury są rejestrowane w jednej firmie.

### <a name="intercompany-transactions"></a>Transakcje międzyfirmowe

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Można stosować międzyfirmowe zamówienia sprzedaży, zamówienia zakupu, płatności i przychody. Nie należy używać załączników arkuszy. Można wyświetlać transakcje międzyfirmowe na poziomie księgi podrzędnej (Rozrachunki z odbiorcami, Rozrachunki z dostawcami). Poniższe przykłady ilustrują sposób obsługi transakcji międzyfirmowych.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Przykład 1: centrala zapewnia usługi biurom regionalnym i pobierają koszty tych usług do biur regionalnych.

Jeśli modelujesz biuro regionalne jako firmę, dostępne są następujące opcje:

- Centrala tworzy wpis dziennika dla opłaty krzyżowej jako wydatek biura regionalnego. Nie można określić wieku transakcji.
- Centrala przesyła zamówienie zakupu dla usług do biura regionalnego. Zamówienie sprzedaży jest tworzone automatycznie w firmie dla biura regionalnego z transakcji międzyfirmowych księgi podrzędnej.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Przykład 2: centrala zamawia i płaci za usługi dostarczane do biur regionalnych.

Jeśli modelujesz biuro regionalne jako firmę, dostępne są następujące opcje:

- Faktury i płatności podlegają wymaganiom prawnym centrali. Centrala może utworzyć wpis dziennika dla opłaty krzyżowej jako wydatek biura regionalnego. Nie można określić wieku transakcji.
- Faktury i płatności podlegają wymaganiom prawnym centrali. Centrala może utworzyć transakcji międzyfirmowe księgi podrzędnej.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Transakcje międzyfirmowe wśród jednostek operacyjnych są obsługiwane tylko za pośrednictwem załączników arkuszy. Jednostka operacyjna nie wydaje ani nie przyjmuje zamówienia zakupu, zamówienia sprzedaży ani faktury od innej jednostki operacyjnej z tej samej firmy. Nie można wyświetlić transakcji międzyfirmowych na poziomie księgi podrzędnej (Rozrachunki z odbiorcami, Rozrachunki z dostawcami). Poniższe przykłady ilustrują sposób obsługi transakcji międzyfirmowych.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Przykład 1: centrala zapewnia usługi biurom regionalnym i pobierają koszty tych usług do biur regionalnych.

Jeśli modelujesz biuro regionalne jako jednostkę operacyjną, centrala zgłosi transakcję wydatku i kody do urzędu regionalnego.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Przykład 2: centrala zamawia i płaci za usługi dostarczane do biur regionalnych.

Jeśli modelujesz biuro regionalne jako jednostkę operacyjną, faktury i płatności muszą spełniać wymagania centrali. Faktura może zakodowana do biura regionalnego. Na rachunku zysków i strat użyj wymiaru finansowego bilansowania w celu raportowania kosztów dla biura regionalnego.

### <a name="local-tax-requirements"></a>Wymagania związane lokalnym podatkiem

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Podmiot prawny jest przedmiotem przepisów podatkowych dla urzędu skarbowego w kraju/regionie, gdzie firma jest zarejestrowana. Na przykład przepisom i podatkom według duńskiej ustawy podlega firma zarejestrowana w Danii. Firma może należeć do tylko jednego kraju/regionu. Kraj/region wybrany dla adresu podstawowego firmy steruje funkcjami specyficznymi dla kraju/regionu, które są dostępne dla tej firmy. Na przykład, jeśli jest to podstawowy adres firmy w Danii, funkcje, które są powiązane z duńskimi przepisami podatkowymi stają się dostępne. W związku z tym, jeśli organizacje znajdują się w różnych krajach/regionach i wymagają zastosowania innych podatków lokalnych, należy zdefiniować te organizacje jako odrębne firmy.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Jednostki operacyjne używają kontekstu kraju firmy nadrzędnej. Operacyjne jednostek w ramach tej samej firmy nie mogą mieć różnych wymagań specyficznych dla kraju/regionu. Jeśli organizacje znajdują się w tym samym kraju/regionu i korzystają z tej samej opcji podatkowej, można je skonfigurować jako jednostki operacyjne.

### <a name="statutory-reporting-for-a-countryregion"></a>Ustawowe raportowanie dla kraju/regionu

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Dla krajów/regionów, które są obsługiwane, można utworzyć większość raportów ustawowych. 

> [!NOTE]
> Warstwy księgowania w księdze głównej pozwalają na dodawanie wpisów korygujących dla firmy nadrzędnej, która stosuje inne standardy księgowania niż firma podrzędna. Na przykład dla firmy stosującej zasady ogólnie przyjęte w Wielkiej Brytanii (UK GAAP) można dokonać wpisów korygujących w warstwie księgowania. Te wpisy mogą być konsolidowane dla firmy nadrzędnej, która używa ogólnie przyjętych zasad rachunkowości (GAAP) w Stanach Zjednoczonych. Wpisy korygujące nie wpływają na raportowanie UK GAAP.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Raporty ustawowe muszą zostać utworzone przy użyciu innej aplikacji. Należy upewnić się, że dane są przechwytywane w Finance and Operations do obsługi wymagań dotyczących każdej jednostki operacyjnej, które różnią się od wymagań centrali.

### <a name="currency"></a>Waluta

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Jeśli organizacje wewnętrzne muszą używać różnych walut funkcjonalnych, należy modelować te organizacje jako firmy. Waluty funkcjonalne są konfigurowane dla każdej firmy. Można jednak wprowadzać transakcje w wielu walutach.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Jeśli organizacje mogą używać jednej waluty funkcjonalnej, można modelować organizacje jako jednostki operacyjne. Jednostki operacyjne muszą współużytkować walutę funkcjonalną. Można jednak wprowadzać transakcje i tworzyć raporty w wielu walutach.

### <a name="year-end-closing"></a>Zamknięcie roku

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Jeśli prawa i praktyki księgowe różnią się między krajami/regionami, w których znajdują się organizacje, mogą one wymagać różnych procedur na koniec roku. Oznacza to, że należy modelować organizacje jako firmy. Każda firma ma własne procedury zamknięcia roku.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Jeśli prawa i praktyki księgowe nie różnią się między krajami/regionami, w których znajdują się organizacje, można zastosować jeden zestaw procedur zamknięcia roku. Oznacza to, że można modelować organizacje jako jednostki operacyjne. Wszystkie jednostki operacyjne muszą używać tej samej procedury zamknięcia roku obrachunkowego.

### <a name="number-sequences"></a>Sekwencje identyfikatorów

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Sekwencje numerów dla niektórych odwołań można łączyć dla każdej firmy. Niektóre sekwencje numerów mogą być współużytkowane.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Sekwencje numerów dla niektórych odwołań można ustalać dla jednostki operacyjnej. Niektóre sekwencje numerów mogą być współużytkowane.

### <a name="products"></a>Produkty

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Definicje produktów są udostępniane i muszą być zwalniane do poszczególnych firm przed włączeniem ich do transakcji. Każda firma ma własny zestaw zwolnionych produktów, które mogą być uwzględniane w dokumentach transakcji. Jeśli organizacje wewnętrzne muszą używać różnych zestawów produktów, należy modelować te organizacje jako firmy.

> [!NOTE]
> Mimo że definicje produktu są udostępniane w każdej firmie, której produkt został wydany, można określić różne parametry sprzedaży, zakupu i składowania dla towarów w każdym miejscu składowania zapasów.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Wszystkie jednostki operacyjne współużytkują ten sam zestaw produktów. Jeśli organizacje wewnętrzne mogą współużytkować ten sam zestaw produktów, można modelować te organizacje jako jednostki operacyjne.

### <a name="inquiry-and-reporting"></a>Zapytania i raporty

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Jeśli organizacja jest modelowana jako firma

Należy ręcznie zmienić firmy do wprowadzania transakcji i wykonywania zapytania w wielu firmach. Ze względu na granice zabezpieczeń danych, skonsolidowane zapytania i raporty mogą być czasochłonne i wymagać wielu zasobów.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Jeśli organizacja jest modelowana jako jednostka operacyjna

Nie trzeba zmieniać firm w celu uzyskania dostępu do danych z wielu jednostek operacyjnych. Skonsolidowane zapytania i raportowania oraz indywidualne zapytania regionalne są łatwiejsze i szybsze.

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>Najważniejsze wskazówki dotyczące modelowania organizacji i hierarchii

Podczas implementowania hierarchii organizacyjnej należy wziąć pod uwagę następujące wskazówki:

- Utwórz dział do modelowania przestrzeni wspólnej między firmą i jednostką biznesową. Następnie zbierz dane z działu do firmy na potrzeby raportowania ustawowego i z działu do jednostki biznesowej dla sprawozdawczości wewnętrznej. Działy mogą służyć jako centra zysku. Korzystając z działów, nie należy używać firm i jednostek biznesowych jako wymiarów w strukturze konta. Działów można użyć jako wymiaru. Jednak należy użyć zarówno centrów kosztów i działów jako wymiarów w strukturze konta, jeśli centra kosztów są używane tylko jako akumulatory kosztów, a działy są używane do rozpoznawania przychodu.
- Modeluj wiele hierarchii dla jednostek operacyjnych, jeśli masz złożone wymagania dotyczące raportowania zysków i strat.
- W jednej firmie nie modeluj wielu hierarchii dla tego samego celu.
- Nie twórz hierarchii w każdym celu. Zazwyczaj można używać jednej hierarchii dla wielu celów. Na przykład do wszystkich celów związanych z zasadami można przypisać jedną hierarchię jednostek operacyjnych.
- Utwórz zrównoważoną hierarchię. W hierarchii wszystkie węzły, które są w tej samej odległości od węzła głównego, są zdefiniowane jako poziom. W zrównoważonej hierarchii tylko jeden typ jednostki operacyjnej może wystąpić na każdym poziomie, a odległość od węzła głównego do każdego poziomu jest taka sama. Jeśli istnieją stopnie pośrednie między działem a firmą lub jednostką biznesową, symbol zastępczy organizacji może być wymagany w celu utworzenia zrównoważonej hierarchii.
- Nie modeluj osobnej hierarchii jednostek operacyjnych, jeśli struktura firmy jest również strukturą operacyjną. Mieszana hierarchia firm i jednostek operacyjnych może służyć do obu celów.
- Przed modelowaniem głównych scenariuszy restrukturyzacji użyj efektywnych dat hierarchii w celu wykonania analizy wpływu i testów weryfikacyjnych.
- Użyj trybu roboczego w celu zmiany hierarchii, zanim opublikujesz nową wersję w środowisku produkcyjnym.
- Ogranicz liczbę osób, które mają uprawnienia do dodawania i usuwania organizacji z hierarchii w środowisku produkcyjnym. Mniejsza liczba zmniejsza ryzyko, że mogą wystąpić kosztowne błędy i trzeba będzie dokonywać korekt.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
