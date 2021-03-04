---
title: Wybieranie technologii integracji danych
description: Ten artykuł zawiera informacje dotyczące integrowania z danymi zarządzanymi przez Human Resources. Opisuje różne technologie integracji, które pomagają określić, które technologie najlepiej pasują do potrzeb użytkownika.
author: andreabichsel
manager: AnnBe
ms.date: 02/28/2020
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
ms.openlocfilehash: 9e6eeac66cff24d193e30aa942039707fc0aed52
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528348"
---
# <a name="choose-a-data-integration-technology"></a>Wybieranie technologii integracji danych

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten artykuł zawiera informacje dotyczące integrowania z danymi zarządzanymi przez Dynamics 365 Human Resources. Opisuje różne technologie integracji, które pomagają określić, które technologie najlepiej pasują do potrzeb użytkownika.

## <a name="data-integration-background"></a>Tło integracji danych

Dane biznesowe to kluczowy zasób, który decyduje o unikatowości firmy. Dane Twojej firmy są bardzo cenne. Relacje między danymi zebranymi w firmie można stosować w celu ulepszenia procesów biznesowych i analizy biznesowej w całej organizacji. Firma Microsoft dąży do zapewnienia łatwego, bezpiecznego i stabilnego dostępu do danych biznesowych, niezależnie od tego, z którego systemu pochodzi.

Historycznie integrowanie danych między wieloma systemami było trudne.
Microsoft podejmuje działania w celu ułatwienia integracji danych, a dużym krokiem w tym kierunku jest usługa [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Human Resources sprawia, że Common Data Service stanie się preferowanym publicznym interfejsem dostępu do danych Human Resources. Zakładamy, że z czasem wszystkie najważniejsze dane zarządzane przez moduł Human Resources zostaną udostępnione w usłudze Common Data Service. Rekomendujemy Common Data Service jako technologię, której należy używać do większości aplikacji integrujących.

Okazuje się, że Common Data Service nie zawiera on jeszcze wszystkich danych wymaganych przez aplikację. Ponadto zdajemy sobie sprawę, że oś czasu projektu może wymagać rozwiązania alternatywnego. Pamiętaj, aby powiadomić nas, gdy Common Data Service nie spełnia wymagań dotyczących integracji.

## <a name="integration-technologies"></a>Technologie integracji

W poniższych sekcjach opisano różne technologie integracji danych, które można stosować do modułu Human Resources.

### <a name="common-data-service-entities"></a>Jednostki usługi Common Data Service

Common Data Service jest preferowanym publicznym interfejsem dostępu do danych modułu Human Resources. Usługa pochodzi z platformy Dynamics 365 XRM, która jest używana przez [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement).

Common Data Service dostarcza platformę i interfejs API dla jednostek danych. Wdrożenie modułu Human Resources powoduje połączenie z wystąpieniem Common Data Service. Jednostki do wdrożenia danych Human Resources w tym wystąpieniu Common Data Service. Jednostki i ich dane są dostępne dla każdej aplikacji, która może połączyć się z wystąpieniem Common Data Service. Human Resources synchronizują dane z jednostkami Common Data Service.

Jeśli jednostki danych wymagane przez aplikacje integrujące są w Common Data Service, można w pełni używać [obsługi Common Data Service i interfejsów API](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Wśród obsługiwanych interfejsów API jest [internetowy interfejs API systemu Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), który implementuje protokół OData umożliwiającą dostęp do danych usługi Common Data Service.

Jednostki usługi Common Data Service i powiązane interfejsy API są najlepszą opcją uzyskiwania dostępu do danych modułu Human Resources z aplikacji internetowych, internetowych usług/interfejsów API oraz z innych aplikacji łączących się ze źródłami danych OData.

> [!NOTE]
> Decyzja o nadaniu usłudze Common Data Service statusu preferowanego interfejsu dostępu do danych modułu Human Resources jest stosunkowo świeża, dlatego może się okazać, że jednostki danych modułu Human Resources niezbędne w Twojej integracji nie są jeszcze dostępne w usłudze Common Data Service.
</br>
> Aby wyświetlić listę jednostek modułu Human Resources dostępnych w usłudze Common Data Service, zobacz [Human Resources i Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities).
> </br>
> Jeśli jednostki modułu Human Resources wymagane w integracji nie są jeszcze dostępne, trzeba poczekać na ich udostępnienie albo użyć jednej z innych technologii integracji opisanych poniżej.
> </br>
> Domyślnie integracja za pomocą Common Data Service  jest wyłączona w nowych środowiskach, w których nie ma danych demonstracyjnych. Jest ona włączana w nowych środowiskach, które zawierają dane demonstracyjne, a synchronizacja danych rozpoczyna się w momencie zainicjowania obsługi środowiska. Po przygotowaniu środowiska do synchronizacji danych można włączyć integrację.

### <a name="dmfdixf-entities"></a>Jednostki struktury DMF/DIXF

Human Resources, zbudowane głównie na tej samej platformie co aplikacje Finance and Operations, stanowią [Data Management Framework (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json). DMF jest również znane jako Struktura importu i eksportu danych (usługa DIXF). Human Resources dostarczają zestawy jednostek danych, które można wykorzystywać do importowania i eksportowania danych Human Resources. Mimo iż preferowanym interfejsem integracji danych modułu Human Resources są jednostki usługi Common Data Service, jednostki struktury DMF nadal są przydatne w pewnych okolicznościach, np.:

- Jednostki usługi Common Data Service nie są jeszcze dostępne.

- Integracja wymaga wydajnych funkcji zbiorczego importu/eksportu danych.

Obecnie jednostki struktury DMF zapewniają najbardziej kompletny zakres pokrycia danych modułu Human Resources.

DMF nie jest odpowiednie do integracji w czasie rzeczywistym, na przykład wtedy, gdy potrzebna jest natychmiastowa opinia użytkownika w interfejsie użytkownika. Operacje pakietowe są planowanymi zadaniami wsadowymi i często wymagają minimalnego opóźnienia wynoszącego 1-2 minut, zanim usługa wsadowa wytworzy zadanie do wykonania oraz dowolnego czasu wymaganego do wykonania operacji importu/eksportu.

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

Ponadto struktura DMF oferuje bardzo zaawansowaną funkcję (nazywaną [Używanie własnej bazy danych](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database), lub BYOD), która umożliwia modułowi Human Resources eksportowanie danych do Twojej własnej bazy danych SQL w systemie Microsoft Azure. Ta funkcja zapewnia ogromne możliwości. Gdy dane znajdują się w Twojej własnej bazie danych SQL, możesz używać dowolnych aplikacji lub oprogramowania pośredniczącego, które są w stanie łączyć się z bazą danych SQL.

BYOD jest głównie rozwiązaniem tylko do odczytu. O ile w bazie danych SQL systemu Azure można przechowywać dowolne dane (w tym zestawy połączonych danych) i wykonywać na nich najróżniejsze operacje, takie dane nie są synchronizowane z modułem Human Resources.

Funkcja BYOD nadaje się do rozwiązań sprawozdawczych, integracji danych, zestawów połączonych danych i jako źródło danych dla potoku w usłudze [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/).

> [!NOTE]
> Funkcji BYOD nie można używać w aplikacjach Attract ani Onboard.

### <a name="odata-enabled-entities"></a>Jednostki obsługujące protokół OData

Większość jednostek struktury DMF jest również dostępnych za pośrednictwem usługi danych modułu Human Resources (protokołu OData). Dokumentacja dostarczona dla [usługi OData Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) jest stosowana do Human Resources, z wyjątkiem tworzenia własnych jednostek do udostępnienia przez protokół OData.

Co prawda preferowanym rozwiązaniem jest usługa Common Data Service oraz implementacja protokołu OData w usłudze Common Data Service (realizowana za pomocą [internetowego interfejsu API systemu Dynamics 365](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))), a nie usługa danych w module Human Resources, ale obecnie jednostki danych usługi modułu Human Resources zapewniają bardziej kompletny zakres pokrycia danych modułu Human Resources.

### <a name="excel-add-in"></a>Dodatek programu Excel

[Dodatek programu Excel](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) na poziomie podstawowym używa jednostek obsługujących protokół OData. Umożliwia użytkownikom końcowym wygodne pobieranie i modyfikowanie danych modułu Human Resources za pośrednictwem dobrze znanego interfejsu użytkownika programu Excel.

Dodatek programu Excel nadaje się do spontanicznego importowania/eksportowania danych przez specjalistów biznesowych. W przypadku cyklicznej integracji danych, która wymaga programistycznej automatyzacji, bardziej odpowiednia jest inna technologia.

### <a name="data-integrator"></a>Integrator danych

Za pomocą [usługi Integratora danych](https://docs.microsoft.com/powerapps/administrator/data-integrator) można integrować dane z i do Common Data Service. Integrator danych pozwala definiować projekty integracji, często opartych na wstępnie zdefiniowanych szablonach, które deweloperzy aplikacji dostosowali do określonych integracji. Można zaplanować automatyczne wykonywanie projektów integracji według cyklicznego harmonogramu lub uruchamiać je ręcznie.

Projekty integratora danych są odpowiednie dla integracji partii Common Data Service. Stanowią one doskonały wybór w zakresie integracji między aplikacjami Dynamics 365. Na przykład Microsoft dostarcza szablon Integratora danych, który umożliwia integrowanie danych z Human Resources do Dynamics 365 Finance. Więcej informacji na temat szablonu można uzyskać w [Integracja z Dynamics 365 Human Resources do Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Zapytanie zaawansowane

Integrator danych współpracuje z narzędziem [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query), ale za pośrednictwem swojej [funkcji Zapytanie zaawansowane](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering). Power Query zapewnia wydajne, elastyczne filtrowanie i przekształcanie danych, w tym sformatowany w języku formuł M. Power Query prawdopodobnie będzie znajoma, jeśli wcześniej projektowano raporty Power BI.

## <a name="deciding-on-an-integration-technology"></a>Decydowanie o technologii integracji

Przy tak dużej liczbie dostępnych technologii integracji zdecydowanie się na konkretną strategię integracji może przyprawiać o ból głowy. Wraz z poszerzaniem zakresu pokrycia danych w usłudze Common Data Service, decyzja stanie się łatwiejsza, a w większości przypadków Common Data Service będzie preferowanym interfejsem dostępu do danych. Ale do tego czasu może się okazać, że Common Data Service jeszcze nie zaspokaja Twoich potrzeb. Poniższa tabela zawiera podsumowanie wybranych kluczowych cech opcji technologii integracji.

| Technologia/narzędzie/interfejs API    | Integracje cykliczne                   | Synchronicznie/asynchronicznie                    | Dostęp programistyczny za pośrednictwem interfejsu API        | Wolumen danych                                   | Zakres pokrycia danych                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Jednostki usługi Common Data Service           | Tak, za pomocą Integratora danych lub oprogramowania pośredniczącego | Synchronicznie, asynchronicznie, wsadowo (za pomocą Integratora danych) | Tak, za pośrednictwem internetowy interfejs API systemu Dynamics 365 (OData) | Zależy od konkretnego zastosowania (obsługuje stronicowanie dla użytkowania interaktywnego) | Coraz lepszy<sup>2</sup>                       |
| Jednostki struktury DMF           | Tak, planowane za pomocą oprogramowania pośredniczącego        | Asynchronicznie, wsadowo                                | Tak, za pośrednictwem interfejsu API REST pakietów struktury DMF         | Duży (setki tysięcy rekordów)                    | Wysoka                                |
| Interfejs API REST pakietów struktury DMF   | Tak, planowane za pomocą oprogramowania pośredniczącego        | Asynchronicznie, wsadowo                                | Tak                                       | Duży (setki tysięcy rekordów)                    | Interfejs API obsługuje wszystkie jednostki struktury DMF       |
| BYOD                   | Tak, planowane przez administratora w module Human Resources        | Asynchronicznie, wsadowo                                | Nie<sup>3</sup>                                    | Duży (setki tysięcy rekordów)                    | Obsługuje wszystkie jednostki struktury DMF           |
| Jednostki obsługujące protokół OData | Tak, przy użyciu oprogramowania pośredniczącego                    | Synchronizuj                                        | Tak, za pośrednictwem usługi danych modułu Human Resources (protokołu OData)  | Zależy od konkretnego zastosowania (obsługuje stronicowanie dla użytkowania interaktywnego) | Wysoka                                |
| Dodatek programu Excel           | Nie                                       | Synchronizuj                                        | Nie                                        | Średni (dziesiątki tysięcy rekordów)                      | Obsługuje wszystkie jednostki obsługujące protokół OData |
| Integrator danych        | Tak, planowane w Integratorze danych        | Asynchronicznie, wsadowo                                | Nie                                        | Zależy od konkretnego zastosowania                                       | Obsługuje wszystkie jednostki usługi Common Data Service           |

<sup>2</sup>firma Microsoft bardzo inwestuje w zwiększanie zakresu pokrycia danych dla jednostek Common Data Service. Zalecamy użycie Common Data Service, jeśli jest dostępna. Obecnie zakres pokrycia danych w usłudze Common Data Service jest niższy w porównaniu do jednostek struktury DMF i jednostek obsługujących protokuł OData.

<sup>3</sup>Dostęp do bazy danych SQL można uzyskać programistycznie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]