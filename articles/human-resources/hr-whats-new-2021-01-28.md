---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources w z 28 stycznia 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 28 stycznia 2021 roku.
author: marcelbf
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4fbf3034805146c3900b46f5ccce76e63b0805a4
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893084"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources w z 28 stycznia 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.3906.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Integrowanie kodów przyczyn świadczeń z obszarem roboczym **Zarządzanie pracownikami** | -- | [Ustaw kody przyczyn](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.


| Numer problemu | Wystawienie |  opis |
| --- | --- | --- |
| 539456 | W kalendarzu jest pokazywany typ urlopu, gdy jest włączony parametr **Pokaż tylko nieobecność bez szczegółów**. | Po włączeniu opcji **Pokaż tylko nieobecności bez szczegółów** data żądania zostanie wyświetlona po umieszczeniu kursora. |
| 528907 | Przyznanie dostępu do osoby prawnej związanej z rolą pracownika powoduje, że menedżerowie nie widzą salda urlopów dla pracowników w obszarze Samoobsługa pracowników w obszarze **Mój zespół**. |Ustawienie tej opcji umożliwia teraz menedżerom dalsze sprawdzanie salda urlopów. |
| 526280 | Błąd uprawnień w danych HcmWorkerEntity, HcmEmployeeEntity i HcmContractorEntity. | Użytkownicy pełniący rolę administratora niezwiązanego z systemem nie mogli wyeksportować wymienionych jednostek z powodu błędu uprawnień w polu NationalityCountryRegion. Użytkownicy będą nadal potrzebować następujących uprawnień do eksportowania tych informacji: HcmWorkerEntityMaintain, HcmWorkerEntityView, HcmEmployeeEntityMaintain, HcmEmployeeEntityMaintain, HcmEmployeeEntityView, HcmContractorEntityMaintain i HCMContractorEntityView. |
| 542147 | Pola **Numer konta bankowego** i **Numer marszruty** są wymagane podczas dodawania konta bankowego poprzez samoobsługę pracownika. | Naprawiliśmy błąd, który powodował, że pracownicy musieli wpisywać pola **Numer konta bankowego** i **Numer rozliczeniowy** podczas dodawania danych konta bankowego. Te pola nie są już wymagane podczas zapisywania informacji o nowym koncie bankowym. |
| 543641 | Kod pocztowy nie jest wypełniany w raportach elektronicznych. | Naprawiono błąd, w wyniku którego kod pocztowy nie pojawiał się w raporcie ACA dla kodów zasięgu od L do Q. |
| 545402 | Dodaj zmianę routingu dla pliku UserBranding.js, aby usunąć błędy 404. | Użytkownik nie powinien już widzieć błędów 404 w konsoli. |

## <a name="in-preview"></a>Wersja próbna   

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aplikacja Human Resources w Microsoft Teams | [Urlop pracownika etatowego i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplikacja Human Resources w Teams](./hr-admin-teams-leave-app.md)<br>[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md) |
| Międzyfirmowe wyświetlanie urlopu dla menedżerów | [Międzyfirmowe wyświetlanie urlopu pracownika etatowego dla menedżerów](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurowanie parametrów urlopu i nieobecności](./hr-leave-and-absence-parameters.md) |

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Potwierdzenie e-mail dla zapisów na świadczenia | Ta funkcja zapewni opcję wysyłania wiadomości e-mail z potwierdzeniem do pracowników, gdy wymeldują się z doświadczeń związanych z rejestracją świadczeń w ramach samoobsługi pracowników. Ta funkcja będzie dostępna 1 lutego. Aby zobaczyć więcej informacji, zobacz [Konfigurowanie parametrów zarządzania świadczeniami w firmie](hr-benefits-setup-parameters-per-company.md). |
| Umiejętności wprowadzone przez menedżera dla swoich pracowników mogą być automatycznie zatwierdzane w przepływie pracy | Wkrótce. |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Aktualizacje terminologii dla Microsoft Dataverse

Od 2020 listopada Common Data Service zmieniło nazwę na [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Więcej informacji można znaleźć w [oficjalnym oświadczeniu](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) na stronie bloga Power Apps. W połączeniu ze zmianą tej nazwy niektóre terminologii Dataverse zostały zaktualizowane. Na przykład *jednostka* to teraz *tabela*, a *pole* to teraz *kolumna*. Aby uzyskać więcej informacji, zobacz [Aktualizacje terminologii](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

W tej wersji terminologia związana z integracją Dynamics 365 Human Resources z Dataverse została zaktualizowana w całej aplikacji, aby odzwierciedlić te zmiany. Na przykład formularz **integracji Common Data Service** jest teraz **integracją Microsoft Dataverse**.

Aby dowiedzieć się więcej o integracji Dynamics 365 Human Resources z programem Microsoft Dataverse, zobacz temat [Konfigurowanie integracji Microsoft Dataverse](./hr-admin-integration-common-data-service.md) i [Konfigurowanie tabel wirtualnych Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]