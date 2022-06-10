---
title: Usunięte lub wycofane funkcje Platform
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji finansowych i operacyjnych.
author: sericks007
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 3de9b9ea0bd20d1346a7cdfd2f919f50374b164c
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811254"
---
# <a name="removed-or-deprecated-platform-features"></a>Usunięte lub wycofane funkcje Platform

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji finansowych i operacyjnych.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

Szczegółowe informacje o obiektów w aplikacji Finanse i Działania można znaleźć w [raportach z wykazami parametrów technicznych](/dynamics/s-e/global/axtechrefrep_61). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finanse i Działania.


## <a name="feature-deprecation-effective-june-2022"></a>Wycofanie funkcji z użytku w czerwcu 2022 r.

### <a name="finance-and-operations-dynamics-365-mobile-application-and-mobile-platform"></a>Aplikacja mobilna i platforma mobilna finansów i operacji (Dynamics 365) 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Pozbywamy się aplikacji mobilnej i platformy finansów i operacji (Dynamics 365), aby skonsolidować je z jedną platformą mobilną, którą jest Power Apps. |
| **Zamieniona przez inną funkcję?**   | Tak, dzięki integracji z Power Platform można zbudować mobilne doświadczenia z danymi z aplikacji finansów i operacji. Więcej szczegółów znajdziesz w [Budowanie doświadczeń mobilnych](../power-platform/build-mobile-experiences.md). |
| **Powiązane obszary produktów**         | Aplikacje Finanse i Działania |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofane. Data zakończenia wsparcia przewidziana jest na październik 2024 roku. |


## <a name="platform-updates-for-version-10029-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.29 aplikacji finansowych i operacyjnych

### <a name="panorama-tab-style"></a>Panorama tab style

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Strony przewijające się w poziomie są zgodne z przestarzałymi wzorcami układu, które mają znane problemy z użytecznością i dostępnością.  |
| **Zamieniona przez inną funkcję?**   | Nie, ale inne style zakładek są nadal dostępne. |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofane. |


## <a name="feature-deprecation-effective-april-2022"></a>Wycofanie funkcji z użytku w kwietniu 2022 r.

### <a name="xml-url-resolution-in-data-management"></a>Rozdzielczość URL XML w zarządzaniu danymi 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Usuwamy obsługę adresów URL XML, ponieważ została ona uznana za potencjalną lukę w zabezpieczeniach. Oznacza to, że zewnętrzne zasoby związane z plikami XML nie będą już rozwiązywane.  |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Aplikacje Finanse i Działania |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofane. |

## <a name="feature-deprecation-effective-march-14-2022"></a>Zakończenie działania z dniem 14 marca 2022 r.

### <a name="xslt-scripting-in-data-management"></a>Skrypty XSLT w zarządzaniu danymi

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa skryptów XSLT w zarządzaniu danymi jest przestarzała, aby poprawić bezpieczeństwo i ochronę danych w aplikacjach finansowych i operacyjnych.  |
| **Zamieniona przez inną funkcję?**   | Nie Klienci i ISV powinni rozważyć ponowne zaimplementowanie swoich rozwiązań w oparciu o język X++, zamiast skryptów XSLT. |
| **Powiązane obszary produktów**         | Aplikacje Finanse i Działania |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Przestarzałe <br><br>**Wyjątek:** odbiorcy, którzy obecnie używać skryptów XLST. Mogą one nadal korzystać z tej wersji do czasu zaktualizowania jej do wersji 10.0.30 lub nowszej. W przypadku wcześniejszych wersji wyjątek ten wygaśnie 31 stycznia 2023 roku. Odbiorcy z tym wyjątkiem odebrali powiadomienie w centrum komunikatów dostępnym w centrum administratora Microsoft 365. |

## <a name="feature-removal-effective-october-2021"></a>Usunięcie funkcji z początkiem października 2021 roku

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Raporty SQL Microsoft Azure w usługach LifeCycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Wszystkie czynności i monitoring będą wykonywane wewnętrznie, przez platformę, poprzez automatyzację. Nie będzie to wymagać ręcznej interwencji.|
| **Zamieniona przez inną funkcję?**   | Tak, istnieje teraz system automatyczny, który powoduje przestarzałe te możliwości. |
| **Powiązane obszary produktów**         | Raporty SQL: Bieżące jednostki DTU, Szczegóły bieżącej jednostki DTU, Pobierz szczegóły blokady, Lista bieżącego przewodnika planu, Pobierz listę identyfikatorów zapytania, Pobierz plan zapytania SQL dla danego identyfikatora planu, Pobierz plany i stan wykonywania zapytań, Pobierz konfigurację ograniczenia, Pobierz statystyki oczekiwania, Lista najdroższych zapytań |
| **Opcja wdrażania**              | Wdrożenie w chmurze: dotyczy środowisk produkcyjnych zarządzanych przez Microsoft oraz piaskownicy od warstwy 2 do warstwy 5. |
| **Stan**                         | Usunięto |

### <a name="azure-sql-actions-in-lcs"></a>Akcje SQL Azure w usłudze LCS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Wycofujemy niektóre akcje SQL w usługach LCS. Wszystkie czynności i monitoring będą wykonywane wewnętrznie, przez platformę, poprzez automatyzację. Nie będzie to wymagać ręcznej interwencji. |
| **Zamieniona przez inną funkcję?**   | Tak, istnieje teraz system automatyczny, który powoduje przestarzałe te możliwości. |
| **Powiązane obszary produktów**         | Akcje SQL: Tworzenie przewodnika planu, który wymusza identyfikator planu, Tworzenie przewodnika planu umożliwiającego dodawanie wskazówek dla tabeli, Usuwanie przewodnika planu, Wyłączanie/włączanie blokad stron i eskalacji blokad, Aktualizowanie statystyk w tabeli, Odbudowa indeksu, Tworzenie indeksu |
| **Opcja wdrażania**              | Wdrożenie w chmurze: dotyczy środowisk produkcyjnych zarządzanych przez Microsoft oraz piaskownicy od warstwy 2 do warstwy 5. |
| **Stan**                         | Usunięto |


## <a name="feature-deprecation-effective-october-2021"></a>Wycofanie funkcji z użytku w październiku 2021 r.

### <a name="show-related-document-attachments-feature"></a>Funkcja „Pokaż załączniki powiązanych dokumentów”

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Funkcja zwracała nieoczekiwane wyniki. |
| **Zamieniona przez inną funkcję?**   | Nie Wszelkie dalsze plany dotyczące tej funkcji będą komunikowane za pośrednictwem standardowego procesu ujawniania grupy czynności wydania. |
| **Powiązane obszary produktów**         | Klient sieci Web — doświadczenie załącznika dokumentu |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Przestarzałe  |

## <a name="platform-updates-for-version-10023-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.23 aplikacji finansowych i operacyjnych

### <a name="ondbsynchronize-event"></a>Zdarzenie OnDBSynchronize

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Brak formantu do wykonania tego zdarzenia. |
| **Zamieniona przez inną funkcję?**   | Tak, przenieś istniejące metody subskrybowane przez zdarzenie **OnDBSynchronize** do rozszerzonej klasy SysSetup. |
| **Powiązane obszary produktów**         | Synchronizacja bazy danych |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofane. Planowana data usunięcia to październik 2022 r. |


### <a name="systemnotificationsmanageraddnotification-api"></a>Interfejs API SystemNotificationsManager.AddNotification

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Firma Microsoft wymaga dodatkowych parametrów podczas dodawania powiadomień. |
| **Zamieniona przez inną funkcję?**   | Tak, interfejs API **SystemNotificationsManager.AddSystemNotification()**. Ten interfejs API wymaga jawnego ustawienia funkcji ExpirationDateTime i RuleID dla generowanych powiadomień. |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofane. Planowana data usunięcia to kwiecień 2023 r. |

## <a name="platform-updates-for-version-10021-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.21 aplikacji finansowych i operacyjnych

### <a name="skype-for-business-online-support"></a>Pomoc techniczna Business Online

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten numer jest dla usługi Business Online został wycofany. Aby uzyskać więcej informacji, zobacz [Temat obsługi usługi Online firmy został wycofany](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/the-skype-for-business-online-service-has-retired/ba-p/2596601). |
| **Zamieniona przez inną funkcję?**   | Obecnie nie, chociaż możemy rozważyć dodanie obecności z aplikacji Teams w przyszłości.|
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | Wycofane. Ustawienie **Skype włączone** zostało wyłączone w wersji 10.0.21. Usunięcie tego ustawienia jest przeznaczone na kwiecień 2022 r.; jednak funkcja przestanie działać po zamknięciu usługi przez zespół Skype. |
 
## <a name="feature-deprecation-effective-august-2021"></a>Wycofanie funkcji z użytku w sierpniu 2021 r.

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Raporty SQL Microsoft Azure w usługach LifeCycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Wszystkie czynności i monitoring będą wykonywane wewnętrznie, przez platformę, poprzez automatyzację. Nie będzie to wymagać ręcznej interwencji.|
| **Zamieniona przez inną funkcję?**   | Tak, istnieje teraz system automatyczny, który powoduje przestarzałe te możliwości. |
| **Powiązane obszary produktów**         | Raporty SQL: Bieżące jednostki DTU, Szczegóły bieżącej jednostki DTU, Pobierz szczegóły blokady, Lista bieżącego przewodnika planu, Pobierz listę identyfikatorów zapytania, Pobierz plan zapytania SQL dla danego identyfikatora planu, Pobierz plany i stan wykonywania zapytań, Pobierz konfigurację ograniczenia, Pobierz statystyki oczekiwania, Lista najdroższych zapytań |
| **Opcja wdrażania**              | Wdrożenie w chmurze: dotyczy środowisk produkcyjnych zarządzanych przez Microsoft oraz piaskownicy od warstwy 2 do warstwy 5. |
| **Stan**                         | Wycofanie: planowana data usunięcia to październik 2021 roku. |

### <a name="azure-sql-actions-in-lcs"></a>Akcje SQL Azure w usłudze LCS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Wycofujemy niektóre akcje SQL w usługach LCS. Wszystkie czynności i monitoring będą wykonywane wewnętrznie, przez platformę, poprzez automatyzację. Nie będzie to wymagać ręcznej interwencji. |
| **Zamieniona przez inną funkcję?**   | Tak, istnieje teraz system automatyczny, który powoduje przestarzałe te możliwości. |
| **Powiązane obszary produktów**         | Akcje SQL: Tworzenie przewodnika planu, który wymusza identyfikator planu, Tworzenie przewodnika planu umożliwiającego dodawanie wskazówek dla tabeli, Usuwanie przewodnika planu, Wyłączanie/włączanie blokad stron i eskalacji blokad, Aktualizowanie statystyk w tabeli, Odbudowa indeksu, Tworzenie indeksu |
| **Opcja wdrażania**              | Wdrożenie w chmurze: dotyczy środowisk produkcyjnych zarządzanych przez Microsoft oraz piaskownicy od warstwy 2 do warstwy 5. |
| **Stan**                         | Wycofanie: planowana data usunięcia to październik 2021 roku. |

## <a name="feature-deprecation-effective-may-2021"></a>Wycofanie funkcji z użytku w maju 2021 r.

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>Portal globalizacyjny w Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Pozbywamy się portalu Globalizacja w LCS, ponieważ ta funkcja została zastąpiona przez inne usługi oparte na LCS. |
| **Zamieniona przez inną funkcję?**   | Tak, ta funkcja została zastąpiona przez usługę [wyszukiwania problemów](../lifecycle-services/issue-search-lcs.md) LCS i [usługę przesyłania alertów dotyczących wymogów prawnych Dynamics](../lcs-solutions/submit-localization-alerts.md). |
| **Powiązane obszary produktów**         | Portal globalizacyjny w LCS|
| **Opcja wdrażania**              | Wdrożenie w chmurze |
| **Stan**                         | Wycofanie: planowana data usunięcia to maj 2022 roku. |


## <a name="feature-removed-effective-january-28-2021"></a>Funkcja usunięta 28 stycznia 2021 r.

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>Zadanie wsadowe do obsługi defragmentacji indeksu SQL

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ta funkcja została usunięta w celu zmniejszenia kosztów ogólnych działania, monitorowania i obsługi zarządzania indeksami przez odbiorców. |
| **Zamieniona przez inną funkcję?**   | W przyszłości zarządzanie indeksami będzie wykonywane przez usługi Microsoft. Będzie to się odbywać w sposób ciągły bez wpływu na obciążenia użytkowników. |
| **Powiązane obszary produktów**         | Aplikacje Finanse i Działania|
| **Opcja wdrażania**              | Wdrożenie w chmurze — dotyczy środowisk produkcyjnych zarządzanych przez Microsoft oraz piaskownicy od warstwy 2 do warstwy 5. |
| **Stan**                         | Ta funkcja została usunięta. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.17 aplikacji finansowych i operacyjnych


### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Aby można było obsługiwać najnowsze wersje Visual Studio, niektóre zmiany należy wprowadzać w odniesieniu do rozszerzeń X++ dla Visual Studio. Te zmiany są niezgodne z Visual Studio 2015. |
| **Zamieniona przez inną funkcję?**   | Visual Studio 2017 zamieni Visual Studio 2015 jako wdrożoną i wymaganą wersję. |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Wycofanie: Po zaktualizowaniu poprzednie narzędzia X++ zostaną usunięte z programu Visual Studio 2015, a zaktualizowane narzędzia nie zostaną zainstalowane w programie Visual Studio 2015. Nie ma to wpływu na hostowane kompilacje. W przypadku tworzenia maszyn wirtualnych potok kompilacji (definicja kompilacji) należy ręcznie zaktualizować, aby można było zmienić zależność od wersji MSBuild 14.0 (Visual Studio 2015) do wersji MSBuild 15.0 (Visual Studio 2017), zgodnie z opisem w temacie [Aktualizowanie potoku w starszej wersji w usłudze Azure Pipelines](../dev-tools/pipeline-msbuild-update.md). |

### <a name="user-avatar"></a>Awatar użytkownika 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Awatar użytkownika wyświetlany po prawej stronie paska nawigacji został pobrany za pomocą interfejsu API z kontrolki nagłówka usługi Dynamics 365, która jest przestarzała. |
| **Zamieniona przez inną funkcję?**   | Użytkownicy widzą swoje inicjały w okręgu na pasku nawigacji. Ten sam wygląd jest obecnie stosowany w przypadku komputerów deweloperskich. |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Usunięto od wersji 10.0.17 |

### <a name="enterprise-portal-ep-deprecation"></a>Enterprise Portal (EP) — uznanie za rozwiązanie przestarzałe  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Artefakty metadanych skojarzone z aplikacją Dynamics AX 2012 Enterprise Portal (EP) są przestarzałe, ponieważ portal EP nigdy nie był obsługiwany w aplikacjach finansowych i operacyjnych. |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Wycofanie: Cały kod EP ma zostać usunięty w wersji z października 2021 r. |

## <a name="deprecation-effective-december-2020"></a>Amortyzacja obowiązuje od grudnia 2020 r.

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Wsparcie Internet Explorer 11 dla Dynamics 365 jest przestarzałe

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Począwszy od grudnia 2020 r., obsługa Microsoft Internet Explorer 11 dla wszystkich produktów Dynamics 365 i Dynamics Lifecycle Services (LCS) jest przestarzała, a Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021 r.<br><br>Będzie to miało wpływ na klientów, którzy używają produktów Dynamics 365 i LCS zaprojektowanych do używania za pośrednictwem interfejsu Internet Explorer 11. Po sierpniu 2021, Internet Explorer 11 nie będzie obsługiwany przez produkty Dynamics 365 i LCS. |
| **Zamieniona przez inną funkcję?**   | Zaleca się, aby klienci przeszli na Microsoft Edge.|
| **Powiązane obszary produktów**         | Wszystkie produkty Dynamics 365 i LCS |
| **Opcja wdrażania**              | Wszystko|
| **Stan**                         | Wycofanie: Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021.|

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.15 aplikacji finansowych i operacyjnych

### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Dodatek Visual Studio do stosowania poprawek metadanych

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Poprawki metadanych nie są już obsługiwane w aktualizacjach usługi [One Version](../../fin-ops/get-started/one-version.md), która zostały wprowadzone w lipcu 2018 r. w wersji 8.1. |
| **Zamieniona przez inną funkcję?**   | Poszczególne poprawki metadanych nie są dostępne dla obsługiwanych wersji. Zamiast tego stosowane są skumulowane aktualizacje jakości. |
| **Powiązane obszary produktów**         | Dodatki Visual Studio |
| **Opcja wdrażania**              | Maszyny wirtualne programowania |
| **Stan**                         | W wersji 10.0.15 dodatek nie jest już uwzględniany w narzędziach Visual Studio. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.14 aplikacji finansowych i operacyjnych

### <a name="online-users-page"></a>Strona Zalogowani użytkownicy 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | To jest starsza strona, która została stworzona dla poprzedniej architektury klient / serwer. Informacje na tej stronie nie zawsze są dokładne, co może być mylące i wprowadzające w błąd. |
| **Zamieniona przez inną funkcję?**   | W przyszłej aktualizacji zostanie wyświetlona nowa strona.|
| **Powiązane obszary produktów**         | Administrowanie systemem |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Do października 2021 ten formularz zostanie usunięty.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.13 aplikacji finansowych i operacyjnych


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Kod niestandardowy zdefiniowany we właściwościach raportu SSRS 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ogólnie rzecz, kod niestandardowy oferuje ograniczone korzyści jednocześnie, wymaga znaczącego odzyskania i obliczenia do działu pomocy technicznej. Kod niestandardowy jest używany głównie przez autorów raportów do wywoływania metod publicznych z zestawu kodu niestandardowego. Jednak usługa hostowana w chmurze nie obsługuje odwołań do niestandardowych zestawów raportów SSRS. |
| **Zamieniona przez inną funkcję?**   | Autorzy raportów mogą kontynuować odwołując się do interfejsów API publicznego rozwiązania .NET dla operacji matematycznych, konwersji i formatowania z dowolnego wyrażenia pola tekstowego. Aby uzyskać więcej informacji, zobacz [Dodaj kod do raportu (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs).  |
| **Powiązane obszary produktów**         | Podzbiór projektów raportów aplikacji zdefiniowany w module RDL, które zawierają kod niestandardowy. |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | W przypadku wersji 10.0.13 kompilator rozpocznie generowanie ostrzeżenia o wystąpieniach, w których w definicji raportu SSRS zostanie wykryty kod niestandardowy. Aby rozwiązać ten problem, Otwórz definicję projektu raportu i Usuń wszystkie artefakty kodu niestandardowego. Ostrzeżenie kompilatora zostanie zastąpione błędem kompilatora w przyszłej aktualizacji.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Uaktualnienie trzech bibliotek składników jQuery 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Są aktualizowane trzy biblioteki składników jQuery dla poprawek zabezpieczeń oraz do obsługi waluty.   
| **Zamieniona przez inną funkcję?**   | Dotyczy to następujących bibliotek: jQuery (do wersji 3.5.0 z wersji 2.1.4), interfejsu użytkownika jQuery (do wersji 1.12.1 z wersji 1.11.4), jQuery qTip (do wersji 3.0.3 z 2.2.1). Wskazówki dotyczące migracji zostały dostarczone w trybie online przez jQuery.  |
| **Powiązane obszary produktów**         | Rozszerzalne kontrolki, w szczególności niestandardowy kod JavaScript wykorzystujący przestarzałe lub usunięte interfejsy API |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | W przypadku wersji 10.0.13/aktualizacji platformy 37 klienci mogą opcjonalnie przełączać się do najnowszych bibliotek, włączając funkcję „Uaktualnij trzy biblioteki składników jQuery”. Przechodzenie do nowych bibliotek będzie obowiązkowe wraz z wydaniem z kwietnia 2021, aby umożliwić migrację interfejsów API, których dotyczy problem.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Istniejący interfejs API kontroli/forceLegacyGrid() sieci

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Istniejąca kontrolka siatki jest zastępowany nową kontrolką siatki. |
| **Zamieniona przez inną funkcję?**   | [Nowa kontrolka siatki](../..//fin-ops/get-started/grid-capabilities.md) |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | W wersji 10.0.13 nowa kontrola sieci jest ogólnie dostępna, a klienci mogą opcjonalnie włączyć tę funkcję. Nowa kontrola sieci zostanie domyślnie włączona w wydaniu z października 2021 r. i obecnie ma być obowiązkowa w kwietniu 2022 r. Gdy nowa kontrola sieci stanie się obowiązkowa, API **forceLegacyGrid()** nie będzie już honorowane. |

### <a name="personalization-without-saved-views"></a>Personalizacja bez zapisanych widoków 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Podsystem personalizacji został zastąpiony funkcją zapisane widoki, dzięki czemu ma lepszą wydajność i oferuje dodatkowe możliwości. |
| **Zamieniona przez inną funkcję?**   | Zapisane widoki |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | W wersji 10.0.13/platform aktualizację 37, funkcja zapisanych widoków jest ogólnie dostępna, a odbiorcy mogą opcjonalnie włączyć tę funkcję. Funkcja zapisanych widoków stanie się obowiązkowa w wersji z października 2021 r. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.12 aplikacji finansowych i operacyjnych

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Rozszerzenia formularza siatki lub grup kontrolek zawierające nieprawidłowe odwołania do pól

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Właściwość Grupa danych w kontrolkach siatki i grup służy do automatycznego pokazywania wszystkich pól grupy pól. Kontrolka siatki lub grupy dodana przez rozszerzenie może zawierać pola, które nie są już zdefiniowane w grupie pól, lub może nie mieć pól, które są zdefiniowane w grupie pól. Może to spowodować niespójne działanie w czasie wykonywania. Aktualizacje platformy dla wersji 10.0.12 aplikacji finansowych i operacyjnych teraz klasyfikuje ten problem jako *ostrzeżenie* kompilatora. Aby rozwiązać ten problem, otwórz rozszerzenie formularza i zapisz je.
| **Zamieniona przez inną funkcję?**   | To ostrzeżenie kompilatora zostanie zastąpione błędem kompilatora w przyszłej aktualizacji. |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Ostrzeżenie kompilatora jest wprowadzone w aktualizacjach platformy dla wersji 10.0.12 aplikacji finansowych i operacyjnych. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.11 aplikacji finansowych i operacyjnych

### <a name="explicit-safe-lists-for-self-service-environments"></a>Jawne bezpieczne listy dla środowisk samoobsługowych

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Proces przenoszenia adresu IP do list bezpiecznych został zmieniony. Samoobsługa nie obsługuje już bezpiecznych list adresów IP. |
| **Zamieniona przez inną funkcję?**   | Aby uzyskać więcej informacji, zobacz [Konfiguracja warunkowego dostępu do Azure Active Directory](/appcenter/general/configuring-aad-conditional-access).|
| **Powiązane obszary produktów**         | Zabezpieczenia |
| **Opcja wdrażania**              | W chmurze |
| **Stan**                         | Przestarzałe: Ta funkcja jest całkowicie przestarzała w przypadku wdrożeń samoobsługowych. |

### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Aby można było obsługiwać najnowsze wersje Visual Studio, niektóre zmiany należy wprowadzać w odniesieniu do rozszerzeń X++ dla Visual Studio. Te zmiany są niezgodne z Visual Studio 2015. |
| **Zamieniona przez inną funkcję?**   | Visual Studio 2017 zamieni Visual Studio 2015 jako wdrożoną i wymaganą wersję. |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Maszyny wirtualne wdrożone w wersji 10.0.13 (Aktualizacja platformy 37) i nowszych zawierają program Visual Studio 2017. Wersja 10.0.16 (Aktualizacja platformy 40) to ostateczna wersja z obsługą programu Visual Studio 2015. Maszyny wirtualne zawierające tylko program Visual Studio 2015 nie będą mogły zostać zaktualizowane do wersji 10.0.17 (Aktualizacja platformy 41). |

### <a name="field-groups-containing-invalid-field-references"></a>Grupy pól zawierających nieprawidłowe pole odwołania

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Grupy pól w definicjach metadanych tabeli mogą zawierać nieprawidłowe odwołania pól. Jeśli te grupy pól zostaną wdrożone, mogą powodować awarie środowiska wykonawczego w Financial Reporting i Microsoft SQL Server Reporting Services (SSRS). Aktualizacja platformy 23 wprowadziła *ostrzeżenie* kompilatora, które umożliwiło zaadresowanie tego problemu z metadanymi. Aktualizacje platformy dla wersji 10.0.11 aplikacji finansowych i operacyjnych teraz klasyfikuje ten problem jako *błąd* kompilatora.<p>Aby naprawić ten problem, należy wykonać następujące czynności.</p><ol><li>Usuń nieprawidłowe odwołanie pola z definicji grupy pól tabel.</li><li>Kompiluj ponownie.</li><li>Upewnij się, że wszystkie błędy zostały rozwiązane.</li></ol> |
| **Zamieniona przez inną funkcję?**   | Ten błąd kompilatora powoduje trwałe zastąpienie ostrzeżenia kompilatora.  |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: ostrzeżenie kompilatora to błąd kompilatora w aktualizacjach platformy dla wersji 10.0.11 aplikacji finansowych i operacyjnych. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licencje ISV utworzone przy użyciu algorytmu wyznaczania wartości skrótu SHA1

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Proces tworzenia licencji niezależnych dostawców oprogramowania (ISV) został zmieniony. Aby uzyskać więcej informacji, zajrzyj do [Licencjonowanie niezależnego dostawcy oprogramowania (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Zamieniona przez inną funkcję?**   | Tak. Do tworzenia licencji używaj Windows PowerShell. |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: licencje ISV utworzone za pomocą algorytmu wyznaczania wartości skrótu SHA1. Ten algorytm jest zależny od certyfikatów utworzonych za pomocą narzędzia MakeCert, a to narzędzie jest przestarzałe.<br><br>Przestarzałe: użycie algorytmu SHA1 na potrzeby zabezpieczeń lub wyznaczania wartości skrótu. Algorytm SHA1 przestanie działać na początku 2021. Dlatego nie należy go już używać.<br><br>Usunięto : Obsługa żądań przychodzących lub wychodzących dotyczących zabezpieczeń TLS (Transport Layer Security) 1.0 i TLS 1.1. |

## <a name="platform-update-32"></a>Aktualizacja platformy Update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Okno dialogowe zmiana żądania przepływu pracy nie zawiera już listy rozwijanej wyboru użytkownika

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Była to kwestia błędu zabezpieczeń, ponieważ żądanie zmiany może zostać wysłane do niezamierzonego użytkownika. Był to również błąd użyteczności, ponieważ zmuszał użytkownika do określenia, kto był wytwórcą przepływu pracy został i ręczny jego wybór.  |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Przepływ pracy |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Lista rozwijana wyboru użytkownika została usunięta z okna dialogowego zmiany żądania w aktualizacji platformy 32. Żądania zmiany żądania zostaną automatycznie wysłane do inicjatora zgodnie z zamierzeniem. Aby uzyskać więcej informacji o tych funkcjach, zapoznaj się z tematem [Akcje w procesach zatwierdzania w przepływie pracy](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Osadzone łącza drążenia wskroś nie są już obsługiwane w dokumentach z podziałem, renderowanych przez usługę hostowaną w chmurze 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Adresy URL nawigacji osadzone w dokumentach renderowanych przez usługę mogą zawierać poufne dane biznesowe. Usuwamy pomoc techniczną dla łączy typu „drążenie wskroś” w dokumentach jako środek bezpieczeństwa, aby dodatkowo chronić dane odbiorców. Użytkownicy będą również mogli uzyskać lepszą wydajność podczas interaktywnego tworzenia dokumentów w wyniku tej zmiany.  |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Raportowania |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Ta funkcja jest aktywnie usuwana z usługi.<br><br>Nowoczesne oprogramowanie klienckie oferuje wiele opcji tworzenia widoków, które zawierają automatycznie generowane łącza umożliwiające nawigację po aplikacji. Dokumenty z podziałem, renderowane przez usługę, są zalecane w przypadku komunikacji zewnętrznej, które są wysyłane, archiwizowane i drukowane dla odbiorców. Ulepszono możliwości wyświetlania podglądu dokumentów bezpośrednio w przeglądarce, która oferuje bezpośredni dostęp do drukarek lokalnych. Aby uzyskać więcej informacji, zobacz [Podgląd dokumentów PDF za pomocą osadzonej przeglądarki](../analytics/preview-pdf-documents.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach
Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
