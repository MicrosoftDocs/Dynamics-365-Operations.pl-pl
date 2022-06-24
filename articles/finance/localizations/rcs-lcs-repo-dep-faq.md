---
title: Regulatory Configuration Service (RCS) – deprekacja pamięci w Lifecycle Services (LCS)
description: Ten artykuł zawiera informacje o wycofaniu z użytku magazynu Microsoft Dynamics Lifecycle Services (LCS), które jest planowane w ramach wdrażania globalnego repozytorium Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: 4a35941d1521d26f95bacf29213fee42daeb42ab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849739"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) — deprekacja pamięci w Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

Zrezygnowano z używania Microsoft Dynamics Lifecycle Services (LCS) jako repozytorium do przechowywania konfiguracji raportowania elektronicznego (ER). To wycofanie wymaga następujących zmian:

- Wyprodukowane przez firmę Microsoft konfiguracje używane w Microsoft Dynamics 365 nie będą już publikowane w bibliotece udostępnionych zasobów w LCS. Zamiast tego, będą one publikowane tylko poprzez globalne repozytorium RCS. Jednakże, konfiguracje dla Dynamics AX 2012 będą nadal publikowane do biblioteki aktywów wspólnych w LCS aż do zakończenia cyklu wsparcia dla AX 2012.
- Funkcja umożliwiająca przesyłanie konfiguracji do biblioteki zasobów projektu w LCS z aplikacji finansowych i operacyjnych oraz z RCS zostanie dezaktywowana. Jednakże, nadal będziesz mógł używać przeglądarki w LCS do wgrywania konfiguracji do biblioteki zasobów projektu. W związku z tym, nadal będziesz mógł dodawać konfiguracje do LCS, aby mogły być one zawarte w pakietach rozwiązań.
- Import konfiguracji z systemu LCS będzie nadal dostępny i obsługiwany w aplikacjach finansowych i operacyjnych oraz w RCS przez pewien czas. Jednakże, funkcjonalność ta zostanie w końcu wycofana. (Dokładna data wycofania zostanie ogłoszona później).

## <a name="deprecation-notice"></a>Powiadomienie o wycofaniu

Informacja o zaprzestaniu korzystania z LCS jako magazynu została podana w [Usunięte lub wycofane funkcje w Dynamics 365 Finance - informacja o wycofaniu LCS](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Planowana data wycofania to 1 kwietnia 2022 roku.

## <a name="key-features"></a>Najważniejsze funkcje

- Użyj funkcji RCS, aby tworzyć i edytować konfiguracje raportowania elektronicznego i funkcje globalizacji.
- Wypychanie konfiguracji bezpośrednio z konstruktora RCS do połączonej aplikacji, takiej jak środowisko Dynamics 365 Finance, dzięki czemu można szybko wprowadzać i testować zmiany w konfiguracjach.
- Centralne przechowywanie, udostępnianie i zarządzanie cyklem życia zarówno w przypadku konfiguracji raportowania elektronicznego, jak i funkcji globalizacji za pomocą scentralizowanego magazynu repozytorium globalnego.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Wytyczne dotyczące działań jednorazowych i bieżących

W tej sekcji opisano zestaw czynności, które należy wykonać jednorazowo. Opisuje również czynności, które muszą być wykonywane na bieżąco po zakończeniu pracy.

### <a name="one-time-action"></a>Akcja jednorazowa

Zaimportuj wszystkie wymagane konfiguracje z LCS do RCS, a następnie opublikuj je z RCS do globalnego repozytorium. Jeśli używasz bibliotek zasobów specyficznych dla projektu do przechowywania konfiguracji pochodnych w LCS, poniższe kroki muszą być wykonane, gdy LCS jest wciąż dostępny.

1. Jeśli instancja RCS nie jest jeszcze dostępna, skonfiguruj ją. Aby uzyskać więcej informacji, zobacz [omówienie RCS](rcs-overview.md).
2. W udostępnionej instancji RCS, dla każdego projektu LCS w bibliotece aktywów, który zawiera pochodne konfiguracje ER, zarejestruj odpowiednie repozytorium LCS.
3. Zaimportuj konfiguracje ER z repozytoriów LCS do RCS. Aby uzyskać więcej informacji, zobacz temat [Importowanie konfiguracji z usług LCS](/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services).
4. Jeśli globalne repozytorium nie zostało automatycznie dostarczone, zarejestruj je w RCS.
5. Prześlij wszystkie pochodne konfiguracje z bieżącej instancji RCS do globalnego repozytorium. Użyj funkcji **Pakiety konfiguracji**, aby pomóc w przekazywaniu. Aby uzyskać więcej informacji, zobacz [Przesyłanie do globalnego repozytorium RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>Przyszłość

Użyj konstruktorów wizualnych w RCS do następujących celów:

- Rozszerzaj szablony dostarczone przez firmę Microsoft.
- Twórz nowe konfiguracje wymagane przez organizację.
- Dostosuj funkcje globalizacji dla fakturowania elektronicznego i usługi obliczania podatku.

Użyj repozytorium globalnego do następujących celów:

- Uzyskuj dostęp do konfiguracji wyprodukowanych przez firmę Microsoft i funkcji globalizacji.
- Umożliwia przekazywanie konfiguracji utworzonych lub rozszerzonych do globalnego repozytorium w celu przechowywania oraz udostępniania ich w środowiskach aplikacji Dynamics 365 własnej organizacji lub organizacjom zewnętrznym. Aby uzyskać więcej informacji, zobacz temat [Tworzenie konfiguracji ER w RCS i przekazywanie do globalnego serwera repo](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>Czy ta zmiana oznacza, że LCS nie może być używany jako centralny magazyn dla konfiguracji?

Tak. Funkcja umożliwiająca przesyłanie konfiguracji do biblioteki zasobów projektu w LCS z aplikacji finansowych i operacyjnych zostanie wycofana. Jednakże, nadal będziesz mógł używać przeglądarki w LCS do wgrywania konfiguracji do biblioteki zasobów projektu.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Myślałem, że RCS to zastępcze repozytorium do importowania globalnych plików szablonów. Nie sądziłem, że jest on używany do przechowywania konfiguracji. Co tu jest poprawne?

RCS to usługa projektowa służąca do tworzenia i edycji konfiguracji ER. RCS ma swoje własne repozytorium, które jest znane jako repozytorium globalne. To repozytorium jest używane do przechowywania konfiguracji, które są tworzone w RCS. Po zaprzestaniu używania LCS jako magazynu, repozytorium globalne będzie jedynym źródłem dla konfiguracji Microsoft. Musisz wykonać jednorazową akcję, aby zaimportować wszystkie wymagane konfiguracje z LCS do RCS, a następnie opublikować je z RCS do Globalnego repozytorium.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Bez LCS, jaki jest sugerowany sposób przechowywania konfiguracji tak, aby konfiguracje „testowe” i „produkcyjne” mogły być łatwo zarządzane i przenoszone?

System RCS używa koncepcji *połączonej aplikacji*. Połączona aplikacja tworzy połączenie między RCS a dowolną instancją aplikacji finansowych i operacyjnych. Ponieważ do edycji konfiguracji można wykorzystać RCS, połączoną aplikację można wykorzystać do przesyłania konfiguracji bezpośrednio z projektanta do środowisk aplikacji finansowych i operacyjnych. Dzięki temu można szybko zmieniać i testować konfiguracje, a nie korzystać z magazynu na poziomie projektu usługi LCS.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>Czy są jakieś przykłady, które pokazują konfigurację i zarządzanie?

Nie ma żadnych przykładów, ale możesz wykonać kroki opisane wcześniej w tym artykule, aby migrować konfiguracje do repozytorium globalnego RCS.

### <a name="is-rcs-a-prerequisite-to-configure-electronic-reporting"></a>Czy program RCS jest warunkiem wstępnym do skonfigurowania raportowania elektronicznego?

Tak. Usługa RCS zawiera funkcje, które obsługują konfigurację funkcji globalizacji, używanych przez usługi globalizacji, takie jak fakturowanie elektroniczne i usługa obliczania podatku. Jednak usługa ma tę samą funkcjonalność konstruktora wizualizacji, która umożliwia rozszerzanie lub tworzenie nowych konfiguracji raportowania elektronicznego. Ponadto usługa RCS zapewnia zarządzanie cyklem życia zarówno dla konfiguracji raportowania elektronicznego, jak i funkcji globalizacji.

### <a name="which-regions-can-rcs-be-deployed-in"></a>W których regionach można wdrożyć usługę RCS?

RCS jest dostępny w następujących regionach platformy Azure:

- Stany Zjednoczone
- Indie
- Francja
- Europa

Aby uzyskać więcej informacji o pomocy technicznej dotyczącej produktów, zobacz [Omówienie usług globalizacji systemu Dynamics](globalization-services-overview.md). Aby uzyskać więcej informacji na temat obsługi lokalizacji geograficznej, zobacz temat [Dynamics 365 oraz Power Platform: Dostępność, lokalizacja danych, język i lokalizacja](https://aka.ms/rcs/D365Productavailabilityguide).

### <a name="whats-the-cost-of-using-rcs"></a>Jaki jest koszt używania usługi RCS?

RCS i repozytorium Globalizacja są udostępniane bezpłatnie w ramach istniejących licencji na aplikacje finansowe i operacyjne. Nie są skojarzone osobne koszty z użyciem usługi projektowania RCS lub przechowywaniem konfiguracji w repozytorium globalnym. Obecnie nie ma limitu liczby konfiguracji lub połączonych aplikacji.