---
title: Wybieranie technologii integracji danych
description: Ten artykuł zawiera wskazówki dotyczące różnych opcji integracji z danymi zarządzanymi przez moduł Human Resources oraz opisuje cechy różnych technologii integracji, tak aby integratory mogli podejmować świadome decyzje dotyczące technologii najlepiej pasujących do ich potrzeb.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f2de5dd41c00e6546b4a4feadaf5774430d572bb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029895"
---
# <a name="choose-a-data-integration-technology"></a>Wybieranie technologii integracji danych

Moduł Dynamics 365 Human Resources zarządza danymi biznesowymi, które są przydatne w różnych procesach biznesowych. Ten artykuł zawiera wskazówki dotyczące różnych opcji integracji z danymi zarządzanymi przez moduł Human Resources oraz opisuje cechy różnych technologii integracji, tak aby integratory mogli podejmować świadome decyzje dotyczące technologii najlepiej pasujących do ich potrzeb.

## <a name="data-integration-vision"></a>Wizja integracji danych

Microsoft postrzega dane biznesowe jako kluczowy zasób, który decyduje o unikatowości firmy. Dane Twojej firmy są bardzo cenne. Dane gromadzone i przechowywane w jednej części firmy są powiązane z danymi zebranymi w innej części firmy, a te relacje mogą służyć do ulepszania procesów biznesowych i wykonywania analiz biznesowych w całej organizacji. Zapewnienie łatwego, bezpiecznego, stabilnego dostępu do danych biznesowych, bez względu na to, który system jest „właścicielem” danych, jest kluczowym warunkiem w naszej wizji integracji danych z modułem Human Resources.

Historycznie integrowanie danych między wieloma systemami było trudne.
Microsoft podejmuje działania w celu ułatwienia integracji danych, a dużym krokiem w tym kierunku jest usługa [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Docelowo usługa Common Data Service stanie się preferowanym publicznym interfejsem dostępu do danych modułu Human Resources. Zakładamy, że z czasem wszystkie najważniejsze dane zarządzane przez moduł Human Resources zostaną udostępnione w usłudze Common Data Service. Rekomendujemy Common Data Service jako technologię, której należy używać do większości aplikacji integrujących. Zdajemy sobie sprawę, że nie wszystkie dane potrzebne Twojej aplikacji występują obecnie w usłudze Common Data Service, a harmonogramy projektów mogą wymagać alternatywnej technologii, dlatego prosimy o poinformowanie nas, czy i w jakim zakresie Common Data Service nie spełnia Twoich wymagań w zakresie integracji.

## <a name="integration-technologies"></a>Technologie integracji

W poniższych sekcjach opisano różne technologie integracji danych, które można stosować do modułu Human Resources.

### <a name="common-data-service-entities"></a>Jednostki usługi Common Data Service

Common Data Service jest preferowanym publicznym interfejsem dostępu do danych modułu Human Resources. Usługa Common Data Service jest zbudowana na dojrzałej platformie wyrosłej z platformy „XRM” systemu Dynamics 365, na której bazują rozwiązania platformy [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement).

Usługa Common Data Service stanowi platformę dla jednostek danych oraz interfejsu API umożliwiającego dostęp do tych jednostek. Po wdrożeniu modułu Human Resources w organizacji łączy się on z wystąpieniem usługi Common Data Service, a jednostki zawierające dane modułu Human Resources są wdrażane w tym wystąpieniu usługi Common Data Service, dzięki czemu jednostki i ich dane są dostępne dla wszystkich aplikacji łączących się z wystąpieniem usługi Common Data Service. W zależności od tego, których aplikacji modułu Human Resources używasz, moduł wykonuje operacje na danych bezpośrednio na jednostkach usługi Common Data Service (w przypadku aplikacji Attract i Onboard) lub synchronizuje dane z/do jednostek usługi Common Data Service.

Gdy jednostki danych udostępniające dane potrzebne aplikacjom integrującym znajdą się w usłudze Common Data Service, można w pełni wykorzystywać [usługę Common Data Service i obsługiwane przez nią interfejsy API](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Wśród obsługiwanych interfejsów API jest [internetowy interfejs API systemu Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), który implementuje protokół OData umożliwiającą dostęp do danych usługi Common Data Service.

Jednostki usługi Common Data Service i powiązane interfejsy API są najlepszą opcją uzyskiwania dostępu do danych modułu Human Resources z aplikacji internetowych, internetowych usług/interfejsów API oraz z innych aplikacji łączących się ze źródłami danych OData.

> [!NOTE]
> Decyzja o nadaniu usłudze Common Data Service statusu preferowanego interfejsu dostępu do danych modułu Human Resources jest stosunkowo świeża, dlatego może się okazać, że jednostki danych modułu Human Resources niezbędne w Twojej integracji nie są jeszcze dostępne w usłudze Common Data Service<sup>1</sup>. Jeśli jednostki modułu Human Resources wymagane w integracji nie są jeszcze dostępne, trzeba poczekać na ich udostępnienie albo użyć jednej z innych technologii integracji opisanych poniżej.
> 
> Domyślnie integracja za pomocą usługi Common Data Service jest wyłączona w nowych środowiskach, w których nie ma danych demonstracyjnych. Jest ona włączana w nowych środowiskach, które zawierają dane demonstracyjne, a synchronizacja danych rozpoczyna się w momencie zainicjowania obsługi środowiska. Po przygotowaniu środowiska do synchronizacji danych można włączyć integrację.

<sup>1</sup>Aby wyświetlić listę jednostek modułu Human Resources dostępnych w usłudze Common Data Service, zobacz [Human Resources i Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities). W przypadku aplikacji Attract i Onboard wszystkie jednostki są dostępne w usłudze Common Data Service.

### <a name="dmfdixf-entities"></a>Jednostki struktury DMF/DIXF

Moduł Human Resources, zbudowany głównie na tej samej platformie, co aplikacje modułu Finance and Operations, dostarcza [strukturę zarządzania danymi (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json), czasami nazywaną także strukturą eksportu i importu danych, lub DIXF, oraz zbiór jednostek danych, których można używać do importowania/eksportowania danych do/z modułu Human Resources. Mimo iż preferowanym interfejsem integracji danych modułu Human Resources są jednostki usługi Common Data Service, jednostki struktury DMF nadal będą przydatne w pewnych okolicznościach, np.:

- Jednostki usługi Common Data Service nie są jeszcze dostępne.

- Integracja wymaga wydajnych funkcji zbiorczego importu/eksportu danych.

Obecnie jednostki struktury DMF zapewniają najbardziej kompletny zakres pokrycia danych modułu Human Resources.

Struktura DMF nie nadają się do integracji w czasie rzeczywistym (na przykład wtedy, gdy jest wymagana bezpośrednia informacja zwrotna od użytkownika w interfejsie użytkownika), ponieważ operacje pakietowe są zaplanowanymi zadaniami wsadowymi, a zazwyczaj występuje opóźnienie co najmniej 1-2 minut, zanim usługa przetwarzania wsadowego pobierze zadanie do wykonania, a trzeba jeszcze doliczyć czas potrzebny na przeprowadzenie operacji importu/eksportu.

Struktura DMF może być najlepszą opcją, gdy jest wymagana duża przepustowość (np. w zaplanowanej nocnej operacji importu/eksportu wielu tysięcy rekordów).

> [!NOTE]
> Struktury DMF nie można używać w aplikacjach Attract ani Onboard.

### <a name="dmf-package-rest-api"></a>Interfejs API REST pakietów struktury DMF

Struktura DMF udostępnia interfejs [API REST](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) do wykonywania operacji na pakietach danych. Ten interfejs API może służyć do programowania interakcji ze strukturą DMF, w tym np. następujących akcji:

- Importowanie pakietu danych.

- Eksportowanie pakietu danych.

- Sprawdzanie stanu operacji importu/eksportu.

Interfejs API REST pakietów struktury DMF jest w pełni obsługiwany w aplikacji Core HR modułu Human Resources.

### <a name="azure-sql-db-byod"></a>Baza danych SQL Azure (BYOD)

Ponadto struktura DMF oferuje bardzo zaawansowaną funkcję (zazwyczaj nazywaną [Używanie własnej bazy danych](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database), lub BYOD), która umożliwia modułowi Human Resources eksportowanie danych do Twojej własnej bazy danych SQL w systemie Microsoft Azure. Zapewnia to ogromną elastyczność, ponieważ gdy dane znajdują się w Twojej własnej bazie danych SQL, możesz używać dowolnych aplikacji lub oprogramowania pośredniczącego, które są w stanie łączyć się z bazą danych SQL.

Zasadniczo rozwiązanie BYOD należy traktować jako tylko do odczytu. O ile w bazie danych SQL systemu Azure można przechowywać dowolne dane (w tym zestawy połączonych danych) i wykonywać na nich najróżniejsze operacje, takie dane nie będą synchronizowane z modułem Human Resources.

Funkcja BYOD nadaje się do rozwiązań sprawozdawczych, integracji danych, zestawów połączonych danych i jako źródło danych dla potoku w usłudze [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/).

> [!NOTE]
> Funkcji BYOD nie można używać w aplikacjach Attract ani Onboard.

### <a name="odata-enabled-entities"></a>Jednostki obsługujące protokół OData

Większość jednostek struktury DMF jest również dostępnych za pośrednictwem usługi danych modułu Human Resources (protokołu OData). Zasadniczo dokumentacja [usługi OData dla aplikacji Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) ma zastosowanie również do modułu Human Resources, bez części dotyczącej tworzenia własnych jednostek do udostępnienia przez protokół OData.

Co prawda preferowanym rozwiązaniem jest usługa Common Data Service oraz implementacja protokołu OData w usłudze Common Data Service (realizowana za pomocą [internetowego interfejsu API systemu Dynamics 365](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))), a nie usługa danych w module Human Resources, ale obecnie jednostki danych usługi modułu Human Resources zapewniają bardziej kompletny zakres pokrycia danych modułu Human Resources.

### <a name="excel-add-in"></a>Dodatek programu Excel

[Dodatek programu Excel](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) na poziomie podstawowym używa jednostek obsługujących protokół OData. Umożliwia użytkownikom końcowym wygodne pobieranie i modyfikowanie danych modułu Human Resources za pośrednictwem dobrze znanego interfejsu użytkownika programu Excel.

Dodatek programu Excel nadaje się do spontanicznego importowania/eksportowania danych przez specjalistów biznesowych. W przypadku cyklicznej integracji danych, która wymaga programistycznej automatyzacji, bardziej odpowiednia jest inna technologia.

### <a name="data-integrator"></a>Integrator danych

Środowisko administratora w usłudze Common Data Service zawiera [usługę Integratora danych](https://docs.microsoft.com/powerapps/administrator/data-integrator), której można używać do integrowania danych z/do usługi Common Data Service. Integrator danych może służyć do definiowania projektów integracji (często opartych na wstępnie zdefiniowanych szablonach, które deweloperzy aplikacji dostosowali do określonych integracji). Można zaplanować automatyczne wykonywanie projektów integracji według cyklicznego harmonogramu lub uruchamiać je ręcznie.

Projekty Integratora danych nadają się do wsadowych integracji w usłudze Common Data Service i stanowią doskonały wybór przy integrowaniu danych między różnymi aplikacjami systemu Dynamics 365. Na przykład Microsoft dostarcza gotowy szablon Integratora danych, który umożliwia integrowanie danych z modułu Human Resources do aplikacji Dynamics 365 Finance. Aby uzyskać więcej informacji, zobacz [Integracja z programu Dynamics 365 Human Resources do programu Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Zapytanie zaawansowane

Integrator danych współpracuje również z narzędziem [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) (za pośrednictwem swojej funkcji [Zapytanie zaawansowane](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering)).
Power Query umożliwia zaawansowane, elastyczne filtrowanie i przekształcanie danych, w tym z wykorzystaniem rozbudowanego języka formuł M, i prawdopodobnie jest znane osobom, które mają doświadczenie w tworzeniu raportów w usłudze Power BI.

## <a name="deciding-on-an-integration-technology"></a>Decydowanie o technologii integracji

Przy tak dużej liczbie dostępnych technologii integracji zdecydowanie się na konkretną strategię integracji może przyprawiać o ból głowy. Z czasem, a zwłaszcza wraz z poszerzaniem zakresu pokrycia danych w usłudze Common Data Service, decyzja stanie się łatwiejsza, a w większości przypadków Common Data Service będzie preferowanym interfejsem dostępu do danych. Ale do tego czasu może się okazać, że Common Data Service jeszcze nie zaspokaja Twoich potrzeb. Poniższa tabela zawiera podsumowanie wybranych kluczowych cech różnych technologii integracji.

| Technologia/narzędzie/interfejs API    | Integracje cykliczne                   | Synchronicznie/asynchronicznie                    | Dostęp programistyczny za pośrednictwem interfejsu API        | Wolumen danych                                   | Zakres pokrycia danych                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Jednostki usługi Common Data Service           | Tak, za pomocą Integratora danych lub oprogramowania pośredniczącego | Synchronicznie, asynchronicznie, wsadowo (za pomocą Integratora danych) | Tak, za pośrednictwem internetowy interfejs API systemu Dynamics 365 (OData) | Zależy od konkretnego zastosowania (obsługuje stronicowanie dla użytkowania interaktywnego) | Coraz lepszy<sup>2</sup>                       |
| Jednostki struktury DMF           | Tak, planowane za pomocą oprogramowania pośredniczącego        | Asynchronicznie, wsadowo                                | Tak, za pośrednictwem interfejsu API REST pakietów struktury DMF         | Duży (setki tysięcy rekordów)                    | Wysoka                                |
| Interfejs API REST pakietów struktury DMF   | Tak, planowane za pomocą oprogramowania pośredniczącego        | Asynchronicznie, wsadowo                                | Tak                                       | Duży (setki tysięcy rekordów)                    | Interfejs API obsługuje wszystkie jednostki struktury DMF       |
| BYOD                   | Tak, planowane przez administratora w module Human Resources        | Asynchronicznie, wsadowo                                | Nie<sup>3</sup>                                    | Duży (setki tysięcy rekordów)                    | Obsługuje wszystkie jednostki struktury DMF           |
| Jednostki obsługujące protokół OData | Tak, przy użyciu oprogramowania pośredniczącego                    | Synchronizuj                                        | Tak, za pośrednictwem usługi danych modułu Human Resources (protokołu OData)  | Zależy od konkretnego zastosowania (obsługuje stronicowanie dla użytkowania interaktywnego) | Wysoka                                |
| Dodatek programu Excel           | Nie                                       | Synchronizuj                                        | Nie                                        | Średni (dziesiątki tysięcy rekordów)                      | Obsługuje wszystkie jednostki obsługujące protokół OData |
| Integrator danych        | Tak, planowane w Integratorze danych        | Asynchronicznie, wsadowo                                | Nie                                        | Zależy od konkretnego zastosowania                                       | Obsługuje wszystkie jednostki usługi Common Data Service           |

<sup>2</sup>Microsoft mocno inwestuje w poprawę zakresu pokrycia danych przez jednostki usługi Common Data Service oraz rekomenduje Common Data Service jako preferowany interfejs dostępu do danych, o ile tylko pokrycie obejmuje konieczne dane. Obecnie zakres pokrycia danych w usłudze Common Data Service jest znacznie niższy niż w jednostkach struktury DMF i jednostkach obsługujących interfejs OData.

<sup>3</sup>Dostęp do bazy danych SQL można uzyskać programistycznie.

## <a name="summary"></a>Sumarycznie

Dane biznesowe Twojej firmy są cennym zasobem, ale ich wartość może znacznie spaść, jeśli trudno je wykorzystywać do konkretnych celów (takich jak sprawozdawczość, łączenie danych w zestawy czy niestandardowe aplikacje). Moduł Dynamics 365 Human Resources oferuje kilka technologii pracy z danymi poza interfejsem użytkownika aplikacji modułu Human Resources, umożliwiając aplikacjom integrującym dostęp do tych danych. Ten temat zawiera opis dostępnych technologii integracji oraz ich wybranych najważniejszych cech. Te informacje powinny być pomocne w podejmowaniu lepszych decyzji o metodach, które należy zastosować w swoich projektach integracji.

