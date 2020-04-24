---
title: Integracja umów serwisowych i projektów
description: Podczas pracy z wierszami umów serwisowych i umowami serwisowymi wykorzystywane są dane ustawiane w obszarach modułu Zarządzanie projektami i ich księgowanie.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a19a138cceb7db08216e1151eb92442691bc58d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202337"
---
# <a name="integration-for-service-agreements-and-projects"></a><span data-ttu-id="b208b-103">Integracja umów serwisowych i projektów</span><span class="sxs-lookup"><span data-stu-id="b208b-103">Integration for service agreements and projects</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b208b-104">Podczas pracy z wierszami umów serwisowych i umowami serwisowymi wykorzystywane są dane ustawiane w następujących obszarach modułu **Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="b208b-104">When you work with service agreements and service agreement lines, you use data that is set up in the following areas in **Project management and accounting**.</span></span>

## <a name="project-prices"></a><span data-ttu-id="b208b-105">Ceny projektu</span><span class="sxs-lookup"><span data-stu-id="b208b-105">Project prices</span></span>

<span data-ttu-id="b208b-106">Koszt własny i cena sprzedaży związane z transakcją umowy serwisowej pochodzą z konfiguracji kosztu własnego, która dotyczy projektu związanego z umową serwisową.</span><span class="sxs-lookup"><span data-stu-id="b208b-106">The cost and the sales price for a service agreement transaction are derived from the cost price setup that applies to the project that is attached to the service agreement.</span></span> <span data-ttu-id="b208b-107">Koszt własny i cena sprzedaży mogą być ustawiane dla kategorii, projektów i pracowników.</span><span class="sxs-lookup"><span data-stu-id="b208b-107">Cost and sales prices can be set up by project, employee, and category.</span></span> 

## <a name="project-validation"></a><span data-ttu-id="b208b-108">Weryfikacja projektu</span><span class="sxs-lookup"><span data-stu-id="b208b-108">Project validation</span></span>

<span data-ttu-id="b208b-109">Projekty, pracownicy i kategorie dostępne do wyboru w wierszu umowy serwisowej można ograniczać za pomocą konfiguracji sprawdzania poprawności w module **Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="b208b-109">The projects, employees, and categories that are available for selection on a service agreement line can be limited by the validation setup in **Project management and accounting**.</span></span> <span data-ttu-id="b208b-110">Konfiguracja sprawdzania poprawności umożliwia łączenie pracowników, projektów i kategorii na potrzeby kontroli dostępu.</span><span class="sxs-lookup"><span data-stu-id="b208b-110">By using the validation setup, you can combine employees, projects, and categories for control access.</span></span> 

## <a name="project-line-properties"></a><span data-ttu-id="b208b-111">Właściwości wiersza projektu</span><span class="sxs-lookup"><span data-stu-id="b208b-111">Project line properties</span></span>

<span data-ttu-id="b208b-112">Właściwość wiersza umowy serwisowej jest wprowadzana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="b208b-112">A line property is entered automatically for a service agreement line.</span></span>

<span data-ttu-id="b208b-113">Właściwości wierszy są tworzone w formularzu **Właściwości wiersza** w module **Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="b208b-113">Line properties are created in the **Line properties** form in **Project management and accounting**.</span></span> <span data-ttu-id="b208b-114">Właściwość wiersza wprowadzona w umowie serwisowej jest związana z projektem wybranym dla umowy serwisowej, a później dziedziczona przez wiersz umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="b208b-114">The line property that is entered on a service agreement is attached to the project that is selected for the service agreement and inherited subsequently by the service agreement line.</span></span> 

## <a name="default-offset-accounts"></a><span data-ttu-id="b208b-115">Domyślne konta przeciwstawne</span><span class="sxs-lookup"><span data-stu-id="b208b-115">Default offset accounts</span></span>

<span data-ttu-id="b208b-116">Podczas wprowadzania transakcji wydatku automatycznie jest dla niej wybierane domyślne konto przeciwstawne wydatku.</span><span class="sxs-lookup"><span data-stu-id="b208b-116">If you enter an expense transaction, a default expense offset account is selected automatically for the transaction.</span></span> <span data-ttu-id="b208b-117">Domyślne konto wydatku jest konfigurowane dla projektu związanego z bieżącą umową serwisową.</span><span class="sxs-lookup"><span data-stu-id="b208b-117">The default expense account is set up for the project that is attached to the current service agreement.</span></span>

## <a name="project-categories"></a><span data-ttu-id="b208b-118">Kategorie projektu</span><span class="sxs-lookup"><span data-stu-id="b208b-118">Project categories</span></span>

<span data-ttu-id="b208b-119">Kategorie dostępne dla wierszy umowy serwisowej są ustawiane w formularzu **Kategorie projektu** w module **Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="b208b-119">The categories that are available for service agreement lines are set up in the **Project categories** form in **Project management and accounting**.</span></span> 

> [!NOTE]
> <P><span data-ttu-id="b208b-120">Kategorie, które mają zaznaczone pole wyboru <STRONG>Aktywne w arkuszach</STRONG> na karcie <STRONG>Projekt</STRONG> w formularzu <STRONG>Kategorie projektu</STRONG>, są dostępne do wyboru.</span><span class="sxs-lookup"><span data-stu-id="b208b-120">Categories that have the <STRONG>Active in journals</STRONG> check box selected on the <STRONG>Project</STRONG> tab in the <STRONG>Project categories</STRONG> form are available for selection.</span></span> <span data-ttu-id="b208b-121">Jednak jeśli pole wyboru <STRONG>Nieaktywne kategorie</STRONG> jest zaznaczone na karcie <STRONG>Arkusze</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie projektami i ich księgowanie</STRONG>, wszystkie kategorie są dostępne do wyboru.</span><span class="sxs-lookup"><span data-stu-id="b208b-121">However, if the <STRONG>Inactive categories</STRONG> check box is selected on the <STRONG>Journals</STRONG> tab in the <STRONG>Project management and accounting parameters</STRONG> form, all categories are available for selection.</span></span></P>

## <a name="project-parameters"></a><span data-ttu-id="b208b-122">Parametry projektu</span><span class="sxs-lookup"><span data-stu-id="b208b-122">Project parameters</span></span>

<span data-ttu-id="b208b-123">Jeśli jest zaznaczone pole wyboru **Zwolnieni pracownicy** na karcie **Arkusze** w formularzu **Parametry modułu Zarządzanie projektami i ich księgowanie**, można wybierać nieaktywnych pracowników i aktywnych pracowników w formularzach **Umowy serwisowe** i **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="b208b-123">If the **Terminated workers** field on the **Journals** tab in the **Project management and accounting parameters** form is selected, you can select inactive employees and active employees in the **Service agreements** and **Service orders** forms.</span></span>

<span data-ttu-id="b208b-124">Ponadto można włączyć pola **Godzina rozpoczęcia** i **Godzina zakończenia** na karcie **Projekt** w formularzu **Zlecenia serwisowe**, aby wprowadzić godziny rozpoczęcia i zakończenia w wierszach zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="b208b-124">Also, you can enable the **Start time** and **End time** fields on the **Project** tab in the **Service orders** form to enter starting and ending times on service order lines.</span></span>

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a><span data-ttu-id="b208b-125">Włączanie funkcji godzin rozpoczęcia i zakończenia w zleceniach serwisowych</span><span class="sxs-lookup"><span data-stu-id="b208b-125">Enable the starting and ending time feature for service orders</span></span>

1.  <span data-ttu-id="b208b-126">Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="b208b-126">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="b208b-127">Kliknij kartę **Arkusze**, a następnie zaznacz pole wyboru **Pokaż godziny rozpoczęcia/zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="b208b-127">Click the **Journals** tab, and then select the **Show start/end times** check box.</span></span>

3.  <span data-ttu-id="b208b-128">Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Arkusze** \> **Nazwy arkuszy**.</span><span class="sxs-lookup"><span data-stu-id="b208b-128">Click **Project management and accounting** \> **Setup** \> **Journals** \> **Journal names**.</span></span>

4.  <span data-ttu-id="b208b-129">Wybierz nazwę arkusza związanego ze zleceniem serwisowym.</span><span class="sxs-lookup"><span data-stu-id="b208b-129">Select the journal name that is attached to the service order.</span></span>

5.  <span data-ttu-id="b208b-130">Kliknij kartę **Ogólne**, a następnie zaznacz pole wyboru **Pokaż godziny rozpoczęcia/zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="b208b-130">Click the **General** tab, and then select the **Show start/end times** check box.</span></span>


> [!NOTE]
> <P><span data-ttu-id="b208b-131">Wybierz nazwę arkusza dla zlecenia serwisowego w polu <STRONG>Godzina</STRONG> na karcie <STRONG>Arkusze</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b208b-131">Select the journal name for the service order in the <STRONG>Hour</STRONG> field on the <STRONG>Journals</STRONG> tab in the <STRONG>Service management parameters</STRONG> form.</span></span></P>





