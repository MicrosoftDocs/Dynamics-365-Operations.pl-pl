---
title: Rozszerzanie rozwiązania Talent przy użyciu usług PowerApps i Microsoft Flow — przykładowe scenariusze
description: W tym temacie opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 for Talent używanych przez Microsoft PowerApps i Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 0b455a8194f58b41a349f004ceda8183c7ee3f7c
ms.sourcegitcommit: 9f94eff93d29bc27352569824e00bbccc2f961b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2019
ms.locfileid: "1781449"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a>Rozszerzanie rozwiązania Talent przy użyciu usług PowerApps i Microsoft Flow — przykładowe scenariusze

W tym temacie opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 for Talent używanych przez Microsoft PowerApps i Microsoft Flow. Można zaimportować pakiet rozwiązań skojarzony z każdym przykładem do środowiska usługi PowerApps. Następnie można używać pakietów jako pomocy lub punktów początkowych do implementacji scenariuszy odpowiednich dla Twojej organizacji.

> [!IMPORTANT]
> Jeśli chcesz korzystać z szablonów i aplikacji, które zostały opisane w tym temacie „tak jak są”, sprawdź je, aby upewnić się, że będą one obejmować wszystkie scenariusze, które są specyficzne dla danej implementacji.


## <a name="prerequisites"></a>Wymagania wstępne

- Aby zaimportować pakiety, użytkownicy muszą mieć uprawnienie **Twórca środowisk**.
- Aby eksportować lub importować aplikacje, musisz mieć licencję PowerApps plan 2 lub licencję próbną PowerApps Plan 2.

## <a name="flow--form-connect"></a>Przepływ — połączenie formularza

Szablon **Przepływ — połączenie formularza** może być używany do odczytu danych z programu Microsoft Forms i zapisania ich w jednostce Common Data Service.

Ten szablon może zostać rozszerzony, tak aby można było go używać w innych scenariuszach. Oto kilka przykładów:

- Przechwytywanie ocen kandydata.
- Przechwytywanie wyników z kwestionariuszy na kursie.
- Kompilowanie biblioteki pytań na rozmowy kwalifikacyjne dla administratorów zasobów ludzkich (HR).
- Przechwytywania oceny kandydata po rozmowie kwalifikacyjnej

W Microsoft Dynamics 365: Attract, formularze mogą pojawiać się w portalu dla kandydatów i kandydaci mogą wypełniać szczegóły. Formularze mogą być również osadzone jako działania w szablonie stanowiska.

Po przesłaniu formularza przez kandydata Microsoft Flow przechwytuje przesłanie formularza, odczytuje dane i zapisuje je w jednostce Common Data Service.

Aby pobrać szablon **Przepływ — połączenie formularza** i strukturę jednostki niestandardowej, przejdź do sekcji [Przepływ — połączenie formularza](https://go.microsoft.com/fwlink/?linkid=2081988) w centrum pobierania Microsoft.

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a>Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps

Szablon **Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps** może być używany jako punkt początkowy dla dowolnych scenariuszy PowerApps charakterystycznych dla Attract. Zawiera on wszystkie parametry domyślne, które są przekazywane przez Attract, takie jak **Podanie o pracę**, **identyfikator kandydata**, i **JobID**.

Za pomocą tego szablonu można pobrać formularz oceny kandydata, dzięki czemu menedżer zatrudniający może wyświetlić ocenę wypełnioną przez kandydata.

Aplikacje, które są tworzone przy użyciu usługi PowerApps mogą być osadzone w szablonie stanowiska w Attract.

Aby pobrać szablon **Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps** i strukturę jednostki niestandardowej, przejdź do [Inicjowanie i wyodrębnianie parametrów przekazanych do usługi Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) w centrum pobierania Microsoft.

## <a name="integration-with-office-365"></a>Integracja z programem Office 365

Aplikacja **Integracja z Office 365** może być używana do pobierania danych zespołu dla zarejestrowanych użytkowników z Microsoft Office 365. Odwołuje się ono do pracowników w Talent do wyodrębnienia szczegółów zarejestrowania i wyrejestrowania oraz nagrań wyjątku. Szczegóły zarejestrowania i wyrejestrowania znajdują się w niestandardowych jednostkach Common Data Service. Zakłada się, że te szczegóły są wypełniane na podstawie informacji w systemach zewnętrznych poprzez integrację.

Ta aplikacja może zostać rozszerzona, tak aby można było jej używać w innych scenariuszach. Na przykład może służyć do wyświetlania informacji dotyczących urlopu zespołu, zdarzeń kalendarza i zdarzeń specyficznych dla zespołu.

Aby pobrać aplikację **Integracja z Office 365** i strukturę jednostki niestandardowej, przejdź do [Integracja z Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) w centrum pobierania Microsoft.

## <a name="flow--email-notification"></a>Przepływ — powiadomienie pocztą e-mail

Szablon **Przepływ — powiadomienie pocztą e-mail** może być używany w scenariuszach powiadamiania pocztą e-mail. Może służyć do wyzwalania wiadomości e-mail z powiadomieniem kandydatów, których zespół rekrutacyjny odrzuci na dowolnym etapie procesu rekrutacji.

Ten szablon można rozszerzyć w celu śledzenia zmian w fazie kandydata w całym procesie rekrutacji i do wysyłania powiadomień do zespołu rekrutacyjnego oraz kandydata.

Generalnie, w przypadku jednostek zapisanych w Common Data Service, przepływy można ustawić tak, aby system wysyłał powiadomienia dotyczące zdarzeń w Core HR, Attract lub Dynamics 365 Talent: Onboard.

Aby pobrać szablon **przepływ — powiadomienie pocztą e-mail**, przejdź do [przepływ — powiadomienie pocztą E-mail](https://go.microsoft.com/fwlink/?linkid=2082103) w centrum pobierania Microsoft.

## <a name="flow--sql-connect-and-execute"></a>Przepływ — połączenie SQL i wykonywanie

Szablon **Przepływ — połączenie SQL i wykonywanie** łączy się z Microsoft SQL Server i umożliwia uruchamianie kwerend przez SQL.

Chociaż ten szablon jest przeznaczony do odczytu i aktualizowania tabel SQL, może zostać rozszerzony, tak aby można było z niego korzystać także w innych scenariuszach. Na przykład, jego może służyć do wypełnienia tabeli tymczasowej Common Data Service rekordami z programu SQL Server i do okresowego synchronizowania tabeli tymczasowej przy użyciu wypychania przyrostowego z programu SQL Server.

Aby pobrać szablon **Przepływ — połączenie SQL i wykonywanie**, przejdź do sekcji [Przepływ — połączenie SQL i wykonywanie](https://go.microsoft.com/fwlink/?linkid=2081789) w centrum pobierania Microsoft.

## <a name="flow--sharepoint-integration"></a>Przepływ — integracja z SharePoint

Szablon **Przepływ — integracja z SharePoint** może służyć do odczytywania danych z listy programu SharePoint, porównywania listy z wartościami pól dla jednostek Common Data Service i wysyłania wyników porównań w wiadomości e-mail z powiadomieniem. 

Organizacja może mieć zestaw umiejętności, które są pilnie wymagane. Te kwalifikacje można przechowywać w SharePoint jako listy SharePoint. Gdy kandydat złoży podanie o pracę na stanowisku, dla którego jest lista wymaganych kwalifikacji, jeśli jest dostateczny poziom dopasowania między kwalifikacjami kandydata a kwalifikacjami zapisanymi w SharePoint, zostanie wysłane powiadomienie e-mail. W ten sposób stanowiska, które wymagają pilnego obsadzenia, są obsadzane szybciej, ponieważ powiadomienia pomagają rekruterom znajdować i zatrudniać kandydatów wewnątrz organizacji.

Ten szablon może zostać rozszerzony tak, aby można go było używać w dowolnych scenariuszach uwzględniających integrację SharePoint.

Aby pobrać szablon **przepływ — integracja SharePoint**, przejdź do [przepływ — integracja SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) w centrum pobierania Microsoft.

## <a name="referral-app"></a>Aplikacja Poleceń
Za pomocą aplikacji Poleceń można dodawać kandydatów do udostępnionej puli talentów. Osoba polecająca może wprowadzić wartość **Imię**, **Nazwisko**, **Adres e-mail** i **Linkedln URL** podczas przesyłania kandydata. Metadane źródła kandydata są następnie wypełniane informacjami osoby polecającej.

Tę aplikację można osadzić w module Samoobsługa pracownika (ESS) w celu przesłania polecenia lub można używać jej jako hiperłącza w portalu korporacyjnym i uruchamiać jako autonomiczną aplikację.

Aby pobrać **Aplikację Poleceń**, przejdź do [Dynamics 365 for Talent do rozwiązania rozszerzalności: Aplikacja Poleceń](http://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) w Microsoft — Centrum pobierania. Możesz zaimportować tę aplikację i dostosować ją w celu dodania dodatkowych funkcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migracja aplikacji między dzierżawcami i środowiskami](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
