---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 22 marca 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 22 marca 2021 roku.
author: marcelbf
ms.date: 03/22/2021
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
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5854fa8c89f1a72c32bd480e71c1cd0a743c6cd7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803352"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 22 marca 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2021 wydanie 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.4049.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Opcja wymuszania anulowania i resetowania zablokowanych zadań wsadowych (560976) | NA | [Resetowanie zablokowanych zadań wsadowych](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-troubleshooting-batch-execution) |
| Pomocnicze aktualizacje UX w celu utworzenia nowego planu świadczeń (419941) | NA | [Tworzenie planu świadczeń](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Wystawienie |  opis |
| --- | --- | --- |
| 554239 | Usprawnienia wydajności jednostek powiązanych z tabelą **BusinessProcessTaskAssignment** | Zwiększ wydajność jednostek powiązanych z tabelą **BusinessProcessTaskAssignment**, dodając sugerowane indeksy do tabeli. |
| 566061 | Usuń kod powrotu jednostki wersji 2 z nocnej synchronizacji | Usuń kod powrotu wersji V2 dla nocnej synchronizacji Dataverse. Wycofanie nie jest już potrzebne i filtrowanie synchronizacji uniemożliwia synchronizację z działaniem zgodnie z oczekiwaniami. Zmiana podniesie spójność synchronizacji danych Dataverse. |
| 538024 | Plany świadczeń pracownika > Usuń błąd zgłaszania transakcji | Wystąpił błąd podczas usuwania realizacji zamówienia dla opcji Plan świadczeń w formularzu Świadczenia pracownika. |
| 557965 | Obszar roboczy **Świadczenia**: łącze do **Aktywnych zdarzeń życia** powinno być zawsze widoczne w sekcji **Łącza** | Wystąpił problem z widocznym łączem do **Aktywnych zdarzeń życiowych** w sekcji **Łącza**, ale wystąpił błąd podczas próby nawigacji, jeśli funkcja obszaru roboczego **Zarządzanie świadczeniami (Wersja zapoznawcza)** nie jest włączona. Aby uzyskać więcej informacji dotyczących włączania obszaru roboczego, zobacz [obszar roboczy Zarządzanie świadczeniami](hr-benefits-management-workspace.md). |
| 556672 | Nie można przetworzyć nalików dla przerwanego pracownika, gdy w funkcji zarządzania funkcjami jest włączona funkcja **Usprawnione wprowadzanie pracowników** | Opcja naliczania urlopu i planów nieobecności została dodana do opcji **Więcej opcji** w obszarze **Historia pracy** dla pracowników, gdy w funkcjach zarządzania funkcjami jest włączona funkcja **Usprawnionego wprowadzania pracowników**. |
| 562656 | Element menu **SysRecordChangeLogValidTimeState** powinien być włączony jako uprawnienie zabezpieczeń oraz rozszerzenie obowiązku zabezpieczeń **SystemExternalBasicMaintain** | W rolach administratorów innych niż systemowe brakuje przycisku **Wyświetl zmiany** w formularzach menedżera dat. |
| 505989 | Przetwarzanie zdarzeń życia: zmiana uprawnień nie jest przetwarzana poprawnie z powodu użytej daty | Stały problem, w którym zmiana w przetwarzaniu uprawnień była zależna od daty rozpoczęcia ważności stanowiska, a nie tylko bieżącego stanowiska. |
| 562286 | Rozwiązanie umowy z pracownikiem powoduje wysłanie wielu aktualizacji do Dataverse | Gdy pracownik zostanie przerwany, do rozwiązania Dataverse zostanie wysłana więcej niż jedna operacja aktualizacji, w wyniku czego dwie aktualizacje powiadomią o tej samej zmianie. Może to spowodować wiele wyzwalaczy, jeśli przepływ Power Automate jest skonfigurowany do wyzwalania z akcji. |
| 527340 | Podczas otwierania rejestracji urlopów i nieobecności wyświetlany jest błąd „Niereprezentowalna data i godzina” | Podczas wybierania rejestracji urlopu i nieobecności błąd nie jest już wyświetlany. |
| 561663 | Zwiększ przedział czasu oczekiwania na inicjowanie obsługi grup | Poprawić stabilności infrastruktury i zapewnić spójność zasobów dzięki aktualizacjom zasobów grupowych. |
| 486129 | Nie można edytować niestandardowych pól w obszarze **Stanowiska > Zarządzaj zmianami** | Rozwiązano problem z możliwością edytowania pól niestandardowych na karcie **Zarządzanie zmianami** dla **Stanowisk**. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Obszar roboczy zarządzania świadczeniami | [Obszar roboczy zarządzania korzyściami (wersja zapoznawcza)](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Obszar roboczy zarządzania świadczeniami](hr-benefits-management-workspace.md) |
| Ograniczenie pracownikom możliwości edytowania biznesowych danych kontaktowych | [Ograniczenie pracownikom możliwości edytowania biznesowych danych kontaktowych](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Ogranicz edytowanie informacji osobistych](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Wkrótce

| Funkcja | Szczegóły |
| --- | --- |
| Umiejętności wprowadzone przez menedżera dla swoich pracowników mogą być automatycznie zatwierdzane w przepływie pracy | Wkrótce. |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2021 wydanie 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2021, wydanie 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
