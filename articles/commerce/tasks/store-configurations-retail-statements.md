---
title: Konfiguracje sklepu dla zestawień sieci sprzedaży
description: Ta procedura prowadzi przez konfiguracje sprzedaży sklepu sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień Commerce.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e255c58997ed1c0ad5614b15867f14714a8bcfc8
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2020
ms.locfileid: "4415094"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="bf26b-103">Konfiguracje sklepu dla zestawień sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="bf26b-103">Store configurations for Retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf26b-104">Ta procedura prowadzi przez konfiguracje sprzedaży sklepu sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień Commerce.</span><span class="sxs-lookup"><span data-stu-id="bf26b-104">This procedure walks through configurations for the store that affect how Commerce statements get created and posted.</span></span> <span data-ttu-id="bf26b-105">Wymiary finansowe w sklepach są omówione w innej procedurze.</span><span class="sxs-lookup"><span data-stu-id="bf26b-105">Financial dimensions on stores are covered in another procedure.</span></span> <span data-ttu-id="bf26b-106">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="bf26b-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="bf26b-107">W **okienku nawigacji** kliknij kolejno opcje **Moduły > Retail i Commerce > Kanały > Sklepy > Wszystkie sklepy**.</span><span class="sxs-lookup"><span data-stu-id="bf26b-107">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
2. <span data-ttu-id="bf26b-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="bf26b-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="bf26b-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="bf26b-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bf26b-110">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="bf26b-110">Click **Edit**.</span></span>
5. <span data-ttu-id="bf26b-111">Ustawienia w skróconej karcie **Zestawienie/zamknięcie** wpływają na tworzenie, sprawdzanie poprawności i księgowanie zestawień dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="bf26b-111">The settings in the **Statement/closing** FastTab affect the statement creation, validation, and posting for the store.</span></span> <span data-ttu-id="bf26b-112">Rozwiń skróconą kartę **Zestawienie/zamknięcie**.</span><span class="sxs-lookup"><span data-stu-id="bf26b-112">Expand the **Statement/closing** FastTab.</span></span>  
6. <span data-ttu-id="bf26b-113">W polu **Metoda zestawienia** wybierz metodę, której chcesz używać do grupowania wierszy zestawienia.</span><span class="sxs-lookup"><span data-stu-id="bf26b-113">In the **Statement method** field, select the method you want to use to group the statement lines by.</span></span>  
7. <span data-ttu-id="bf26b-114">Wybierz opcję „Tak” w **Jedno zestawienie na dzień**, jeśli ma być tworzone tylko jedno zestawienie dziennie podczas wykonywania zadania wsadowego tworzenia zestawień.</span><span class="sxs-lookup"><span data-stu-id="bf26b-114">Select "Yes" in **One statement per day** if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
8. <span data-ttu-id="bf26b-115">Pole **Obliczenia deklaracji środków płatniczych** określa, czy deklaracje środków płatniczych powinny być dodawane razem czy też ma być używana ostatnia deklaracja.</span><span class="sxs-lookup"><span data-stu-id="bf26b-115">The **Tender declaration calculation** field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
9. <span data-ttu-id="bf26b-116">W polu **Zaokrąglanie** wybierz konto księgowe do księgowania różnic zaokrągleń.</span><span class="sxs-lookup"><span data-stu-id="bf26b-116">In the **Rounding** field, select the ledger account to post rounding differences into.</span></span>  
10. <span data-ttu-id="bf26b-117">W polu **Maksymalna różnica zaokrągleń** można wprowadzić maksymalną dozwoloną różnicę zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="bf26b-117">In the **Maximum rounding difference** field, enter the maximum rounding difference allowed.</span></span>
11. <span data-ttu-id="bf26b-118">W polu **Księgowanie** można wprowadzić maksymalną łączną rozbieżność księgowania dozwoloną dla zestawienia.</span><span class="sxs-lookup"><span data-stu-id="bf26b-118">In the **Posting** field, enter the maximum total posting difference allowed for a statement.</span></span>
12. <span data-ttu-id="bf26b-119">W polu **Zmiana** można wprowadzić maksymalną łączną rozbieżność dozwoloną w granicach zmiany w zestawieniu.</span><span class="sxs-lookup"><span data-stu-id="bf26b-119">In the **Shift** field, enter the maximum total difference within a shift in a statement.</span></span>  
13. <span data-ttu-id="bf26b-120">W polu **Transakcja** można wprowadzić maksymalną łączną rozbieżność dozwoloną w wierszu zestawienia.</span><span class="sxs-lookup"><span data-stu-id="bf26b-120">In the **Transaction** field, enter the maximum total difference in a statement line.</span></span>  
14. <span data-ttu-id="bf26b-121">W polu **Metoda zamknięcia** można określić, czy transakcje, które zostaną uwzględnione w zestawieniu, powinny być częścią zamkniętej zmiany czy też mogą być dowolnymi transakcjami o zdefiniowanym zakresie daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="bf26b-121">In the **Closing method** field, define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
15. <span data-ttu-id="bf26b-122">W polu **Koniec dnia roboczego** można wprowadzić godzinę, jeśli transakcje zachodzące po północy mają być księgowane w poprzednim dniu.</span><span class="sxs-lookup"><span data-stu-id="bf26b-122">In the **End of business day** field, enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
16. <span data-ttu-id="bf26b-123">Wybierz opcję „Tak” w **Księguj z dniem roboczym**, jeśli transakcje zachodzące po północy mają być księgowane jako część poprzedniego dnia.</span><span class="sxs-lookup"><span data-stu-id="bf26b-123">Select "Yes" in **Post as business day** if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
17. <span data-ttu-id="bf26b-124">Wybierz opcję „Tak” w **Podziel wg metody zestawienia** , aby zestawienia były tworzone dla każdej zdefiniowanej metody wykonywania zestawień.</span><span class="sxs-lookup"><span data-stu-id="bf26b-124">Select "Yes" in **Split by Statement method** to get statements created for each statement method defined.</span></span> <span data-ttu-id="bf26b-125">To działanie może być przydatne, jeśli wydajność księgowania wymaga poprawy dla sklepów o dużym wolumenie transakcji, ponieważ spowoduje to utworzenie wielu mniejszych zestawień, które mogą być przetwarzane jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="bf26b-125">This action can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
18. <span data-ttu-id="bf26b-126">Na karcie skróconej **Ogólne** w polu **Domyślny odbiorca** można wybrać konto odbiorcy na potrzeby sprzedaży klientom przypadkowym.</span><span class="sxs-lookup"><span data-stu-id="bf26b-126">In the **General** FastTab, in the **Default customer** field, you can select the customer account to use for sales to walk-in customers.</span></span>  

