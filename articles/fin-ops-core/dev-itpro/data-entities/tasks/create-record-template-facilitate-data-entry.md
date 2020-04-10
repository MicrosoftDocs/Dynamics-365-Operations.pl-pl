---
title: Tworzenie szablonu rekordu w celu ułatwienia wprowadzania danych
description: Ten temat przedstawia sposób tworzenia szablonu rekordu, tak aby wartości pól, które są często używane, nie musiały być jawnie wprowadzane dla każdego nowego rekordu.
author: margoc
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec21415158ad611d0ad55778e76aa128f53561bd
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143391"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="71f68-103">Tworzenie szablonu rekordu w celu ułatwienia wprowadzania danych</span><span class="sxs-lookup"><span data-stu-id="71f68-103">Create a record template to facilitate data entry</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71f68-104">Ten temat przedstawia sposób tworzenia szablonu rekordu, tak aby wartości pól, które są często używane, nie musiały być jawnie wprowadzane dla każdego nowego rekordu.</span><span class="sxs-lookup"><span data-stu-id="71f68-104">This topic demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="71f68-105">W tej procedurze zostanie utworzy nowy rekord dla nowych laptopów, które należy dodać do środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="71f68-105">In this procedure, you'll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="71f68-106">Procedura wykorzystuje przykładową firmę USMF.</span><span class="sxs-lookup"><span data-stu-id="71f68-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="71f68-107">W okienku nawigacji przejdź do **Moduły > Środki trwałe > Środki trwałe > Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="71f68-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="71f68-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="71f68-108">Select **New**.</span></span>
3. <span data-ttu-id="71f68-109">W polu **Grupa środków trwałych** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="71f68-109">In the **Fixed asset group** field, enter or select a value.</span></span>
4. <span data-ttu-id="71f68-110">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="71f68-110">In the **Name** field, type a value.</span></span> <span data-ttu-id="71f68-111">Na przykład wpisz **Laptop dyrektora w firmie**.</span><span class="sxs-lookup"><span data-stu-id="71f68-111">For example, enter **Corporate lead laptop**.</span></span>  
5. <span data-ttu-id="71f68-112">W polu **Wyszukaj nazwę** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="71f68-112">In the **Search name** field, type a value.</span></span> <span data-ttu-id="71f68-113">Na przykład wpisz **laptop**.</span><span class="sxs-lookup"><span data-stu-id="71f68-113">For example, enter **laptop**.</span></span>  
6. <span data-ttu-id="71f68-114">Rozwiń sekcję **Informacje techniczne** .</span><span class="sxs-lookup"><span data-stu-id="71f68-114">Expand the **Technical information** section.</span></span>
7. <span data-ttu-id="71f68-115">W polach **Marka**, **Model** i **Rok modelu** wpisz wartości.</span><span class="sxs-lookup"><span data-stu-id="71f68-115">In the **Make**, **Model**, and **Model year** fields, type values.</span></span>
8. <span data-ttu-id="71f68-116">W okienku akcji kliknij pozycję **Opcje**.</span><span class="sxs-lookup"><span data-stu-id="71f68-116">On the Action Pane, select **Options**.</span></span>
9. <span data-ttu-id="71f68-117">Wybierz **Informacje o rekordzie**.</span><span class="sxs-lookup"><span data-stu-id="71f68-117">Select **Record info**.</span></span>
10. <span data-ttu-id="71f68-118">Wybierz **Szablon użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="71f68-118">Select **User template**.</span></span>
11. <span data-ttu-id="71f68-119">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="71f68-119">In the **Name** field, type a value.</span></span>
12. <span data-ttu-id="71f68-120">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="71f68-120">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="71f68-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="71f68-121">Select **OK**.</span></span>
14. <span data-ttu-id="71f68-122">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="71f68-122">Select **Close**.</span></span>

