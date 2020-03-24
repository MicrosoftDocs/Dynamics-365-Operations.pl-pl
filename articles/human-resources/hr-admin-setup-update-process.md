---
title: Aktualizowanie procesu
description: Microsoft Dynamics 365 Human Resources to rozwiązanie typu oprogramowanie jako usługa (SaaS), które zapewnia ciągłe aktualizacje dla zmian w aplikacji i platformie.
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
ms.openlocfilehash: 267682f4497bacf70f93840a948d0e525dfa4aa1
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092208"
---
# <a name="update-process"></a>Aktualizowanie procesu

Microsoft Dynamics 365 Human Resources to rozwiązanie typu oprogramowanie jako usługa (SaaS), które zapewnia ciągłe aktualizacje usług bez interwencji użytkownika. Te aktualizacje zawierają modyfikacje aplikacji i platformy, które często wprowadzają krytyczne udoskonalenia usługi, w tym aktualizacje wymagane przepisami prawa.

## <a name="update-policy"></a>Zasady aktualizacji

Aktualizacje są publikowane regularnie dla wszystkich środowisk. Program Human Resources jest wspierany zgodnie z [zasadami cyklu życia pomocy technicznej Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), które określają spójny i przewidywalny harmonogram dostępności wsparcia technicznego.

## <a name="release-cadence"></a>Częstotliwość wydań

Aktualizacje modułu Human Resources są stosowane do wszystkich środowisk automatycznie. Dla modułu Human Resources są publikowane dwa typy wydań:

- **Aktualizacje usług**: cotygodniowe aktualizacje obejmujące poprawki błędów i nowe funkcje. Aktualizacje usług obejmują także odpowiednie aktualizacje platformy, kiedy są one publikowane. Aby zapoznać się z orientacyjnym harmonogramem publikowania aktualizacji platformy, zobacz [Tabela 3: Wydania platformy](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases). Aktualizacje cotygodniowe zazwyczaj są publikowane w środę. Aby uzyskać więcej informacji o aktualizacjach cotygodniowych, zobacz [Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365/talent/whats-new).

    Wszystkie obsługiwane centra danych są aktualizowane co tydzień, o ile nie zaznaczono inaczej. Aktualizacje cotygodniowe zazwyczaj rozpoczynają się w środę i trwają do niedzieli. Stany Zjednoczone, Australia, Europa, Wielka Brytania, Azja i Kanada są objęte aktualizacjami cotygodniowymi. 

- **Aktualizacje rozwiązania Common Data Service**: te aktualizacje odbywają się w przybliżeniu co sześć tygodni, jeśli jest to konieczne. Obejmują nowe jednostki i zmiany istniejących jednostek w usłudze Common Data Service. Te aktualizacje są publikowane w tych samych regionach, jak aktualizacje cotygodniowe, a ich zreplikowanie do wszystkich centrów danych może potrwać do sześciu tygodni. Aktualizacje rozwiązania mogą być zbieżne z cotygodniowymi aktualizacjami usług, ale nie muszą.

W poniższej tabeli przedstawiono przykładowy harmonogram:

| Tydzień | Typ aktualizacji |
| --- | --- |
| 1 | Aktualizacja usługi (wszystkie regiony) |
| 2 | Aktualizacja usługi (wszystkie regiony) + Aktualizacja rozwiązania (regiony na tydzień 1) |
| 3 | Aktualizacja usługi (wszystkie regiony) + Aktualizacja rozwiązania (regiony na tydzień 2) |
| 4 | Aktualizacja usługi (wszystkie regiony) + Aktualizacja rozwiązania (regiony na tydzień 3) |
| 5 | Aktualizacja usługi (wszystkie regiony) + Aktualizacja rozwiązania (regiony na tydzień 4) |
| 6 | Aktualizacja usługi (wszystkie regiony) + Aktualizacja rozwiązania (regiony na tydzień 5) |
| 7 | Aktualizacja usługi (wszystkie regiony) + Aktualizacja rozwiązania (regiony na tydzień 6) |
| 8 | Aktualizacja usługi (wszystkie regiony) |

> [!NOTE]
> Aktualizacje rozwiązania są dostępne we wszystkich centrach danych po opublikowaniu. Jeśli nie chcesz czekać na automatyczne zreplikowanie aktualizacji, możesz ręcznie zastosować te aktualizacje w dowolnym środowisku w dowolnym centrum danych.

W razie potrzeby dla modułu Human Resources są również dostarczane następujące typy rozwiązań błędów:

- **Poprawka**: poprawki błędów, które mogą towarzyszyć cotygodniowym wydaniom aktualizacji usług albo być publikowane niezależnie

- **Poprawka awaryjna**: proaktywne i reaktywne poprawki, które co do zasady są autonomiczne, mogą zawierać modyfikacje konfiguracji lub kodu źródłowego w celu rozwiązania istniejących problemów w ośrodku oraz mogą występować poza cotygodniowymi aktualizacji wersji usług

Wersje są przeglądane, testowane i weryfikowane w środowisku wewnętrznym. Zaakceptowane kompilacje są wdrażane w środowisku produkcyjnym.

## <a name="exceptions-in-2019"></a>Wyjątki w roku 2019

Następujące daty są wyjątkami od zwykłego harmonogramu wydań:

| Data | Opis |
| --- | --- |
| Tydzień rozpoczynający się 25 listopada | Bez aktualizacji |
| Tydzień rozpoczynający się 16 grudnia | Tylko drobne aktualizacje |
| Tydzień rozpoczynający się 23 grudnia | Bez aktualizacji |
| Tydzień rozpoczynający się 30 grudnia | Bez aktualizacji |

## <a name="communications"></a>Komunikacja

W lokalizacjach wymienionych poniżej można dowiedzieć się, co szykujemy w module Human Resources i jakie aktualizacje dotychczas opublikowano:

- [Plan rozwoju rozwiązania Dynamics 365 Human Resources](https://dynamics.microsoft.com/roadmap/talent/)

- [Plany wydań Dynamics 365](https://docs.microsoft.com/dynamics365/release-plans/)

- [Nowości i zmiany w Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Wyszukiwanie problemów w usługach Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (tylko błędy platformy)

- [Blog o rozwiązaniu Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Społeczność użytkowników rozwiązania Human Resources w serwisie Yammer](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Funkcje w wersji zapoznawczej w środowisku piaskownicy

Funkcje w wersji zapoznawczej można weryfikować w środowisku piaskownicy przed ich włączeniem w środowisku produkcyjnym. Aby uzyskać więcej informacji o włączaniu funkcji, zobacz [Zarządzanie funkcjami — omówienie](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Wszystkie nowe funkcje pozostają w podglądzie przez co najmniej 30 dni, a zazwyczaj 30-60 dni. Najważniejsze funkcje są zazwyczaj dostępne w październiku i kwietniu każdego roku po okresie podglądu. Po wyświetleniu nowych możliwości w obszarze roboczym zarządzanie funkcjami można je włączyć. Niektóre funkcje mogą być domyślnie włączone.

Czasami funkcja jest domyślnie włączona i nie można jej wyłączyć (na przykład w obszarze roboczym zarządzanie funkcjami).

Gdy funkcja jest ogólnie dostępna, może być włączana lub wyłączana w środowiskach produkcyjnych. Przestrzeń robocza Zarządzanie funkcjami wskazuje, kiedy funkcja podglądu stanie się obowiązkowa. Ta data zazwyczaj jest równa 1 października lub 1 kwietnia w celu dostosowania ich do półrocznych planów zwolnień. Nie można wyłączać obowiązkowych funkcji. Dopóki ta funkcja nie stanie się obowiązkowa, można ją włączać i wyłączać we wszystkich środowiskach.

Zdecydowanie zalecamy sprawdzenie działania funkcji w wersji zapoznawczej w środowisku piaskownicy lub w próbnym. Najlepiej utworzyć kopię bieżącego środowiska produkcyjnego lub bazy danych w środowisku piaskownicy, co pozwoli kompleksowo sprawdzić działanie nowych funkcji z danymi firmy.

Aby uzyskać więcej informacji na temat inicjowania obsługi środowiska piaskownicy, zobacz [Inicjowanie obsługi administracyjnej projektu programu Human Resources](hr-admin-setup-provision.md). Aby usunąć środowisko testowe, zobacz [Usuwanie wystąpienia](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Zgłaszanie usterek

Podczas testowania funkcji w wersji zapoznawczej lub sprawdzania nowych możliwości oprogramowania można znaleźć elementy, które nie działają zgodnie z oczekiwaniami. Wszelkie usterki prosimy zgłaszać do [działu pomocy technicznej systemu Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Informacje dodatkowe

- [Plany wydań rozwiązań Dynamics 365 i Power Platform](https://docs.microsoft.com/dynamics365/release-plans)
- [Nowości i zmiany w module Dynamics 365 Human Resources](hr-admin-whats-new.md)
- [Zasady dotyczące cyklu życia oprogramowania](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)

