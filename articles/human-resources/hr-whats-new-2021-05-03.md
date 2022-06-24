---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 3 maja 2021 r.
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 3 maja 2021 roku.
author: marcelbf
ms.date: 05/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 01ebd15e09e181a7ea0ec5bf70c8df731d2169c0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902868"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 3 maja 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano nowe, zmienione lub przyszłe funkcje dostępne w aplikacji Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4140.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Dodaj pasek informacyjny podczas tworzenia zdarzeń życia. | - | Podczas tworzenia zdarzenia życia na pasku informacji jest wyświetlany komunikat wskazujący typ utworzonego zdarzenia życia.

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Możemy zaktualizować ten artykuł w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego artykułu.

| Numer problemu | Problem |  Opis |
| --- | --- | --- |
| 559312 |  Poziom nie jest wyświetlany podczas tworzenia stałego planu wynagrodzeń dla pracownika. |  Gdy istnieje niezgodność stref czasowych między strefą czasową użytkownika a strefą czasową firmy, nie można odczytać poziomu wynagrodzeń dla zadania. Kwerenda została zaktualizowana do pobrania na podstawie czasu UTC. |
| 573676  | Nie można dodać nowego okresu w formularzu **Plan świadczeń**. | Zaktualizowany formularz w taki sposób, aby przycisk **Nowy** był włączony w obszarze szybkiego formularza **Okres** w **planach świadczeń**. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Rozszerzenia środowiska przepływu pracy urlopów i nieobecności | [Rozszerzenia środowiska przepływu pracy urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2147528) | [Złóż wniosek o czas wolny](hr-employee-self-service-request-time-off.md)|
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md)|
| Przeprowadzanie inspekcji transakcji naliczania urlopów | - | [Przeprowadzanie inspekcji transakcji naliczania urlopów](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Aktualizacja Platform Update 10.0.18 (42) | Aktualizacja platformy z 10.0.18 ma się rozpocząć w następnym wydaniu serwisowym w dniu 17 maja 2021. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.18 aplikacji Finanse i Działania (maj 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Obsługa pól niestandardowych w regułach uprawnień zarządzania świadczeniami  | [Obsługa pól niestandardowych na potrzeby przetwarzania uprawnień](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
