---
title: Rozszerz aplikację Talent o usługi Power Apps i Power Automate
description: W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Talent - Attract używanych przez Microsoft Power Apps i Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 1051fa4db16bb94cc9d60a91fc3637d7e5305cc2
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029918"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Rozszerz aplikację Talent o usługi Power Apps i Power Automate

W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Talent: Attract - Attract używanych przez Microsoft Power Apps i Microsoft Power Automate. Można zaimportować pakiet rozwiązań skojarzony z każdym przykładem do środowiska Power Apps. Następnie można używać pakietów jako pomocy lub punktów początkowych do implementacji scenariuszy odpowiednich dla Twojej organizacji.

> [!IMPORTANT]
> Jeśli chcesz korzystać z szablonów i aplikacji, które zostały opisane w tym artykule „tak jak są”, sprawdź je, aby upewnić się, że będą one obejmować wszystkie scenariusze, które są specyficzne dla danej implementacji.


## <a name="prerequisites"></a>Wymagania wstępne

- Aby zaimportować pakiety, użytkownicy muszą mieć uprawnienie **Twórca środowisk**.
- Aby eksportować lub importować aplikacje, musisz mieć licencję Power Apps plan 2 lub licencję próbną Power Apps Plan 2.

## <a name="power-automate--form-connect"></a>Power Automate — połączenie formularza

**Power Automate — połączenie** formularza może być używany do odczytu danych z programu Microsoft Forms i zapisania ich w jednostce Common Data Service.

Ten szablon może zostać rozszerzony, tak aby można było go używać w innych scenariuszach. Oto kilka przykładów:

- Przechwytywanie ocen kandydata.
- Przechwytywanie wyników z kwestionariuszy na kursie.
- Kompilowanie biblioteki pytań na rozmowy kwalifikacyjne dla administratorów zasobów ludzkich (HR).
- Przechwytywania oceny kandydata po rozmowie kwalifikacyjnej

W Microsoft Dynamics 365: Attract, można używać formularzy w portalu dla kandydatów, gdzie kandydaci mogą wypełniać szczegóły. Formularze mogą być również osadzone jako działania w szablonie stanowiska.

Po przesłaniu formularza przez kandydata Microsoft Power Automate przechwytuje przesłanie formularza, odczytuje dane i zapisuje je w jednostce Common Data Service.

Aby pobrać szablon **Power Automate— połączenie formularza** i strukturę jednostki niestandardowej, przejdź do sekcji [Power Automate — połączenie formularza](https://go.microsoft.com/fwlink/?linkid=2081988) w centrum pobierania Microsoft.

## <a name="power-automate--sharepoint-integration"></a>Power Automate – Integracja SharePoint

**Power Automate — integracja z SharePoint** może służyć do odczytywania danych z listy Microsoft SharePoint, porównywania listy z wartościami pól dla jednostek Common Data Service i wysyłania wyników porównań w wiadomości e-mail z powiadomieniem. 

Organizacja może mieć zestaw umiejętności, które są pilnie wymagane. Te kwalifikacje można przechowywać w SharePoint jako listy SharePoint. Gdy kandydat złoży podanie o pracę na stanowisku, dla którego jest lista wymaganych kwalifikacji, jeśli jest dostateczny poziom dopasowania między kwalifikacjami kandydata a kwalifikacjami zapisanymi w SharePoint, zostanie wysłane powiadomienie e-mail. W ten sposób stanowiska, które wymagają pilnego obsadzenia, są obsadzane szybciej, ponieważ powiadomienia pomagają rekruterom znajdować i zatrudniać kandydatów wewnątrz organizacji.

Ten szablon może zostać rozszerzony tak, aby można go było używać w dowolnych scenariuszach uwzględniających integrację SharePoint.

Aby pobrać **Power Automate – SharePoint integracja**, przejdź do [Power Automate – integracja SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) w centrum pobierania Microsoft.

## <a name="referral-app"></a>Aplikacja Poleceń

Za pomocą aplikacji Poleceń można dodawać kandydatów do udostępnionej puli talentów. Osoba polecająca może wprowadzić wartość **Imię**, **Nazwisko**, **Adres e-mail** i **Linkedln URL** podczas przesyłania kandydata. Metadane źródła kandydata są następnie wypełniane informacjami osoby polecającej.

Tę aplikację można osadzić w module Samoobsługa pracownika (ESS) w celu przesłania polecenia lub można używać jej jako hiperłącza w portalu korporacyjnym i uruchamiać jako autonomiczną aplikację.

Aby pobrać **Aplikację Poleceń**, przejdź do [Dynamics 365 Talent do rozwiązania rozszerzalności: Aplikacja Poleceń](https://www.microsoft.com/download/details.aspx?id=58497) w Microsoft — Centrum pobierania. Możesz zaimportować tę aplikację i dostosować ją w celu dodania dodatkowych funkcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Migracja aplikacji między dzierżawcami i środowiskami](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
