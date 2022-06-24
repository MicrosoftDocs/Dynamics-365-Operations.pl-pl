---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 6 września 2021 r.
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 6 września 2021 roku.
author: marcelbf
ms.date: 09/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 776498b32f8323b1a06f39b518cdc1ae534f9bcc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872160"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 6 września 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano nowe, zmienione lub przyszłe funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4443.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
|---|---|---|
| Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem | [Umożliwienie menedżerowi ds. nieobecności zarządzania urlopem](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | W tej wersji aktualizujemy widok obszaru roboczego menedżera nieobecności. Aby uzyskać więcej informacji, zobacz [konfiguracja ról menedżera urlopów](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Skonfiguruj wymagania dotyczące załącznika dla każdego typu urlopu | [Skonfiguruj wymagania dotyczące załącznika dla każdego typu urlopu](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [Konfigurowanie typów urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2168108) |
| Konfigurowanie jednostek urlopu według typu urlopu | [Konfigurowanie jednostek urlopu według typu urlopu](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [Konfigurowanie typów urlopów i nieobecności](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Microsoft może zaktualizować ten artykuł w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego artykułu.

| Numer problemu | Problem | Opis |
|---|---|---|
| 610128 | Błąd podczas publikowania danych w przypadku używania danych HcmDiscussionOverallCommentEntity | Gdy dane są publikowane ze skoroszytu programu Excel do jednostki HcmDiscussionOverralCommentEntity, występuje następujący błąd: „Nie można zlokalizować rekordu źródła danych typu HcmTopicOverrall”. |
| 589073 | Raport EEO-1 zawiera wartości „Nieokreślony” i wartość pustą pola **Płeć** jako wartość „Kobieta”. | Jeśli **Mężczyzna** nie jest określony w polu **Płeć**, raport EEO-1 generuje domyślną wartość **Kobieta**. |
| 589617 | Saldo czasu wolnego od karty, Salda Dostępne do zakupu i Dostępne do sprzedaży nie są wyświetlane, gdy role użytkowników są ograniczone do określonej osoby prawnej. | Jeśli użytkownik (rola pracownika) jest ograniczony do określonej firmy, salda nie są poprawnie wyświetlane na karcie **Salda czasu wolnego od pracy** oraz w polach **Dostępne do zakupu** i **Dostępne do sprzedaży**. |
| 604310 | Zakładka Menedżer nieobecności powinna być ukryta, gdy użytkownik nie ma przypisanej hierarchii nieobecności. | Dla danej firmy karta **Menedżer nieobecności** powinna być ukryta w portalu samoobsługowym, chyba że jest włączony parametr między firmami i co najmniej jedna hierarchia nieobecności jest skojarzona z użytkownikiem. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub wyłączania funkcji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
|---|---|---|
| Włączenie uproszczonej integracji listy płac (interfejsy API integracji listy płac) | [Włączenie uproszczonej integracji z dostawcami listy płac](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Interfejs API integracji listy płac](hr-admin-integration-payroll-api-introduction.md) |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Umożliwienie oznaczania pracowników jako gotowych do wypłaty | [Umożliwienie oznaczania pracowników jako gotowych do wypłaty](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Gotowe do wypłaty](/dynamics365/human-resources/hr-compensation-payroll) |
| Pola niestandardowe w aplikacji Eligibility |[Wsparcie pól niestandardowych w przetwarzaniu uprawnień](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Korzystanie z pól niestandardowych w przetwarzaniu uprawnień](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>Wkrótce

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funkcja | Szczegóły |
|---|---|
| Aktualizacja Platform Update 10.0.21 (45) | Publikacja aktualizacji platformy 10.0.21 ma się rozpocząć w następnym wydaniu serwisowym w dniu 4 października 2021. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.21 aplikacji finansowych i operacyjnych (październik 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
| Oświadczenie o świadczeniach | Oświadczenie o świadczeniach do przeglądania aktualnych wyborów świadczeń pracownika. Aby uzyskać więcej informacji, zobacz [sprawozdanie o świadczeniach](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) w dokumencie Grupy czynności wydania. |

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
