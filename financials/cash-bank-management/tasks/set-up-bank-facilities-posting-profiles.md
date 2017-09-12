--- 
title: "Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń"
description: "To zadanie tworzy instrument bankowy oraz profil księgowania, który jest potrzebny do przetwarzania poręczenia."
author: kweekley
manager: AnnBe
ms.date: 02/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c23fe66c58e9ceff74469cc8eab61eb606c57ee1
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a><span data-ttu-id="93c34-103">Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń</span><span class="sxs-lookup"><span data-stu-id="93c34-103">Set up bank facilities and posting profiles for letters of guarantee</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93c34-104">To zadanie tworzy instrument bankowy oraz profil księgowania, który jest potrzebny do przetwarzania poręczenia.</span><span class="sxs-lookup"><span data-stu-id="93c34-104">This task creates a Bank facility and posting profile that is needed to process a letter of guarantee.</span></span>



<span data-ttu-id="93c34-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="93c34-105">This task uses the USMF demo company.</span></span> 




## <a name="general-ledger-parameter"></a><span data-ttu-id="93c34-106">Parametr księgi głównej</span><span class="sxs-lookup"><span data-stu-id="93c34-106">General ledger parameter</span></span>
1. <span data-ttu-id="93c34-107">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="93c34-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="93c34-108">Rozwiń sekcję Dokument bankowy.</span><span class="sxs-lookup"><span data-stu-id="93c34-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="93c34-109">Zaznacz opcję Włączanie poręczenia.</span><span class="sxs-lookup"><span data-stu-id="93c34-109">Select the Enable letter of guarantee option.</span></span>
4. <span data-ttu-id="93c34-110">W polu Arkusz transakcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="93c34-110">In the Transaction journal field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="93c34-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="93c34-111">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="93c34-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="93c34-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="93c34-113">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="93c34-113">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="93c34-114">Zdefiniuj kod sekwencji numeracji odwołań do numeru poręczenia i numeru transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="93c34-114">Define number sequence code for Letter of guarantee number and Letter of guarantee transaction references</span></span>  
8. <span data-ttu-id="93c34-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="93c34-115">Click Save.</span></span>
9. <span data-ttu-id="93c34-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="93c34-116">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="93c34-117">Tworzenie instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="93c34-117">Create Bank facility</span></span>
1. <span data-ttu-id="93c34-118">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Instrumenty bankowe.</span><span class="sxs-lookup"><span data-stu-id="93c34-118">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="93c34-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="93c34-119">Click New.</span></span>
3. <span data-ttu-id="93c34-120">W polu Grupa instrumentów wprowadź nazwę grupy instrumentów bankowych dla transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="93c34-120">In the Facility group field, enter the bank facility group name for the letter of guarantee transaction.</span></span>
4. <span data-ttu-id="93c34-121">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="93c34-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="93c34-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="93c34-122">Click Save.</span></span>
6. <span data-ttu-id="93c34-123">Kliknij kartę Typy instrumentu.</span><span class="sxs-lookup"><span data-stu-id="93c34-123">Click the Facility types tab.</span></span>
7. <span data-ttu-id="93c34-124">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="93c34-124">Click New.</span></span>
8. <span data-ttu-id="93c34-125">W polu Typ instrumentu wprowadź nazwę typu instrumentów bankowych, który jest powiązany z umową instrumentu bankowego.</span><span class="sxs-lookup"><span data-stu-id="93c34-125">In the Facility type field, enter the name of the bank facility type that is related to the bank facility agreement.</span></span>
9. <span data-ttu-id="93c34-126">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="93c34-126">In the Description field, type a value.</span></span>
10. <span data-ttu-id="93c34-127">W polu Grupa instrumentów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="93c34-127">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="93c34-128">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="93c34-128">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="93c34-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="93c34-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="93c34-130">W polu Charakter instrumentu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="93c34-130">In the Facility nature field, select an option.</span></span>
14. <span data-ttu-id="93c34-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="93c34-131">Click Save.</span></span>
15. <span data-ttu-id="93c34-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="93c34-132">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="93c34-133">Profil księgowania na koncie bankowym</span><span class="sxs-lookup"><span data-stu-id="93c34-133">Bank posting profile</span></span>
1. <span data-ttu-id="93c34-134">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Profil księgowania dokumentów bankowych.</span><span class="sxs-lookup"><span data-stu-id="93c34-134">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="93c34-135">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="93c34-135">Click New.</span></span>
3. <span data-ttu-id="93c34-136">W polu Numer konta/grupy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="93c34-136">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="93c34-137">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="93c34-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="93c34-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="93c34-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="93c34-139">W polu Konto rozliczeniowe wybierz konto główne do rozliczenia.</span><span class="sxs-lookup"><span data-stu-id="93c34-139">In the Settle account field, select the main account for settlement.</span></span>
7. <span data-ttu-id="93c34-140">W polu Konto opłaty wybierz konto dla transakcji wydatkowych.</span><span class="sxs-lookup"><span data-stu-id="93c34-140">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="93c34-141">W polu Konto marży wybierz konto dla transakcji dotyczących marży.</span><span class="sxs-lookup"><span data-stu-id="93c34-141">In the Margin account field, select the account for the margin transaction.</span></span>
9. <span data-ttu-id="93c34-142">W polu Konto likwidacji wybierz konto likwidacji dla transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="93c34-142">In the Liquidation account field, select the liquidation account for the letter of guarantee transaction.</span></span> 
10. <span data-ttu-id="93c34-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="93c34-143">Click Save.</span></span>
11. <span data-ttu-id="93c34-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="93c34-144">Close the page.</span></span>


