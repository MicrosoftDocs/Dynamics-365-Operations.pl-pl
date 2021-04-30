---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 5 kwietnia 2021
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 5 kwietnia 2021 roku.
author: marcelbf
ms.date: 04/05/2021
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
ms.author: marcelbf
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ffb1d8966cb7e41a7032c6d4449b9e332c0e4703
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890608"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 5 kwietnia 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4074.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Ograniczenie pracownikom możliwości edytowania biznesowych danych kontaktowych | [Ograniczenie pracownikom możliwości edytowania biznesowych danych kontaktowych](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Ograniczanie edycji informacji osobistych](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Wystawienie |  opis |
| --- | --- | --- |
| 550852 | Przycisk **Zatwierdzenie** nie jest sprawdzany poprawność obowiązkowych pól ustawionych w formularzu **Przegląd**. | Jeśli w formularzu **Przegląd** ustawisz pole jako wymagane i opublikujesz zmiany roli Menedżer, formularz nie będzie sprawdzany w sposób oczekiwany. |
| 559564 | Historyczne akcje dotyczące pracowników dla zmiany stałej rekompensaty powodują błąd dla zakończonych użytkowników. | Czynność pracownika polegająca na odejściu z odszkodowania powoduje błąd. Po zwolnieniu pracownika akcja awansu przed zwolnieniem daje błąd. |
| 560074 | Lista rozwijana kategorii zatrudnienia nie jest filtrowana według **Typu pracownika** i pokazuje kategorie dla pracowników i podwykonawców. | W formularzu **Pracownik** w menu rozwijanym **Kategoria zatrudnienia** powinny być wyświetlane kategorie pracownika lub zleceniobiorcy, w zależności od typu pracownika. |
| 567388 | Niektóre informacje dla nowo utworzonych pracowników nie są natychmiast synchronizowane z tabelą **cdm_worker** w Dataverse. | Podczas tworzenia nowego rekordu pracownika nowy rekord zostanie zsynchronizowany z tabelą **cdm_worker** w Dataverse, ale nie wszystkie właściwości zostaną uwzględnione w rekordzie Dataverse. |
| 563837 | Funkcje, które nie są dostępne na ekranie Human Resources. | Kilka funkcji, które nie mają zastosowania do Human Resources, jest wyświetlanych w zarządzaniu funkcjami. Te funkcje zostaną teraz usunięte z listy funkcji dostępnych do włączenia w Human Resources. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Umiejętności wprowadzone przez menedżera dla swoich pracowników mogą być automatycznie zatwierdzane w przepływie pracy | Wkrótce. |
| Aktualizacja Platform Update 10.0.17 (41) | Aktualizacja platformy z 10.0.17 ma się rozpocząć w następnym wydaniu 19 kwietnia 2021. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.17 aplikacji Finance and Operations (kwiecień 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md). |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]