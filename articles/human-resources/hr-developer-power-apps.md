---
title: Rozszerz aplikację Talent o usługi Power Apps i Power Automate
description: W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Human Resources - Attract używanych przez Microsoft Power Apps i Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: Dynamics 365 Human Resources;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core;Experience Apps;Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8d4185b958ed35e9d2bc764db8ea77b3a2f53c37
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029872"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Rozszerzanie za pomocą rozwiązań Power Apps i Power Automate

W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Human Resources - Attract używanych przez Microsoft Power Apps i Microsoft Power Automate. Można zaimportować pakiet rozwiązań skojarzony z każdym przykładem do środowiska Power Apps. Następnie można używać pakietów jako pomocy lub punktów początkowych do implementacji scenariuszy odpowiednich dla Twojej organizacji.

> [!IMPORTANT]
> Jeśli chcesz korzystać z szablonów i aplikacji, które zostały opisane w tym temacie „tak jak są”, sprawdź je, aby upewnić się, że będą one obejmować wszystkie scenariusze, które są specyficzne dla danej implementacji.

## <a name="prerequisites"></a>Wymagania wstępne

- Aby zaimportować pakiety, użytkownicy muszą mieć uprawnienie **Twórca środowisk**.
- Aby eksportować lub importować aplikacje, musisz mieć licencję Power Apps plan 2 lub licencję próbną Power Apps Plan 2.

## <a name="integration-with-office-365-power-automate"></a>Integration with Office 365, Power Automate

Aplikacja **Integracja z Office 365** może być używana do pobierania danych zespołu dla zarejestrowanych użytkowników z Microsoft Office 365. Odwołuje się ona do pracowników w module Human Resources w celu wyodrębnienia typów identyfikacji pracowników. Menedżerowie mogą sprawdzać daty ważności typów identyfikatorów pracowników etatowych. Mogą również wysłać przypomnienie pocztą e-mail, jeśli typ identyfikatora pracownika ma wygasnąć. Aparat Power Automate integruje się z platformą Power Apps w celu wysłania tego przypomnienia. Po wysłaniu przypomnienia potwierdzenie zostanie wysłane z powrotem do rozwiązania Power Apps z rozwiązania Power Automate. Typy identyfikacji to między innymi prawo jazdy, paszport i inne akceptowane formy identyfikatorów.

Tę aplikację można rozszerzyć dla innych scenariuszy. Na przykład może ona służyć do wyświetlania informacji dotyczących urlopu zespołu, zdarzeń kalendarza i zdarzeń specyficznych dla zespołu.

Aby pobrać aplikację **Integration with Office 365, Power Automate**, przejdź do sekcji [Integracja z programem Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) w Centrum pobierania Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate — połączenie SQL i wykonywanie

**Power Automate — połączenie SQL i wykonywanie** łączy się z Microsoft SQL Server i umożliwia uruchamianie kwerend przez SQL.

Chociaż ten szablon odczytuje i aktualizuje tabele SQL, można go rozszerzać i wykorzystywać w innych scenariuszach. Na przykład może on służyć do wypełnienia tabeli tymczasowej w usłudze Common Data Service rekordami z programu SQL Server i do okresowego synchronizowania tabeli tymczasowej przy użyciu wypychania przyrostowego z programu SQL Server.

Narzędzie Zapytanie zaawansowane jest zintegrowane z usługą Flow w celu umożliwienia przekształcania danych i wypychania przyrostowego.

Aby pobrać **Power Automate — połączenie SQL i wykonywanie**, przejdź do sekcji [Power Automate — połączenie SQL i wykonywanie](https://go.microsoft.com/fwlink/?linkid=2081789) w centrum pobierania Microsoft.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Migracja aplikacji między dzierżawcami i środowiskami](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
