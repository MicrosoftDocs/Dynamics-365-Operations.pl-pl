---
title: Porady dotyczące dodatku Widoczność magazynu
description: Ten artykuł zawiera kilka wskazówek, które należy rozważyć podczas konfigurowania i używania dodatku Widoczność zapasów.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3bdd161815a15d5c39b3c0afc176a288c8d9055a
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306094"
---
# <a name="inventory-visibility-tips"></a>Porady dotyczące dodatku Widoczność magazynu

[!include [banner](../includes/banner.md)]

Oto kilka wskazówek, które należy rozważyć podczas konfigurowania i używania dodatku Widoczność zapasów:

- Obecnie dodatek Widoczność zapasów obsługuje tylko środowiska Microsoft Dataverse utworzone za pomocą usługi Lifecycle Services Microsoft Dynamics (LCS). Jeżeli środowisko Dataverse zostało utworzone w inny sposób (na przykład za pomocą centrum administracyjnego Power Apps) i jest połączone ze środowiskiem Dynamics 365 Supply Chain Management, należy najpierw skontaktować się z zespołem ds. produktu Widoczność magazynu, aby rozwiązać ten problem z mapowaniem. Kontakt z zespołem można uzyskać pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). Zespół poinformuje Cię, kiedy środowisko jest gotowe do zainstalowania dodatku Widoczność zapasów.
- Jeśli masz więcej niż jedno środowisko usługi LCS, utwórz inną aplikację Azure Active Directory (Azure AD) dla każdego środowiska. Jeśli do zainstalowania dodatku Widoczność magazynu dla różnych środowisk używasz tego samego identyfikatora aplikacji i identyfikatora dzierżawcy, wystąpi problem z tokenem w starszych środowiskach. Będzie prawidłowe tylko ostatnie wystąpienie zainstalowanego dodatku Widoczność zapasów.
- Widoczność zapasów nie jest obecnie obsługiwana w przypadku środowisk hostowanych w chmurze. Jest ona obsługiwana tylko w przypadku środowisk Tier-2+.
- Interfejs Application Programming Interface (API) aktualnie obsługuje wykonywanie zapytań o maksymalnie 100 pojedynczych towarów według wartości `ProductID`. W każdym zapytaniu można określić również kilka wartości `SiteID` i `LocationID`. Maksymalny limit jest zdefiniowany jako `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- API zbiorcze może zwrócić maksymalnie 512 rekordów dla każdego żądania.
- Źródło danych `fno` jest zarezerwowane dla Supply Chain Management. Jeśli dodatek Widoczność magazynu jest zintegrowany ze środowiskiem Supply Chain Management, nie zaleca się usuwania konfiguracji związanych z `fno` w [źródle danych](inventory-visibility-configuration.md#data-source-configuration).
- Widoczność magazynu nie może zmienić żadnych danych dla źródła danych `fno`. Przepływ danych jest jednokierunkowy, co oznacza, że wszystkie zmiany ilościowe dla źródła danych `fno` muszą pochodzić z twojego środowiska Supply Chain Management. Dlatego nie możesz używać API do wysyłania żądań zmiany lub rezerwacji dla źródła danych `fno`.
- Jeśli dodasz jedną lub więcej nowych miar do swojego środowiska Supply Chain Management, powinieneś dodać je również w Widoczności zapasów. Jednak wszystkie zmiany ilościowe dla nowych działań muszą pochodzić z waszego środowiska Supply Chain Management.
- [Konfiguracja partycji](inventory-visibility-configuration.md#partition-configuration) składa się obecnie z dwóch wymiarów podstawowych (`SiteId` i `LocationId`) wskazujących sposób dystrybuowania danych. Operacje wykonywane na tej samej partycji mogą uzyskać wyższą wydajność przy niższym koszcie. Rozwiązanie domyślnie zawiera tę konfigurację partycji. Dlatego *nie trzeba obliczać jej ręcznie*. Nie dostosowuj domyślnej konfiguracji partycji. Usunięcie lub zmiana może spowodować nieoczekiwany błąd.
- Wymiarów podstawowych określonych w konfiguracji partycji nie należy definiować w [konfiguracji hierarchii indeksu produktów](inventory-visibility-configuration.md#index-configuration).
- Konfiguracja hierarchii indeksu [produktu](inventory-visibility-configuration.md#index-configuration) musi zawierać co najmniej jedną hierarchię indeksu (na przykład zawierającą wymiar podstawowy `Empty`), w przeciwnym razie zapytania zakończą się niepowodzeniem z błędem "Nie ustawiono hierarchii indeksu".
- Źródło danych `@iv` jest wstępnie zdefiniowanym źródłem danych, a miary fizyczne zdefiniowane w `@iv` za pomocą prefiksu `@` są miarami wstępnie zdefiniowanymi. Te miary są wstępnie zdefiniowaną konfiguracją funkcji alokacji, więc nie należy ich zmieniać ani usuwać albo prawdopodobnie wystąpią nieoczekiwane błędy podczas korzystania z funkcji alokacji.
- Do wstępnie zdefiniowanej miary obliczanej można dodawać nowe miary fizyczne `@iv.@available_to_allocate`, ale nie można zmieniać ich nazwy.
- Jeśli użytkownik przywraca bazę danych Supply Chain Management, przywrócona baza danych może zawierać dane, które nie są spójne z danymi poprzednio zsynchronizowanymi przez widoczność zapasów do Dataverse. Ta niespójność danych może spowodować błędy systemowe i inne problemy. Dlatego przed przywróceniem bazy danych Supply Chain Management ważne jest, aby przed przywróceniem bazy wyczyścić wszystkie dane związane z widocznością zapasów z Dataverse. Więcej szczegółów znajdziesz w [Wyczyść dane widoczności zapasów przed przywróceniem bazy danych Dataverse Supply Chain Management](inventory-visibility-setup.md#restore-environment-database).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
