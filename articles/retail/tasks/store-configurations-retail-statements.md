--- 
title: "Konfiguracje sklepu dla zestawień sieci sprzedaży"
description: "Ta procedura prowadzi przez konfiguracje sprzedaży sklepu sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 96aff33904c1de4a8b2642890eba7bf854d8e0c1
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="ef974-103">Konfiguracje sklepu dla zestawień sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ef974-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ef974-104">Ta procedura prowadzi przez konfiguracje sprzedaży sklepu sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ef974-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="ef974-105">Wymiary finansowe w sklepach sieci sprzedaży są omówione w innej procedurze.</span><span class="sxs-lookup"><span data-stu-id="ef974-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="ef974-106">Ta procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="ef974-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="ef974-107">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ef974-107">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="ef974-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ef974-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ef974-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ef974-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ef974-110">Ustawienia w sekcji Zestawienie/zamknięcie wpływają na tworzenie, sprawdzanie poprawności i księgowanie zestawień dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="ef974-110">The settings in the Statement/closing section affect the statement creation, validation, and posting for the store.</span></span>  <span data-ttu-id="ef974-111">Otwórz sekcję Zestawienie/zamknięcie.</span><span class="sxs-lookup"><span data-stu-id="ef974-111">Open the Statement/closing section.</span></span>  
    * <span data-ttu-id="ef974-112">Wybierz metodę, której chcesz używać do grupowania wierszy zestawienia.</span><span class="sxs-lookup"><span data-stu-id="ef974-112">Select the method you want to use to group the statement lines by.</span></span>  
    * <span data-ttu-id="ef974-113">Wybierz opcję „Tak”, jeśli ma być tworzone tylko jedno zestawienie dziennie podczas wykonywania zadania wsadowego tworzenia zestawień.</span><span class="sxs-lookup"><span data-stu-id="ef974-113">Select "Yes" if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
    * <span data-ttu-id="ef974-114">Pole Obliczenia deklaracji środków płatniczych określa, czy deklaracje środków płatniczych powinny być dodawane razem czy też ma być używana ostatnia deklaracja.</span><span class="sxs-lookup"><span data-stu-id="ef974-114">The Tender declaration calculation field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
    * <span data-ttu-id="ef974-115">Wybierz konto księgowe do księgowania różnic zaokrągleń.</span><span class="sxs-lookup"><span data-stu-id="ef974-115">Select the ledger account to post rounding differences into.</span></span>  
    * <span data-ttu-id="ef974-116">W polu Maksymalna różnica zaokrągleń można wprowadzić maksymalną dozwoloną różnicę zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="ef974-116">In the Maximum rounding difference field, you can enter the maximum rounding difference allowed.</span></span>  
    * <span data-ttu-id="ef974-117">W polu Księgowanie można wprowadzić maksymalną łączną rozbieżność księgowania dozwoloną dla zestawienia.</span><span class="sxs-lookup"><span data-stu-id="ef974-117">In the Posting field, you can enter the maximum total posting difference allowed for a statement.</span></span>  
    * <span data-ttu-id="ef974-118">W polu Zmiana można wprowadzić maksymalną łączną rozbieżność dozwoloną w granicach zmiany w zestawieniu.</span><span class="sxs-lookup"><span data-stu-id="ef974-118">In the Shift field, you can enter the maximum total difference within a shift in a statement.</span></span>  
    * <span data-ttu-id="ef974-119">W polu Transakcja można wprowadzić maksymalną łączną rozbieżność dozwoloną w wierszu zestawienia.</span><span class="sxs-lookup"><span data-stu-id="ef974-119">In the Transaction field, you can enter the maximum total difference in a statement line.</span></span>  
    * <span data-ttu-id="ef974-120">W polu Metoda zamknięcia można określić, czy transakcje, które zostaną uwzględnione w zestawieniu, powinny być częścią zamkniętej zmiany czy też mogą być dowolnymi transakcjami o zdefiniowanym zakresie daty/godziny.</span><span class="sxs-lookup"><span data-stu-id="ef974-120">In the Closing method field, you can define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
    * <span data-ttu-id="ef974-121">W polu Koniec dnia roboczego można wprowadzić godzinę, jeśli transakcje zachodzące po północy mają być księgowane w poprzednim dniu.</span><span class="sxs-lookup"><span data-stu-id="ef974-121">In the End of business day field, you can enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
    * <span data-ttu-id="ef974-122">Wybierz opcję „Tak”, jeśli transakcje zachodzące po północy mają być księgowane jako część poprzedniego dnia.</span><span class="sxs-lookup"><span data-stu-id="ef974-122">Select "Yes" if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
    * <span data-ttu-id="ef974-123">Wybierz opcję „Tak”, aby zestawienia były tworzone dla każdej zdefiniowanej metody wykonywania zestawień.</span><span class="sxs-lookup"><span data-stu-id="ef974-123">Select "Yes" to get statements created for each statement method defined.</span></span> <span data-ttu-id="ef974-124">Może to być przydatne, jeśli wydajność księgowania wymaga poprawy dla sklepów o dużym wolumenie transakcji, ponieważ spowoduje to utworzenie wielu mniejszych zestawień, które mogą być przetwarzane jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="ef974-124">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
    * <span data-ttu-id="ef974-125">W polu Domyślny odbiorca można wybrać konto odbiorcy na potrzeby sprzedaży klientom przypadkowym.</span><span class="sxs-lookup"><span data-stu-id="ef974-125">In the Default customer field, you can select the customer account to use for sales to walk-in customers.</span></span>  


