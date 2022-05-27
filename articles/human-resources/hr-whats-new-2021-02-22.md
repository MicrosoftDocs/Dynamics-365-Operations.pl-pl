---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 22 lutego 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 22 lutego 2021 roku.
author: marcelbf
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c0f854908f4c4bb76604665701c97724351b0120
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686891"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 22 lutego 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.3988.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aplikacja Dynamics 365 Human Resources dla Microsoft Teams | [Urlop pracownika etatowego i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplikacja Human Resources w Teams](./hr-admin-teams-leave-app.md)<br>[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Wystawienie |  opis |
| --- | --- | --- |
| 529994 | Modyfikowanie pola **Znane jako** w formularzu **Pracownik** nie powoduje uruchomienia aktualizacji Dataverse | Naprawiono problem polegający na tym, że Dataverse nie aktualizuje się po zaktualizowaniu pola **Znany jako** w formularzu **Pracownik**. |
| 532651 | Raport PBI dotyczący analizy wynagrodzeń nie korzysta z przeliczania walut przy obliczaniu wskaźników dla całej firmy | Naprawiono problem polegający na tym, że raport PBI analizy wynagrodzeń nieprawidłowo przeliczał waluty. |
| 552226 | Przetwarzanie zdarzeń życiowych wielokrotnie zamyka i otwiera plany dla pojedynczego zdarzenia życiowego  | Rozwiązano problem polegający na tym, że pracownik jest w wielu podmiotach prawnych i występuje zdarzenie życiowe, rekord zdarzenia życiowego generowany jest dla każdej firmy, w której znajduje się pracownik. Podczas przetwarzania zdarzeń życiowych należy wybrać podmiot prawny do przetwarzania. Jednak logika przetwarzania nie ogranicza się do tej firmy. Zamiast tego przetwarza dla wszystkich podmiotów prawnych oraz zamyka i ponownie otwiera plany w wybranej firmie. To działanie jest zdarzeniem życiowym, które ma być przetwarzane wiele razy w tym samym podmiocie prawnym, co skutkuje wielokrotnym zamknięciem / ponownym otwarciem każdego planu, na który miało wpływ zdarzenie życiowe. |
| 518064 | Wybrano tylko jedną osobę zależną od kwalifikujących się planów, gdy więcej niż jeden jest oznaczony jako domyślny wyznaczony | Naprawiono problem polegający na tym, że w kwalifikujących się planach nie wybiera się automatycznie wielu domyślnych wyznaczonych osób. Możesz teraz wyznaczyć głównego beneficjenta do osobistego kontaktu. Główny beneficjent jest wymieniony jako 100% w kwalifikujących się planach, gdy jest wielu beneficjentów. |
| 552365 | Zadania eksportu własnej bazy danych (BYOD) kończą się niepowodzeniem po uaktualnieniu do aktualizacji platformy 40 | Naprawiono problem polegający na tym, że eksport BYOD kończy się niepowodzeniem po zastosowaniu aktualizacji platformy 40 do środowiska. |
| 547123 | Ograniczenie liczby zadań, których dotyczy kwerenda, na liście zadań do wykonania na pulpicie nawigacyjnym | Liczba zadań wyświetlanych na liście zadań jest teraz ograniczona do 15, aby rozwiązać problem z wydajnością spowodowany nadmierną liczbą zadań próbujących załadować. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Międzyfirmowe wyświetlanie urlopu dla menedżerów | [Międzyfirmowe wyświetlanie urlopu pracownika etatowego dla menedżerów](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurowanie parametrów urlopu i nieobecności](./hr-leave-and-absence-parameters.md) |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Ograniczenie pracownikom możliwości edytowania biznesowych danych kontaktowych | [Ograniczenie pracownikom możliwości edytowania biznesowych danych kontaktowych](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Ogranicz edytowanie informacji osobistych](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Umiejętności wprowadzone przez menedżera dla swoich pracowników mogą być automatycznie zatwierdzane w przepływie pracy | Wkrótce. |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Aktualizacje terminologii dla Microsoft Dataverse

Od 2020 listopada Common Data Service zmieniło nazwę na [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Więcej informacji można znaleźć w [oficjalnym oświadczeniu](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) na stronie bloga Power Apps. Wraz ze zmianą tej nazwy niektóre terminologii Dataverse zostały zaktualizowane. Na przykład *jednostka* to teraz *tabela*, a *pole* to teraz *kolumna*. Aby uzyskać więcej informacji, zobacz [Aktualizacje terminologii](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

W tej wersji terminologia związana z integracją Dynamics 365 Human Resources z Dataverse została zaktualizowana w całej aplikacji, aby odzwierciedlić te zmiany. Na przykład formularz **integracji Common Data Service** jest teraz **integracją Microsoft Dataverse**.

Aby dowiedzieć się więcej o integracji Dynamics 365 Human Resources z programem Microsoft Dataverse, zobacz temat [Konfigurowanie integracji Microsoft Dataverse](./hr-admin-integration-common-data-service.md) i [Konfigurowanie tabel wirtualnych Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="updates-to-service-deployment"></a>Aktualizacje wdrożenia usługi

Począwszy od wydania z 22 lutego 2021 roku, dopasowywliśmy wdrożenie aktualizacji usług regionalnych. Zmiany będą obejmować rotację kolejności, w jakiej regiony globalne otrzymują aktualizacje usługi HR oraz modyfikacje czasu oczekiwania między etapami aktualizacji. Dzięki tym zmianom jesteśmy bardziej zgodni z praktykami bezpiecznego wdrażania (SDP) w celu poprawy stabilności usług, jakości i możliwości obsługi.

Będziemy nadal postępować zgodnie z dwutygodniowym cyklem wdrażania. Pacjenci mogą spodziewali się, że sprzyjają, że są zwykle stosowane w ich środowiskach zasobów ludzkich w trakcie cyklu dwutygodniowego niż w doświadczeniach.

Aby uzyskać więcej informacji na temat usługi procesu aktualizacji, należy zapoznać się z tematem [Aktualizacja procesu](./hr-admin-setup-update-process.md).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]