--- 
title: "Konfigurowanie opłat za usługi dodatkowe centrum i danych głównych usług dodatkowych"
description: "W tej procedurze pokazano sposób tworzenia danych głównych usług dodatkowych dla centrum oraz użycia tych danych do utworzenie opłaty za usługi dodatkowe centrum."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6d09e32c9e2c41c49e376320d507593849f68cb0
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="040ab-103">Konfigurowanie opłat za usługi dodatkowe centrum i danych głównych usług dodatkowych</span><span class="sxs-lookup"><span data-stu-id="040ab-103">Set up hub accessorial charges and accessorial masters</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="040ab-104">W tej procedurze pokazano sposób tworzenia danych głównych usług dodatkowych dla centrum oraz użycia tych danych do utworzenie opłaty za usługi dodatkowe centrum.</span><span class="sxs-lookup"><span data-stu-id="040ab-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="040ab-105">Procedura wykorzystuje zestaw danych firmy USMF.</span><span class="sxs-lookup"><span data-stu-id="040ab-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="040ab-106">Konfiguracji zazwyczaj dokonuje koordynator transportu.</span><span class="sxs-lookup"><span data-stu-id="040ab-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="040ab-107">Ustawianie głównego centrum</span><span class="sxs-lookup"><span data-stu-id="040ab-107">Set up a hub master</span></span>
1. <span data-ttu-id="040ab-108">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Główne usługi dodatkowe.</span><span class="sxs-lookup"><span data-stu-id="040ab-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="040ab-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="040ab-109">Click New.</span></span>
3. <span data-ttu-id="040ab-110">W polu Główne dodatkowe usługi wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="040ab-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="040ab-111">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="040ab-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="040ab-112">W polu Typ dodatkowych usług wybierz opcję „Centrum”.</span><span class="sxs-lookup"><span data-stu-id="040ab-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="040ab-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="040ab-113">Click Save.</span></span>
7. <span data-ttu-id="040ab-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="040ab-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="040ab-115">Konfigurowanie opłaty za usługi dodatkowe centrum</span><span class="sxs-lookup"><span data-stu-id="040ab-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="040ab-116">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Opłaty współpracownika centrum.</span><span class="sxs-lookup"><span data-stu-id="040ab-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="040ab-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="040ab-117">Click New.</span></span>
3. <span data-ttu-id="040ab-118">W polu Identyfikator współpracownika centrum wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="040ab-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="040ab-119">W polu Centrum kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="040ab-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="040ab-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="040ab-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="040ab-121">W polu Pozycja centrum wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="040ab-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="040ab-122">Opłatę można utworzyć za odbiór lub dostawę.</span><span class="sxs-lookup"><span data-stu-id="040ab-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="040ab-123">W zależności od wybranej opcji opłata będzie stosowana do odpowiedniego segmentu transportu na trasie.</span><span class="sxs-lookup"><span data-stu-id="040ab-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="040ab-124">W polu Główne dodatkowe usługi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="040ab-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="040ab-125">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="040ab-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="040ab-126">Wybierz utworzone właśnie dane główne.</span><span class="sxs-lookup"><span data-stu-id="040ab-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="040ab-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="040ab-127">Click Save.</span></span>
10. <span data-ttu-id="040ab-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="040ab-128">Close the page.</span></span>


