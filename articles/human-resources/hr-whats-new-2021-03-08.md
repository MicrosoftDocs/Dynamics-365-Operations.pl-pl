---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 8 marca 2021 r.
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 8 marca 2021 roku.
author: marcelbf
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9280e85f9701573717c4115b4d752ed11be4862e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868076"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 08 marca 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano nowe, zmienione lub przyszłe funkcje dostępne w aplikacji Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4017.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Międzyfirmowe wyświetlanie urlopu dla menedżerów | [Międzyfirmowe wyświetlanie urlopu pracownika etatowego dla menedżerów](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurowanie parametrów urlopu i nieobecności](./hr-leave-and-absence-parameters.md) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Możemy zaktualizować ten artykuł w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego artykułu.

| Numer problemu | Problem |  Opis |
| --- | --- | --- |
| 486611 | Jeśli opcja **Wyłącz urlop we wszystkich kalendarzach** jest włączona, nieobecności są pokazywane w kalendarzu urlopów | Jeśli opcja **Wyłącz urlop we wszystkich kalendarzach** jest włączona, informacje o urlopie nie są już wyświetlane, gdy jest włączona funkcja usprawnień kalendarza urlopów i nieobecności.|
| 508972 | Brak weryfikacji rejestracji dla jednostki Transakcja bankowa urlopu i nieobecności | W przypadku korzystania z jednostki Transakcja bankowa urlopu i nieobecności nie można już importować pracowników, którzy nie są zarejestrowani w planie. |
| 554854 | Aktualizacja kalendarza w błędach podmiotu zatrudnienia, jeśli domyślny podmiot prawny w opcjach użytkownika jest inny | Użycie jednostki Zatrudnienie do aktualizacji kalendarza dla pracownika nie powoduje już błędu, jeśli domyślna osoba prawna w Opcjach użytkownika jest inna. |
| 558347 | Podczas ładowania strony początkowej pojawia się komunikat „Nie można utworzyć rekordu w konfiguracjach formularza (FormRunConfiguration)”. | Personalizacje powodują, że podczas ładowania strony początkowej pojawia się błąd „Nie można utworzyć rekordu w konfiguracjach formularza (FormRunConfiguration)”. |
| 557327 | Obszar roboczy zarządzania korzyściami: nad siatką pojawia się luka. | Naprawiono problem z wrażeniem użytkownika polegający na pojawianiu się niezamierzonej przerwy na granicach siatki tabeli w obszarze roboczym Korzyści. |
| 557334 | Obszar roboczy Zarządzanie świadczeniami: pole wyboru **Okres** powinno być wyświetlane tylko na karcie **Podsumowanie** | Lista rozwijana **Wybór okresu** świadczeń jest teraz wyświetlana tylko wtedy, gdy karta **Podsumowanie** jest aktywna w obszarze roboczym Korzyści, a nie w sekcjach **Wyniki procesu** i **Łącza**. |
| 557336 | Obszar roboczy Zarządzanie świadczeniami: tekst **Otwarta rejestracja z wyrejestrowanymi planami** jest obcięty w widoku kafelków | Zmieniono tekst w widoku kafelków na **Wyewidencjonowane plany... otwieranie rejestracji** w celu uniknięcia pominięcia niezbędnego kontekstu. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Ograniczenie pracownikom możliwości edytowania biznesowych danych kontaktowych | [Ograniczenie pracownikom możliwości edytowania biznesowych danych kontaktowych](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Ogranicz edytowanie informacji osobistych](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Umiejętności wprowadzone przez menedżera dla swoich pracowników mogą być automatycznie zatwierdzane w przepływie pracy | Wkrótce. |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]