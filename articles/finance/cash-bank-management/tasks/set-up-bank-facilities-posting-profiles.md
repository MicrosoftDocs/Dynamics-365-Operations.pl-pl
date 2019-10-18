---
title: Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń
description: To zadanie tworzy instrument bankowy oraz profil księgowania, który jest potrzebny do przetwarzania poręczenia.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 427159048ffbb17749e813d67a900622900a7f21
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179422"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a><span data-ttu-id="19ec4-103">Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń</span><span class="sxs-lookup"><span data-stu-id="19ec4-103">Set up bank facilities and posting profiles for letters of guarantee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="19ec4-104">To zadanie tworzy instrument bankowy oraz profil księgowania, który jest potrzebny do przetwarzania poręczenia.</span><span class="sxs-lookup"><span data-stu-id="19ec4-104">This task creates a Bank facility and posting profile that is needed to process a letter of guarantee.</span></span>



<span data-ttu-id="19ec4-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="19ec4-105">This task uses the USMF demo company.</span></span> 




## <a name="general-ledger-parameter"></a><span data-ttu-id="19ec4-106">Parametr księgi głównej</span><span class="sxs-lookup"><span data-stu-id="19ec4-106">General ledger parameter</span></span>
1. <span data-ttu-id="19ec4-107">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="19ec4-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="19ec4-108">Rozwiń sekcję Dokument bankowy.</span><span class="sxs-lookup"><span data-stu-id="19ec4-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="19ec4-109">Zaznacz opcję Włączanie poręczenia.</span><span class="sxs-lookup"><span data-stu-id="19ec4-109">Select the Enable letter of guarantee option.</span></span>
4. <span data-ttu-id="19ec4-110">W polu Arkusz transakcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="19ec4-110">In the Transaction journal field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="19ec4-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="19ec4-111">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="19ec4-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="19ec4-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="19ec4-113">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="19ec4-113">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="19ec4-114">Zdefiniuj kod sekwencji numeracji odwołań do numeru poręczenia i numeru transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="19ec4-114">Define number sequence code for Letter of guarantee number and Letter of guarantee transaction references</span></span>  
8. <span data-ttu-id="19ec4-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="19ec4-115">Click Save.</span></span>
9. <span data-ttu-id="19ec4-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="19ec4-116">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="19ec4-117">Tworzenie instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="19ec4-117">Create Bank facility</span></span>
1. <span data-ttu-id="19ec4-118">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Instrumenty bankowe.</span><span class="sxs-lookup"><span data-stu-id="19ec4-118">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="19ec4-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="19ec4-119">Click New.</span></span>
3. <span data-ttu-id="19ec4-120">W polu Grupa instrumentów wprowadź nazwę grupy instrumentów bankowych dla transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="19ec4-120">In the Facility group field, enter the bank facility group name for the letter of guarantee transaction.</span></span>
4. <span data-ttu-id="19ec4-121">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="19ec4-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="19ec4-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="19ec4-122">Click Save.</span></span>
6. <span data-ttu-id="19ec4-123">Kliknij kartę Typy instrumentu.</span><span class="sxs-lookup"><span data-stu-id="19ec4-123">Click the Facility types tab.</span></span>
7. <span data-ttu-id="19ec4-124">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="19ec4-124">Click New.</span></span>
8. <span data-ttu-id="19ec4-125">W polu Typ instrumentu wprowadź nazwę typu instrumentów bankowych, który jest powiązany z umową instrumentu bankowego.</span><span class="sxs-lookup"><span data-stu-id="19ec4-125">In the Facility type field, enter the name of the bank facility type that is related to the bank facility agreement.</span></span>
9. <span data-ttu-id="19ec4-126">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="19ec4-126">In the Description field, type a value.</span></span>
10. <span data-ttu-id="19ec4-127">W polu Grupa instrumentów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="19ec4-127">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="19ec4-128">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="19ec4-128">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="19ec4-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="19ec4-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="19ec4-130">W polu Charakter instrumentu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="19ec4-130">In the Facility nature field, select an option.</span></span>
14. <span data-ttu-id="19ec4-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="19ec4-131">Click Save.</span></span>
15. <span data-ttu-id="19ec4-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="19ec4-132">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="19ec4-133">Profil księgowania na koncie bankowym</span><span class="sxs-lookup"><span data-stu-id="19ec4-133">Bank posting profile</span></span>
1. <span data-ttu-id="19ec4-134">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Profil księgowania dokumentów bankowych.</span><span class="sxs-lookup"><span data-stu-id="19ec4-134">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="19ec4-135">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="19ec4-135">Click New.</span></span>
3. <span data-ttu-id="19ec4-136">W polu Numer konta/grupy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="19ec4-136">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="19ec4-137">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="19ec4-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="19ec4-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="19ec4-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="19ec4-139">W polu Konto rozliczeniowe wybierz konto główne do rozliczenia.</span><span class="sxs-lookup"><span data-stu-id="19ec4-139">In the Settle account field, select the main account for settlement.</span></span>
7. <span data-ttu-id="19ec4-140">W polu Konto opłaty wybierz konto dla transakcji wydatkowych.</span><span class="sxs-lookup"><span data-stu-id="19ec4-140">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="19ec4-141">W polu Konto marży wybierz konto dla transakcji dotyczących marży.</span><span class="sxs-lookup"><span data-stu-id="19ec4-141">In the Margin account field, select the account for the margin transaction.</span></span>
9. <span data-ttu-id="19ec4-142">W polu Konto likwidacji wybierz konto likwidacji dla transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="19ec4-142">In the Liquidation account field, select the liquidation account for the letter of guarantee transaction.</span></span> 
10. <span data-ttu-id="19ec4-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="19ec4-143">Click Save.</span></span>
11. <span data-ttu-id="19ec4-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="19ec4-144">Close the page.</span></span>

