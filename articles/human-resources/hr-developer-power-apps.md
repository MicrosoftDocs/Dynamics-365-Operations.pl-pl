---
title: Rozszerz aplikację Talent o usługi Power Apps i Power Automate
description: W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Human Resources używanych przez Microsoft Power Apps i Microsoft Power Automate.
author: negudava
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4036378ca70089a9978a9bf5fb48c058a2064cdc
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689502"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Rozszerzanie o usługi Power Apps i Power Automate


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Human Resources używanych przez Microsoft Power Apps i Microsoft Power Automate. Można zaimportować pakiet rozwiązań skojarzony z każdym przykładem do środowiska Power Apps. Następnie można używać pakietów jako pomocy lub punktów początkowych do implementacji scenariuszy odpowiednich dla Twojej organizacji.

> [!IMPORTANT]
> Jeśli chcesz korzystać z szablonów i aplikacji, które zostały opisane w tym temacie „tak jak są”, sprawdź je, aby upewnić się, że będą one obejmować wszystkie scenariusze, które są specyficzne dla danej implementacji.

## <a name="prerequisites"></a>Wymagania wstępne

- Aby zaimportować pakiety, użytkownicy muszą mieć uprawnienie **Twórca środowisk**.
- Aby eksportować lub importować aplikacje, musisz mieć licencję Power Apps plan 2 lub licencję próbną Power Apps Plan 2.

## <a name="integration-with-microsoft-365-power-automate"></a>Integration with Microsoft 365, Power Automate

Aplikacja **Integracja z Microsoft 365** może być używana do pobierania danych zespołu dla zarejestrowanych użytkowników z Microsoft 365. Odwołuje się ona do pracowników w module Human Resources w celu wyodrębnienia typów identyfikacji pracowników. Menedżerowie mogą sprawdzać daty ważności typów identyfikatorów pracowników etatowych. Mogą również wysłać przypomnienie pocztą e-mail, jeśli typ identyfikatora pracownika ma wygasnąć. Aparat Power Automate integruje się z platformą Power Apps w celu wysłania tego przypomnienia. Po wysłaniu przypomnienia potwierdzenie zostanie wysłane z powrotem do rozwiązania Power Apps z rozwiązania Power Automate. Typy identyfikacji to między innymi prawo jazdy, paszport i inne akceptowane formy identyfikatorów.

Tę aplikację można rozszerzyć dla innych scenariuszy. Na przykład może ona służyć do wyświetlania informacji dotyczących urlopu zespołu, zdarzeń kalendarza i zdarzeń specyficznych dla zespołu.

Aby pobrać aplikację **Integration with Microsoft 365, Power Automate**, przejdź do sekcji [Integracja z programem Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) w Centrum pobierania Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate — połączenie SQL i wykonywanie

**Power Automate — połączenie SQL i wykonywanie** łączy się z Microsoft SQL Server i umożliwia uruchamianie kwerend przez SQL.

Chociaż ten szablon odczytuje i aktualizuje tabele SQL, można go rozszerzać i wykorzystywać w innych scenariuszach. Na przykład może on służyć do wypełnienia tabeli tymczasowej w usłudze Dataverse rekordami z programu SQL Server i do okresowego synchronizowania tabeli tymczasowej przy użyciu wypychania przyrostowego z programu SQL Server.

Narzędzie Zapytanie zaawansowane jest zintegrowane z usługą Flow w celu umożliwienia przekształcania danych i wypychania przyrostowego.

Aby pobrać **Power Automate — połączenie SQL i wykonywanie**, przejdź do sekcji [Power Automate — połączenie SQL i wykonywanie](https://go.microsoft.com/fwlink/?linkid=2081789) w centrum pobierania Microsoft.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Microsoft Power Platform](/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
