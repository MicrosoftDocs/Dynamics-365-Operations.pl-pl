---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 22 października 2020 r.
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 22 października 2020 roku.
author: jcart1106
ms.date: 10/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b183ea08a2decc2696ca3bc3997b5cf7f04652d4
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068070"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 22 października 2020 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



W tym artykule opisano nowe, zmienione lub przyszłe funkcje dostępne w aplikacji Dynamics 365 Human Resources. Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2020 wydanie 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.3680.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aktualizacja Platform Update 10.0.14(38) | -- | [Aktualizacje platformy dla wersji 10.0.14 aplikacji finansowych i operacyjnych (listopad 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14.md) |
| Usprawnienia dotyczące zadań zarządzania organizacją i kadrami | [Usprawnienia dotyczące przepływu pracy zarządzania organizacją i kadrami](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Możemy zaktualizować ten artykuł w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego artykułu.

| Numer problemu| Problem  | Opis|
| --- | --- | --- |
| 437922 | Importowanie godzin FMLA przy użyciu jednostki DMF powoduje błąd tylko do odczytu. | Użycie jednostki godziny FMLA do importowania godzin skojarzonych z sprawą FMLA nie powiodło się. Dodałeś logikę, aby upewnić się, że importowane godziny nie przekraczają godzin pozostałych dla sprawy. |
| 512019 | Nieprawidłowa kwota **ostatniej przeniesionej na następny okres**. | Na stronie **Czas wolny** zmień wartość **Na dzień** na pierwszy dzień następnego okresu obrachunkowego, na którym wyświetlona jest nieprawidłowa ilość **ostatniego przeniesienia na następny okres** dla typu **Urlopu rocznego**. Teraz wyświetlana jest poprawna kwota. |
| 458639 | Jednostka **Kontaktów pracownika** nie obsługuje trybu śledzenia zmian. | Zaktualizowano jednostkę **Kontakty pracownika**, dzięki czemu można z niej skorzystać w ramach wykonywania własnych scenariuszy bazy danych (BYOD).|
| 505347 | Menedżerowie szkoleń mogą przesłać żądanie opuszczenia dla pracownika, gdy włączono funkcję usprawnionego pracownika. | Role inne niż asystent ds. zarządzania kadrami nie mogą przesyłać żądań time0off dla pracowników. |
| 513490 | Rejestrowanie zarządzania korzyściami: Dodaj rejestrowanie dla planów bez opcji zapotrzebowania. | Włączono rejestrowanie wyników dla **Planu bez opcji dotyczących zapotrzebowania**. Teraz są wyświetlane w tabeli **Wyników procesu** i są poprawnie sortowane, aby były wyświetlane u góry. |
| 517021 | Nie można wybrać wielu planów z tym samym kodem **Typ planu**, jeśli **Typ planu** ma jedną rejestrację na typ. | Zmieniono ograniczenia wyboru planów, w których dozwolona jest tylko jedna rejestracja. Ograniczenia są teraz na poziomie **Kodu typu planu** zamiast **Typu planu**. Ta zmiana umożliwia tworzenie na przykład planów, takich jak HSA i FSA, które są tymi samymi typem, ale można również nadać im oddzielny **Kod typu planu**. W ten sposób można wybrać obie opcje dla tego samego okresu rejestracji. |
| 444791 | Nie można wyświetlić wynagrodzenia w module sklep pracowniczy, jeśli włączony jest **Ograniczony dostęp** do systemu wynagrodzeń. | W karcie **Wynagrodzenie** pracownika etatowego bieżąca kwota i procent podwyżki są wyświetlane po zarejestrowaniu pracownika w planie z włączonym **Ograniczeniem dostępu** i przypisanym do konkretnych ról. Ten problem został rozwiązany, więc pracownik i Menedżer mogą zawsze wyświetlać szczegóły dotyczące wynagrodzenia dla siebie i ich bezpośrednich podwładnych. |
| 457542 | Zaktualizowanie szczegółów kursu po zamknięciu kursu nie powoduje zaktualizowania informacji o tym samym pracowniku, który przeszedł kurs. | Informacje o pracowniku są teraz poprawnie aktualizowane po zamknięciu i ponownym otwarciu kursu. |
| 515342 | Nie można wstawić danych do **CDSLeaveRequestDetailEntity**. Firma nie została znaleziona lub nie istnieje. | Teraz można użyć **CDSLeaveRequestDetailEntity** do wstawienia danych. |
| 514743 | Błąd w formularzu **Parametrów poczty e-mail** podczas korzystania z programu Microsoft Exchange. | Komunikat „nie można załadować plików lub zestawu...” wyświetlany na stronie **Parametry poczty e-mail**, gdy dostawca poczty e-mail ustawił program **Exchange**. Ta poprawka umożliwia również ładowanie i zapisywanie strony **Parametrów poczty e-mail** zgodnie z oczekiwaniami. |


## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aplikacja Human Resources w Microsoft Teams | [Urlop pracownika etatowego i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplikacja Human Resources w Teams](./hr-admin-teams-leave-app.md)<br>[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md) |
| Rozszerzone żądania i zatwierdzenia przepływu pracy | [Usprawnienia dotyczące przepływu pracy zarządzania organizacją i kadrami](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Jednostki wirtualne w Dataverse dla Human Resources | [Rozwiń dane podstawowe Dynamics 365 Human Resources w Dataverse](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Konfigurowanie jednostek wirtualnych usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |
| Integracja z usługą LinkedIn Talent Hub | [Integracja z usługą LinkedIn Talent Hub](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integracja z usługą LinkedIn Talent Hub](./hr-admin-integration-linkedin.md) |
| Łącza niestandardowe w samoobsłudze menedżera | [Łącza niestandardowe w samoobsłudze menedżera](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Łącza niestandardowe w samoobsłudze menedżera](./hr-employee-manager-self-service-custom-links.md) |

## <a name="coming-soon"></a>Wkrótce

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2020 wydanie 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2020, wydanie 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
