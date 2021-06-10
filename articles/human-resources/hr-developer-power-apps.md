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
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5b1ebe17063d954b52a0607d39e3ea08518adb89
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057605"
---
# <a name="extend-with-power-apps-and-power-automate"></a><span data-ttu-id="ac572-103">Rozszerzanie o usługi Power Apps i Power Automate</span><span class="sxs-lookup"><span data-stu-id="ac572-103">Extend with Power Apps and Power Automate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="ac572-104">W tym artykule opisano przykładowe scenariusze rozszerzeń programu Microsoft Dynamics 365 Human Resources używanych przez Microsoft Power Apps i Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ac572-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Human Resources that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="ac572-105">Można zaimportować pakiet rozwiązań skojarzony z każdym przykładem do środowiska Power Apps.</span><span class="sxs-lookup"><span data-stu-id="ac572-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="ac572-106">Następnie można używać pakietów jako pomocy lub punktów początkowych do implementacji scenariuszy odpowiednich dla Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="ac572-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac572-107">Jeśli chcesz korzystać z szablonów i aplikacji, które zostały opisane w tym temacie „tak jak są”, sprawdź je, aby upewnić się, że będą one obejmować wszystkie scenariusze, które są specyficzne dla danej implementacji.</span><span class="sxs-lookup"><span data-stu-id="ac572-107">If you want to use the templates and apps that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac572-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ac572-108">Prerequisites</span></span>

- <span data-ttu-id="ac572-109">Aby zaimportować pakiety, użytkownicy muszą mieć uprawnienie **Twórca środowisk**.</span><span class="sxs-lookup"><span data-stu-id="ac572-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="ac572-110">Aby eksportować lub importować aplikacje, musisz mieć licencję Power Apps plan 2 lub licencję próbną Power Apps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="ac572-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="integration-with-microsoft-365-power-automate"></a><span data-ttu-id="ac572-111">Integracja z Microsoft 365, Power Automate</span><span class="sxs-lookup"><span data-stu-id="ac572-111">Integration with Microsoft 365, Power Automate</span></span>

<span data-ttu-id="ac572-112">Aplikacja **Integracja z Microsoft 365** może być używana do pobierania danych zespołu dla zarejestrowanych użytkowników z Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac572-112">The **Integration with Microsoft 365** app can be used to extract team information for signed-in users from Microsoft 365.</span></span> <span data-ttu-id="ac572-113">Odwołuje się ona do pracowników w module Human Resources w celu wyodrębnienia typów identyfikacji pracowników.</span><span class="sxs-lookup"><span data-stu-id="ac572-113">It references workers in Human Resources to extract employee identification types.</span></span> <span data-ttu-id="ac572-114">Menedżerowie mogą sprawdzać daty ważności typów identyfikatorów pracowników etatowych.</span><span class="sxs-lookup"><span data-stu-id="ac572-114">Managers can check expiration dates of employee ID types.</span></span> <span data-ttu-id="ac572-115">Mogą również wysłać przypomnienie pocztą e-mail, jeśli typ identyfikatora pracownika ma wygasnąć.</span><span class="sxs-lookup"><span data-stu-id="ac572-115">They can also send an email reminder if the employee ID type is expiring.</span></span> <span data-ttu-id="ac572-116">Aparat Power Automate integruje się z platformą Power Apps w celu wysłania tego przypomnienia.</span><span class="sxs-lookup"><span data-stu-id="ac572-116">Power Automate integrates with Power Apps to send this reminder.</span></span> <span data-ttu-id="ac572-117">Po wysłaniu przypomnienia potwierdzenie zostanie wysłane z powrotem do rozwiązania Power Apps z rozwiązania Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ac572-117">Confirmation will be sent back to Power Apps from Power Automate when the reminder is sent.</span></span> <span data-ttu-id="ac572-118">Typy identyfikacji to między innymi prawo jazdy, paszport i inne akceptowane formy identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="ac572-118">Identification types include driver's license, passport, and other acceptable forms of ID.</span></span>

<span data-ttu-id="ac572-119">Tę aplikację można rozszerzyć dla innych scenariuszy.</span><span class="sxs-lookup"><span data-stu-id="ac572-119">You can extend this app for other scenarios.</span></span> <span data-ttu-id="ac572-120">Na przykład może ona służyć do wyświetlania informacji dotyczących urlopu zespołu, zdarzeń kalendarza i zdarzeń specyficznych dla zespołu.</span><span class="sxs-lookup"><span data-stu-id="ac572-120">For example, you can use it to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="ac572-121">Aby pobrać aplikację **Integracja z Microsoft 365, Power Automate**, przejdź do [Integracja z Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) w Centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac572-121">To download the **Integration with Microsoft 365, Power Automate** app, go to [Integration with Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="ac572-122">Power Automate — połączenie SQL i wykonywanie</span><span class="sxs-lookup"><span data-stu-id="ac572-122">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="ac572-123">**Power Automate — połączenie SQL i wykonywanie** łączy się z Microsoft SQL Server i umożliwia uruchamianie kwerend przez SQL.</span><span class="sxs-lookup"><span data-stu-id="ac572-123">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="ac572-124">Chociaż ten szablon odczytuje i aktualizuje tabele SQL, można go rozszerzać i wykorzystywać w innych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="ac572-124">Although this template reads and updates SQL tables, you can extend it and use it for other scenarios.</span></span> <span data-ttu-id="ac572-125">Na przykład może on służyć do wypełnienia tabeli tymczasowej w usłudze Dataverse rekordami z programu SQL Server i do okresowego synchronizowania tabeli tymczasowej przy użyciu wypychania przyrostowego z programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac572-125">For example, you can use it to fill a staging table in Dataverse with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="ac572-126">Narzędzie Zapytanie zaawansowane jest zintegrowane z usługą Flow w celu umożliwienia przekształcania danych i wypychania przyrostowego.</span><span class="sxs-lookup"><span data-stu-id="ac572-126">Advanced Query is integrated with Flow to enable Data transformation and incremental push.</span></span>

<span data-ttu-id="ac572-127">Aby pobrać **Power Automate — połączenie SQL i wykonywanie**, przejdź do sekcji [Power Automate — połączenie SQL i wykonywanie](https://go.microsoft.com/fwlink/?linkid=2081789) w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac572-127">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac572-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ac572-128">Additional resources</span></span>

[<span data-ttu-id="ac572-129">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="ac572-129">The Microsoft Power Platform</span></span>](/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]