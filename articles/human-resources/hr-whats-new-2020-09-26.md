---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 26 września 2020 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 26 września 2020 roku.
author: jcart1106
manager: tfehr
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d27104a08cdc899f12942d80e693f3495d90a6ec
ms.sourcegitcommit: 1329b3b98854422c4c3773ede44a5cefa7d07085
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2020
ms.locfileid: "4040083"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 26 września 2020 r.

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2020 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.3589-hf.3.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje:

- **Aktualizacja platformy 10.0.13 jest teraz dostępna** : Aby uzyskać więcej informacji dotyczących tej aktualizacji, zajrzyj do [aktualizacji platformy dotyczących wersji 10.0.13 aplikacji Finance and Operations (październik 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13).

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Wystawienie | opis |
| --- | --- | --- |
| 469495 | Aktualizowanie domyślnej siatki wymiarów finansowych i okna dialogowego | Siatka i okno dialogowe wymiarów finansowych są aktualizowane w Human Resources. |
| 474887 | Element pracy żądania opuszczenia powoduje otwarcie nieprawidłowego łącza w ręcznej decyzji | Gdy Konfiguracja przepływu pracy zawiera ręczną decyzję, przejście do żądania urlopu z **Elementy pracy przypisane do mnie** powoduje otwarcie niewłaściwego łącza, wyświetlenie pustego formularza lub żądania opuszczenia dla bieżącego użytkownika, a nie do pola przypisanego do ręcznej decyzji. |
| 474962 | Parametry urlopu i nieobecności mają pola z niejednoznacznymi etykietami | Etykiety encji parametrów urlopu i nieobecności zostały zaktualizowane, aby były bardziej przejrzyste. |
| 481401 | Przetwarzanie naliczania jest zawieszane, gdy podstawa naliczania jest późniejsza niż data początkowa naliczania i na koniec miesiąca | Przetwarzanie naliczeń zostało zaktualizowane w taki sposób, aby nie miało opóźnienia, jeśli podstawa daty naliczenia jest późniejsza niż data początkowa naliczania i na koniec miesiąca. |
| 447167 | Listy rekordów wygasania zawierają nieaktywnych pracowników | Karta **Rekordy wygasania** w module **Zarządzanie personelem** obejmuje nieaktywnych pracowników. W tej chwili obejmuje tylko aktywnych pracowników. |
| 486840 | Niewłaściwe opuszczenie wniosku urlopowego zostanie otwarte z **Elementy pracy przypisane do mnie** | Wybranie urlopu z prośbą urlopową z **Elementy pracy przypisane do mnie** nie powoduje już otwarcia ostatniego urlopu nieobecności przypisanego bieżącemu użytkownikowi. |
| 506868 | Common Data Service Nie ustawiono pola **Tytuł** dla jednostki **Stanowiska zadania** | Pole **Tytuł** w jednostkach **Zadania** i **Stanowisko zadania** jest wyświetlane jako nieokreślone. Wyświetlone zostanie pole **Tytuł**. |
| 430359 | Nie można uzyskać dostępu do zadań listy czynności do odłączania z przypisanymi rolami menedżera i pracownika | Pracownicy z przyszłą datą zakończenia zatrudnienia nie mogą uzyskać dostępu do swoich zadań kontrolnych, jeśli mają tylko rolę pracownika lub menedżera. Obecnie użytkownicy mający tylko rolę pracownika lub menedżera mogą uzyskiwać dostęp do zadań odłączania z przyszłą datą zakończenia zatrudnienia. |
| 458102 | Nowy pracownik nie jest wyświetlany w jednostce **Informacje o liście płac pracowników** podczas jej tworzenia | W jednostce informacji o liście płac pracownika znajdują się nowi pracownicy bez konieczności otwierania informacji o liście płac dla pracownika przed wyeksportowaniem jednostki. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aplikacja Human Resources w Microsoft Teams | [Urlop pracownika etatowego i nieobecność pracowników w Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md) |
| Rozszerzone żądania i zatwierdzenia przepływu pracy | [Usprawnienia dotyczące przepływu pracy zarządzania organizacją i kadrami](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>Wkrótce

Planowana jest następująca Nowa funkcja do przyszłego wydania:

- [Łącza niestandardowe w samoobsłudze menedżera](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2019 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Co nowego lub zmienione w Human Resources](hr-admin-whats-new.md)
[Przegląd Dynamics 365 Human Resources 2020 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[Zarządzanie procesem](hr-admin-setup-update-process.md)
[Zarządzanie funkcjami](hr-admin-manage-features.md)
