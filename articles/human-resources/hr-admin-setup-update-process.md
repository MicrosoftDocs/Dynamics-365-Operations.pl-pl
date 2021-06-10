---
title: Aktualizowanie procesu
description: Microsoft Dynamics 365 Human Resources to rozwiązanie typu oprogramowanie jako usługa (SaaS), które zapewnia ciągłe aktualizacje dla zmian w aplikacji i platformie.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2466c53885340991aeeb0a07af83517473b332b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053642"
---
# <a name="update-process"></a>Aktualizowanie procesu

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Microsoft Dynamics 365 Human Resources to rozwiązanie typu oprogramowanie jako usługa (SaaS), które zapewnia ciągłe aktualizacje usług bez interwencji użytkownika. Te aktualizacje zawierają modyfikacje aplikacji i platformy, które często wprowadzają krytyczne udoskonalenia usługi, w tym aktualizacje wymagane przepisami prawa.

## <a name="update-policy"></a>Zasady aktualizacji

Aktualizacje są publikowane regularnie dla wszystkich środowisk. Program Human Resources jest wspierany zgodnie z [zasadami cyklu życia pomocy technicznej Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), które określają spójny i przewidywalny harmonogram dostępności wsparcia technicznego.

## <a name="release-cadence"></a>Częstotliwość wydań 

Aktualizacje modułu Human Resources są stosowane do wszystkich środowisk automatycznie. Dla modułu Human Resources są publikowane dwa typy wydań:

- **Aktualizacje usług**: Aktualizacje pojawiają się co dwa tygodnie, zawierają poprawki błędów i nowe funkcje. Aktualizacje usług obejmują także odpowiednie aktualizacje platformy, kiedy są one publikowane. Aby zapoznać się z orientacyjnym harmonogramem publikowania aktualizacji platformy, zobacz [Tabela 3: Wydania platformy](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases). Aktualizacje co dwa tygodnie zawierają wdrożenia globalne w różnych regionach. Aby uzyskać więcej informacji o aktualizacjach co dwa tygodnie, zobacz [Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources](hr-admin-whats-new.md).

    Wszystkie obsługiwane centra danych są aktualizowane co dwa tygodnie, o ile nie zaznaczono inaczej. Stany Zjednoczone, Australia, Europa, Wielka Brytania, Azja i Kanada są objęte aktualizacjami co dwa tygodnie. 

- **Aktualizacje rozwiązania Dataverse**: te aktualizacje odbywają się w przybliżeniu co sześć tygodni, jeśli jest to konieczne. Obejmują nowe jednostki i zmiany istniejących jednostek w usłudze Dataverse. Te aktualizacje są publikowane w tych samych regionach, jak aktualizacje co dwa tygodnie, a ich zreplikowanie do wszystkich centrów danych może potrwać do sześciu tygodni. Aktualizacje rozwiązania mogą być zbieżne z aktualizacjami usług co dwa tygodnie, ale nie muszą.

> [!NOTE]
> Aktualizacje rozwiązania są dostępne we wszystkich centrach danych po opublikowaniu. Jeśli nie chcesz czekać na automatyczne zreplikowanie aktualizacji, możesz ręcznie zastosować te aktualizacje w dowolnym środowisku w dowolnym centrum danych.

W razie potrzeby dla modułu Human Resources są również dostarczane następujące typy rozwiązań błędów:

- **Poprawka**: poprawki błędów, które mogą towarzyszyć wydaniom aktualizacji usług co dwa tygodnie albo być publikowane niezależnie

- **Poprawka awaryjna**: Proaktywne i reaktywne poprawki, które co do zasady są autonomiczne, mogą zawierać modyfikacje konfiguracji lub kodu źródłowego w celu rozwiązania istniejących problemów w ośrodku oraz mogą występować poza aktualizacjami wersji usług co dwa tygodnie

Wersje są przeglądane, testowane i weryfikowane w środowisku wewnętrznym. Zaakceptowane kompilacje są wdrażane w środowisku produkcyjnym.

## <a name="release-cadence-exceptions-in-2021"></a>Częstotliwośc wydawania wyjątków w wersji 2021

Aby uwzględnić dni wolne, harmonogram wydawanych aktualizacji dla listopada i grudnia 2021 roku jest następujący:

- Wersja listopadowa: 1 listopada – 14 listopada
- Wersja grudniowa: 29 listopada – 12 grudnia
 
Dwutygodniowe odstępy pomiędzy wersjami zaczną zwnou obowiązywać od 10 stycznia 2022 roku.

## <a name="communications"></a>Komunikacja

W lokalizacjach wymienionych poniżej można dowiedzieć się, co szykujemy w module Human Resources i jakie aktualizacje dotychczas opublikowano:

- [Plan rozwoju rozwiązania Dynamics 365 Human Resources](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Plany wydań Dynamics 365](/dynamics365/release-plans/)

- [Nowości i zmiany w Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Wyszukiwanie problemów w usługach Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (tylko błędy platformy)

- [Blog o rozwiązaniu Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Społeczność użytkowników rozwiązania Human Resources w serwisie Yammer](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Funkcje w wersji zapoznawczej w środowisku piaskownicy

Funkcje w wersji zapoznawczej można weryfikować w środowisku piaskownicy przed ich włączeniem w środowisku produkcyjnym. Aby uzyskać więcej informacji o włączaniu funkcji, zobacz [Zarządzanie funkcjami — omówienie](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Wszystkie nowe funkcje pozostają w podglądzie przez co najmniej 30 dni, a zazwyczaj 30-60 dni. Najważniejsze funkcje są zazwyczaj dostępne w październiku i kwietniu każdego roku po okresie podglądu. Po wyświetleniu nowych możliwości w obszarze roboczym zarządzanie funkcjami można je włączyć. Niektóre funkcje mogą być domyślnie włączone.

Czasami funkcja jest domyślnie włączona i nie można jej wyłączyć (na przykład w obszarze roboczym zarządzanie funkcjami).

Gdy funkcja jest ogólnie dostępna, może być włączana lub wyłączana w środowiskach produkcyjnych. Przestrzeń robocza Zarządzanie funkcjami wskazuje, kiedy funkcja podglądu stanie się obowiązkowa. Ta data zazwyczaj jest równa 1 października lub 1 kwietnia w celu dostosowania ich do półrocznych planów zwolnień. Nie można wyłączać obowiązkowych funkcji. Dopóki ta funkcja nie stanie się obowiązkowa, można ją włączać i wyłączać we wszystkich środowiskach.

Zdecydowanie zalecamy sprawdzenie działania funkcji w wersji zapoznawczej w środowisku piaskownicy lub w próbnym. Najlepiej utworzyć kopię bieżącego środowiska produkcyjnego lub bazy danych w środowisku piaskownicy, co pozwoli kompleksowo sprawdzić działanie nowych funkcji z danymi firmy.

Aby uzyskać więcej informacji na temat inicjowania obsługi środowiska piaskownicy, zobacz [Inicjowanie obsługi administracyjnej projektu programu Human Resources](hr-admin-setup-provision.md). Aby usunąć środowisko testowe, zobacz [Usuwanie wystąpienia](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Zgłaszanie usterek

Podczas testowania funkcji w wersji zapoznawczej lub sprawdzania nowych możliwości oprogramowania można znaleźć elementy, które nie działają zgodnie z oczekiwaniami. Wszelkie usterki prosimy zgłaszać do [działu pomocy technicznej systemu Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Informacje dodatkowe

[Plany wydań rozwiązań Dynamics 365 i Power Platform](/dynamics365/release-plans)</br>
[Nowości i zmiany w module Dynamics 365 Human Resources](hr-admin-whats-new.md)</br>
[Zasady dotyczące cyklu życia oprogramowania](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]