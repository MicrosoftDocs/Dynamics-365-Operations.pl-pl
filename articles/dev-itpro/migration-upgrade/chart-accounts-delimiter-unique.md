---
title: Ustawianie unikatowości ogranicznika planu kont
description: W Dynamics 365 for Finance and Operations nie można mieć tego samego separatora dla planu kont i wartości wymiarów. Po uaktualnieniu należy zmienić wartości separatora.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: e197a1b44e038a97b8bf6db692dcc2eef2bc5f7b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "335860"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="13c8e-104">Ustawianie unikatowości ogranicznika planu kont</span><span class="sxs-lookup"><span data-stu-id="13c8e-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13c8e-105">W Microsoft Dynamics AX 2012 można używać tego samego separatora dla planu kont i wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="13c8e-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="13c8e-106">W Dynamics 365 for Finance and Operations nie można mieć tego samego separatora dla planu kont i wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="13c8e-106">In Dynamics 365 for Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="13c8e-107">W razie istnienia zduplikowanych separatorów można je zmienić po uaktualnieniu.</span><span class="sxs-lookup"><span data-stu-id="13c8e-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="13c8e-108">Funkcja jest dostępna w następujących programach:</span><span class="sxs-lookup"><span data-stu-id="13c8e-108">This feature is available in:</span></span>
- <span data-ttu-id="13c8e-109">Dynamics 365 for Finance and Operations wersja 8.0</span><span class="sxs-lookup"><span data-stu-id="13c8e-109">Dynamics 365 for Finance and Operations version 8.0</span></span>
- <span data-ttu-id="13c8e-110">Dynamics 365 for Finance and Operations wersja 7.1 z poprawką KB 4094701 Nie można wprowadzić wymiarów finansowych, jeśli wartości wymiarów zawierają separator planu kont</span><span class="sxs-lookup"><span data-stu-id="13c8e-110">Dynamics 365 for Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="13c8e-111">Dynamics 365 for Finance and Operations wersja 7.2 z poprawką KB 4092967 Nie można wybrać podprojektu jako wymiaru, jeśli format podprojektu zawiera separator wymiaru</span><span class="sxs-lookup"><span data-stu-id="13c8e-111">Dynamics 365 for Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="13c8e-112">Aktualizacja separatora</span><span class="sxs-lookup"><span data-stu-id="13c8e-112">Update delimiter</span></span>
<span data-ttu-id="13c8e-113">Jeśli występuje konflikt z planem kont, można zmienić separator planu kont i format identyfikatora projektu/podprojektu.</span><span class="sxs-lookup"><span data-stu-id="13c8e-113">If there is a conflict with the Chart of Accounts, the Chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="13c8e-114">Nie można zmieniać żadnych innych separatorów wymiarów.</span><span class="sxs-lookup"><span data-stu-id="13c8e-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="13c8e-115">Separator planu kont można zmienić po uaktualnieniu do programu Finance and Operations w ustawieniu **Parametry księgi głównej** > **Plan kont i wymiary** > **Zmień ogranicznik**.</span><span class="sxs-lookup"><span data-stu-id="13c8e-115">You can change the chart of accounts delimiter after upgrade to Finance and Operations in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="13c8e-116">Jeśli jedyny konflikt występuje z formatem identyfikatora projektu/podprojektu, można zmienić tę wartość w ustawieniu **Parametry modułu Zarządzanie projektami i ich księgowanie** > **Ogólne** > **Modyfikuj format podprojektu**.</span><span class="sxs-lookup"><span data-stu-id="13c8e-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="13c8e-117">Jak ustalić, czy środowisko wymaga aktualizacji separatorów</span><span class="sxs-lookup"><span data-stu-id="13c8e-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="13c8e-118">Jeśli separatory w uaktualnionym środowisku powodują konflikt, może występować niestabilność podczas wprowadzania wartości w formancie wpisu podzielonego na segmenty lub formacie wprowadzania wymiarów.</span><span class="sxs-lookup"><span data-stu-id="13c8e-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="13c8e-119">Oznacza to, że trzeba będzie zawsze używać wyszukiwań lub wysuwanych menu podczas wprowadzania kombinacji wymiarów i kont.</span><span class="sxs-lookup"><span data-stu-id="13c8e-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>
