---
title: Regulatory Configuration Service (RCS) – deprekacja pamięci w Lifecycle Services (LCS)
description: Ten temat zawiera informacje o wycofaniu z użytku magazynu Microsoft Dynamics Lifecycle Services (LCS), które jest planowane w ramach wdrażania globalnego repozytorium Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 05/25/2021
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
ms.openlocfilehash: abaeb34db1d209fa8e5cc83a98c333f42e91f2d2
ms.sourcegitcommit: 7cda434becd198c1cd405e001289777ae7a24fe1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6127926"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) — deprekacja pamięci w Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

Zrezygnowano z używania Microsoft Dynamics Lifecycle Services (LCS) jako repozytorium do przechowywania konfiguracji raportowania elektronicznego (ER). To wycofanie wymaga następujących zmian:

- Wyprodukowane przez firmę Microsoft konfiguracje używane w Microsoft Dynamics 365 nie będą już publikowane w bibliotece udostępnionych zasobów w LCS. Zamiast tego, będą one publikowane tylko poprzez globalne repozytorium RCS. Jednakże, konfiguracje dla Dynamics AX 2012 będą nadal publikowane do biblioteki aktywów wspólnych w LCS aż do zakończenia cyklu wsparcia dla AX 2012.
- Funkcja, która umożliwia przekazywanie konfiguracji do biblioteki aktywówprojektu w LCS z aplikacji Finance and Operations oraz z usługi RCS, zostanie dezaktywowana. Jednakże, nadal będziesz mógł używać przeglądarki w LCS do wgrywania konfiguracji do biblioteki zasobów projektu. W związku z tym, nadal będziesz mógł dodawać konfiguracje do LCS, aby mogły być one zawarte w pakietach rozwiązań.
- Import konfiguracji z LCS będzie nadal dostępny i wspierany w aplikacjach Finance and Operations oraz w RCS, przez pewien czas. Jednakże, funkcjonalność ta zostanie w końcu wycofana. (Dokładna data wycofania zostanie ogłoszona później).

## <a name="deprecation-notice"></a>Powiadomienie o wycofaniu

Informacja o zaprzestaniu korzystania z LCS jako magazynu została podana w [Usunięte lub wycofane funkcje w Dynamics 365 Finance - informacja o wycofaniu LCS](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Planowana data wycofania to 1 kwietnia 2022 roku.

## <a name="key-features"></a>Najważniejsze funkcje

- Możesz użyć RCS do tworzenia i edycji konfiguracji. Konfiguracje te można następnie przesłać bezpośrednio z projektanta do podłączonej aplikacji. Dzięki temu można szybko zmieniać i testować konfiguracje.
- Globalne repozytorium jest scentralizowanym miejscem przechowywania wszystkich konfiguracji ER.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Wytyczne dotyczące działań jednorazowych i bieżących

W tej sekcji opisano zestaw czynności, które należy wykonać jednorazowo. Opisuje również czynności, które muszą być wykonywane na bieżąco po zakończeniu pracy.

### <a name="one-time-action"></a>Akcja jednorazowa

Zaimportuj wszystkie wymagane konfiguracje z LCS do RCS, a następnie opublikuj je z RCS do globalnego repozytorium. Jeśli używasz bibliotek zasobów specyficznych dla projektu do przechowywania konfiguracji pochodnych w LCS, poniższe kroki muszą być wykonane, gdy LCS jest wciąż dostępny.

1. Jeśli instancja RCS nie jest jeszcze dostępna, skonfiguruj ją. Aby uzyskać więcej informacji, zobacz [omówienie RCS](rcs-overview.md).
2. W udostępnionej instancji RCS, dla każdego projektu LCS w bibliotece aktywów, który zawiera pochodne konfiguracje ER, zarejestruj odpowiednie repozytorium LCS.
3. Zaimportuj konfiguracje ER z repozytoriów LCS do RCS. Aby uzyskać więcej informacji, zobacz temat [Importowanie konfiguracji z usług LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).
4. Jeśli globalne repozytorium nie zostało automatycznie dostarczone, zarejestruj je w RCS.
5. Prześlij wszystkie pochodne konfiguracje z bieżącej instancji RCS do globalnego repozytorium. Użyj **pakietów konfiguracji, które umożliwiają użytkownikowi przekazywanie wszystkich konfiguracji do systemu GR w jednej operacji**, aby pomóc w przekazywaniu. Aby uzyskać więcej informacji, zobacz [Przesyłanie do globalnego repozytorium RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>Przyszłość

Użyj projektantów wizualnych w RCS, aby stworzyć wszystkie nowe konfiguracje. Następnie prześlij konfiguracje do Globalnego repozytorium w celu przechowywania. Aby uzyskać więcej informacji, zobacz temat [Tworzenie konfiguracji ER w RCS i przekazywanie do globalnego serwera repo](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>Czy ta zmiana oznacza, że LCS nie może być używany jako centralny magazyn dla konfiguracji?

Tak. Funkcja, która umożliwia przekazywanie konfiguracji do biblioteki aktywów projektu w LCS z aplikacji Finance and Operations oraz z usługi RCS, zostanie wycofana. Jednakże, nadal będziesz mógł używać przeglądarki w LCS do wgrywania konfiguracji do biblioteki zasobów projektu.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Myślałem, że RCS to zastępcze repozytorium do importowania globalnych plików szablonów. Nie sądziłem, że jest on używany do przechowywania konfiguracji. Co tu jest poprawne?

RCS to usługa projektowa służąca do tworzenia i edycji konfiguracji ER. RCS ma swoje własne repozytorium, które jest znane jako repozytorium globalne. To repozytorium jest używane do przechowywania konfiguracji, które są tworzone w RCS. Po zaprzestaniu używania LCS jako magazynu, repozytorium globalne będzie jedynym źródłem dla konfiguracji Microsoft. Musisz wykonać jednorazową akcję, aby zaimportować wszystkie wymagane konfiguracje z LCS do RCS, a następnie opublikować je z RCS do Globalnego repozytorium.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Bez LCS, jaki jest sugerowany sposób przechowywania konfiguracji tak, aby konfiguracje „testowe” i „produkcyjne” mogły być łatwo zarządzane i przenoszone?

System RCS używa koncepcji *połączonej aplikacji*. Połączona aplikacja tworzy połączenie między RCS i dowolnym wystąpieniem aplikacji Finance and Operations. Ponieważ za pomocą usługi RCS można edytować konfiguracje, połączona aplikacja może służyć do wypychania konfiguracji bezpośrednio od konstruktora do środowisk aplikacji Finance and Operations. Dzięki temu można szybko zmieniać i testować konfiguracje, a nie korzystać z magazynu na poziomie projektu usługi LCS.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>Czy są jakieś przykłady, które pokazują konfigurację i zarządzanie?

Nie ma żadnych przykładów, ale możesz wykonać kroki opisane wcześniej w tym temacie, aby migrować konfiguracje do repozytorium globalnego RCS.
