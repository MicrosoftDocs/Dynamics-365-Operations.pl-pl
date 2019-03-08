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
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f696f5aa809692a0cc2c4ff559945a301480d7e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "321669"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a><span data-ttu-id="eafbf-103">Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń</span><span class="sxs-lookup"><span data-stu-id="eafbf-103">Set up bank facilities and posting profiles for letters of guarantee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eafbf-104">To zadanie tworzy instrument bankowy oraz profil księgowania, który jest potrzebny do przetwarzania poręczenia.</span><span class="sxs-lookup"><span data-stu-id="eafbf-104">This task creates a Bank facility and posting profile that is needed to process a letter of guarantee.</span></span>



<span data-ttu-id="eafbf-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="eafbf-105">This task uses the USMF demo company.</span></span> 




## <a name="general-ledger-parameter"></a><span data-ttu-id="eafbf-106">Parametr księgi głównej</span><span class="sxs-lookup"><span data-stu-id="eafbf-106">General ledger parameter</span></span>
1. <span data-ttu-id="eafbf-107">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="eafbf-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="eafbf-108">Rozwiń sekcję Dokument bankowy.</span><span class="sxs-lookup"><span data-stu-id="eafbf-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="eafbf-109">Zaznacz opcję Włączanie poręczenia.</span><span class="sxs-lookup"><span data-stu-id="eafbf-109">Select the Enable letter of guarantee option.</span></span>
4. <span data-ttu-id="eafbf-110">W polu Arkusz transakcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="eafbf-110">In the Transaction journal field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="eafbf-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="eafbf-111">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="eafbf-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="eafbf-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="eafbf-113">Kliknij kartę Sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="eafbf-113">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="eafbf-114">Zdefiniuj kod sekwencji numeracji odwołań do numeru poręczenia i numeru transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="eafbf-114">Define number sequence code for Letter of guarantee number and Letter of guarantee transaction references</span></span>  
8. <span data-ttu-id="eafbf-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="eafbf-115">Click Save.</span></span>
9. <span data-ttu-id="eafbf-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="eafbf-116">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="eafbf-117">Tworzenie instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="eafbf-117">Create Bank facility</span></span>
1. <span data-ttu-id="eafbf-118">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Instrumenty bankowe.</span><span class="sxs-lookup"><span data-stu-id="eafbf-118">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="eafbf-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="eafbf-119">Click New.</span></span>
3. <span data-ttu-id="eafbf-120">W polu Grupa instrumentów wprowadź nazwę grupy instrumentów bankowych dla transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="eafbf-120">In the Facility group field, enter the bank facility group name for the letter of guarantee transaction.</span></span>
4. <span data-ttu-id="eafbf-121">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="eafbf-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="eafbf-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="eafbf-122">Click Save.</span></span>
6. <span data-ttu-id="eafbf-123">Kliknij kartę Typy instrumentu.</span><span class="sxs-lookup"><span data-stu-id="eafbf-123">Click the Facility types tab.</span></span>
7. <span data-ttu-id="eafbf-124">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="eafbf-124">Click New.</span></span>
8. <span data-ttu-id="eafbf-125">W polu Typ instrumentu wprowadź nazwę typu instrumentów bankowych, który jest powiązany z umową instrumentu bankowego.</span><span class="sxs-lookup"><span data-stu-id="eafbf-125">In the Facility type field, enter the name of the bank facility type that is related to the bank facility agreement.</span></span>
9. <span data-ttu-id="eafbf-126">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="eafbf-126">In the Description field, type a value.</span></span>
10. <span data-ttu-id="eafbf-127">W polu Grupa instrumentów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="eafbf-127">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="eafbf-128">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="eafbf-128">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="eafbf-129">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="eafbf-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="eafbf-130">W polu Charakter instrumentu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="eafbf-130">In the Facility nature field, select an option.</span></span>
14. <span data-ttu-id="eafbf-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="eafbf-131">Click Save.</span></span>
15. <span data-ttu-id="eafbf-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="eafbf-132">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="eafbf-133">Profil księgowania na koncie bankowym</span><span class="sxs-lookup"><span data-stu-id="eafbf-133">Bank posting profile</span></span>
1. <span data-ttu-id="eafbf-134">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Profil księgowania dokumentów bankowych.</span><span class="sxs-lookup"><span data-stu-id="eafbf-134">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="eafbf-135">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="eafbf-135">Click New.</span></span>
3. <span data-ttu-id="eafbf-136">W polu Numer konta/grupy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="eafbf-136">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="eafbf-137">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="eafbf-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="eafbf-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="eafbf-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="eafbf-139">W polu Konto rozliczeniowe wybierz konto główne do rozliczenia.</span><span class="sxs-lookup"><span data-stu-id="eafbf-139">In the Settle account field, select the main account for settlement.</span></span>
7. <span data-ttu-id="eafbf-140">W polu Konto opłaty wybierz konto dla transakcji wydatkowych.</span><span class="sxs-lookup"><span data-stu-id="eafbf-140">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="eafbf-141">W polu Konto marży wybierz konto dla transakcji dotyczących marży.</span><span class="sxs-lookup"><span data-stu-id="eafbf-141">In the Margin account field, select the account for the margin transaction.</span></span>
9. <span data-ttu-id="eafbf-142">W polu Konto likwidacji wybierz konto likwidacji dla transakcji poręczenia.</span><span class="sxs-lookup"><span data-stu-id="eafbf-142">In the Liquidation account field, select the liquidation account for the letter of guarantee transaction.</span></span> 
10. <span data-ttu-id="eafbf-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="eafbf-143">Click Save.</span></span>
11. <span data-ttu-id="eafbf-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="eafbf-144">Close the page.</span></span>

