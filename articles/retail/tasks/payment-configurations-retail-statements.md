--- 
title: "Konfigurowanie ustawień metody płatności wpływających na zestawienia sieci sprzedaży"
description: "Ta procedura pokazuje konfiguracje metod płatności dla sklepów sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ba21db9ee97dc4d851c77a906927ef513940b743
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="configure-payment-method-settings-that-affect-retail-statements"></a><span data-ttu-id="e0abc-103">Konfigurowanie ustawień metody płatności wpływających na zestawienia sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e0abc-103">Configure payment method settings that affect retail statements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e0abc-104">Ta procedura pokazuje konfiguracje metod płatności dla sklepów sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e0abc-104">This procedure demonstrates configurations for Retail store payment methods, which affect how Retail statements get created and posted.</span></span>

<span data-ttu-id="e0abc-105">To nagranie wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="e0abc-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="e0abc-106">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e0abc-106">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="e0abc-107">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e0abc-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e0abc-108">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e0abc-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e0abc-109">W okienku akcji kliknij pozycję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="e0abc-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="e0abc-110">Kliknij opcję Metody płatności.</span><span class="sxs-lookup"><span data-stu-id="e0abc-110">Click Payment methods.</span></span>
6. <span data-ttu-id="e0abc-111">Rozwiń lub zwiń sekcję Księgowanie.</span><span class="sxs-lookup"><span data-stu-id="e0abc-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="e0abc-112">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="e0abc-112">Click Edit.</span></span>
    * <span data-ttu-id="e0abc-113">Określ, czy kwoty otrzymane przy tej metodzie płatności mają być księgowane na koncie księgowym czy koncie bankowym.</span><span class="sxs-lookup"><span data-stu-id="e0abc-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="e0abc-114">Wybierz konto, na którym mają być księgowane kwoty otrzymane w tej metodzie płatności.</span><span class="sxs-lookup"><span data-stu-id="e0abc-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="e0abc-115">Wybierz konto do księgowania ewentualnych różnic między kwotą łącznie otrzymaną z transakcji a kwotą obliczoną dla tej metody płatności.</span><span class="sxs-lookup"><span data-stu-id="e0abc-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="e0abc-116">W tym polu można wpisać kwotę kontrolującą, kiedy kwota różnicy ma być księgowana na innym koncie rozbieżności.</span><span class="sxs-lookup"><span data-stu-id="e0abc-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="e0abc-117">Można używać tego pola do śledzenia ponadnormatywnych różnic.</span><span class="sxs-lookup"><span data-stu-id="e0abc-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="e0abc-118">Wybierz konto do księgowania ewentualnych różnic między kwotą łącznie otrzymaną z transakcji a kwotą obliczoną, jeśli przekracza ona wartość zdefiniowaną w polu „Maksymalna kwota różnicy”.</span><span class="sxs-lookup"><span data-stu-id="e0abc-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="e0abc-119">Wybierz opcję „Tak”, aby księgować kwoty przekazywane do banku na oddzielnym koncie.</span><span class="sxs-lookup"><span data-stu-id="e0abc-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="e0abc-120">W tym polu można określić, czy kwoty przekazywane do banku mają być księgowane na koncie księgowym czy koncie bankowym.</span><span class="sxs-lookup"><span data-stu-id="e0abc-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="e0abc-121">Wybierz konto, na którym mają być księgowane kwoty przekazywane do banku.</span><span class="sxs-lookup"><span data-stu-id="e0abc-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="e0abc-122">Wybierz typ transakcji bankowej, który będzie używany przy księgowaniu kwot przekazywanych do banku na konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="e0abc-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="e0abc-123">Wybierz opcję „Tak”, aby księgować kwoty przekazywane do sejfu na oddzielnym koncie.</span><span class="sxs-lookup"><span data-stu-id="e0abc-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="e0abc-124">Określ, czy kwoty przekazywane do sejfu mają być księgowane na koncie księgowym czy koncie bankowym.</span><span class="sxs-lookup"><span data-stu-id="e0abc-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="e0abc-125">Wybierz konto, na którym mają być księgowane kwoty przekazywane do sejfu.</span><span class="sxs-lookup"><span data-stu-id="e0abc-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="e0abc-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e0abc-126">Click Save.</span></span>


