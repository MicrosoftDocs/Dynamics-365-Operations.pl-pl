---
title: Wyłącz reguły w sprawdzaniu spójności transakcji sprzedaży detalicznej
description: W tym temacie opisano funkcje wyłączania reguł sprawdzania spójności transakcji sprzedaży detalicznej wprowadzone w rozwiązaniu Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586304"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="588c4-103">Wyłącz reguły w sprawdzaniu spójności transakcji sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="588c4-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="588c4-104">Sieci handlowe mogą mieć unikatowe dla nich scenariusze i procesy biznesowe.</span><span class="sxs-lookup"><span data-stu-id="588c4-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="588c4-105">Z tego względu nie wszystkie domyślnie zainstalowane w sprawdzaniu spójności transakcji sprzedaży detalicznej reguły są dostępne dla wszystkich sieci handlowych.</span><span class="sxs-lookup"><span data-stu-id="588c4-105">Therefore, not all the rules that are included by default in the retail transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="588c4-106">W celu uwzględnienia różnic rozwiązanie Microsoft Dynamics 365 Retail oferuje funkcje, których można użyć do wyłączenia nie mających zastosowania reguł.</span><span class="sxs-lookup"><span data-stu-id="588c4-106">To accommodate differences, Microsoft Dynamics 365 Retail provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="588c4-107">Aby wyświetlić listę reguł dostępnych w sprawdzaniu spójności transakcji sprzedaży detalicznej w swoim środowisku i zobaczyć stan każdej reguły, przejdź do **Handel detaliczny \> Ustawienia centrali \> Parametry \> Parametry sieci sprzedaży** i wybierz kartę **Weryfikacja transakcji**.</span><span class="sxs-lookup"><span data-stu-id="588c4-107">To view the list of rules that are available in the retail transaction consistency checker in your environment, and to see the status of each rule, go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="588c4-108">Domyślnie stan każdej reguły jest ustawiony na **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="588c4-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="588c4-109">Z tego względu wszystkie reguły są używane do weryfikacji transakcji sprzedaży detalicznej przed pobraniem ich do zestawień.</span><span class="sxs-lookup"><span data-stu-id="588c4-109">Therefore, all the rules are used to validate retail transactions before they are pulled into the retail statements.</span></span> <span data-ttu-id="588c4-110">Aby wyłączyć regułę, zmień jej stan na **Wyłączone**.</span><span class="sxs-lookup"><span data-stu-id="588c4-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="588c4-111">Wyłączone reguły nie są brane pod uwagę, gdy transakcje sprzedaży detalicznej są weryfikowane w trakcie procesu obliczania zestawień.</span><span class="sxs-lookup"><span data-stu-id="588c4-111">Disabled rules aren't considered when retail transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="588c4-112">Aby pominąć cały proces weryfikacji bez względu na włączone reguły, przejdź do **Handel detaliczny \> Ustawienia centrali \> Parametry \> Parametry sieci sprzedaży**, a następnie w karcie **Weryfikacja transakcji** ustaw opcję **Wyłącz sprawdzanie spójności transakcji sieci sprzedaży** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="588c4-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Retail transactions** option to **Yes**.</span></span> <span data-ttu-id="588c4-113">Po ustawieniu tej opcji na **Nie** nie można ponownie ustawić jej na **Tak** w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="588c4-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>
