---
title: Tworzenie umowy instrumentu bankowego na poręczenie
description: To zadanie tworzy umowę instrumentu bankowego w celu przetwarzania poręczenia.
author: panolte
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 165552cade2a38d9605240ab6a8ff423585786ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446784"
---
# <a name="create-a-bank-facility-agreement-for-the-letter-of-guarantee"></a><span data-ttu-id="abb16-103">Tworzenie umowy instrumentu bankowego na poręczenie</span><span class="sxs-lookup"><span data-stu-id="abb16-103">Create a bank facility agreement for the letter of guarantee</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="abb16-104">To zadanie tworzy umowę instrumentu bankowego w celu przetwarzania poręczenia.</span><span class="sxs-lookup"><span data-stu-id="abb16-104">This task creates a bank facility agreement to process a letter of guarantee.</span></span> <span data-ttu-id="abb16-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="abb16-105">This task uses the USMF demo company.</span></span> 


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="abb16-106">Tworzenie umowy instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="abb16-106">Create Bank facility agreement</span></span>
1. <span data-ttu-id="abb16-107">Wybierz kolejno opcje Zarządzanie gotówką i bankami > Poręczenia > Umowy instrumentu bankowego.</span><span class="sxs-lookup"><span data-stu-id="abb16-107">Go to Cash and bank management > Letters of guarantee > Bank facility agreements.</span></span>
2. <span data-ttu-id="abb16-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="abb16-108">Click New.</span></span>
3. <span data-ttu-id="abb16-109">W polu Numer umowy wprowadź numer umowy bankowej dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="abb16-109">In the Agreement number field, enter the bank agreement number for the transaction.</span></span>
4. <span data-ttu-id="abb16-110">W polu Konto bankowe wybierz numer konta bankowego, dla którego jest otwarte poręczenie.</span><span class="sxs-lookup"><span data-stu-id="abb16-110">In the Bank account field, select the bank account number for which the letter of guarantee is open.</span></span> 
5. <span data-ttu-id="abb16-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="abb16-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="abb16-112">W polu Data początkowa wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="abb16-112">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="abb16-113">W polu Data końcowa wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="abb16-113">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="abb16-114">Przełącz rozwinięcie sekcji Ogólne.</span><span class="sxs-lookup"><span data-stu-id="abb16-114">Toggle the expansion of the General section.</span></span>
9. <span data-ttu-id="abb16-115">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="abb16-115">Click Add line.</span></span>
10. <span data-ttu-id="abb16-116">W polu Typ instrumentu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="abb16-116">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="abb16-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="abb16-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="abb16-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="abb16-118">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="abb16-119">W polu Limit wprowadź kwotę wynegocjowaną z bankiem.</span><span class="sxs-lookup"><span data-stu-id="abb16-119">In the Limit field, enter the amount negotiated with the bank.</span></span>
14. <span data-ttu-id="abb16-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="abb16-120">Click Save.</span></span>
15. <span data-ttu-id="abb16-121">Przełącz rozwinięcie sekcji Poręczenie.</span><span class="sxs-lookup"><span data-stu-id="abb16-121">Toggle the expansion of the Letter of guarantee section.</span></span>
16. <span data-ttu-id="abb16-122">W polu Metoda obliczania wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="abb16-122">In the Calculation method field, select an option.</span></span>
    * <span data-ttu-id="abb16-123">Tam gdzie trzeba wprowadź metodę obliczania i szczegóły dotyczące wartości procentowych dla opcji Depozyt zabezpieczający, Zlecenie wystawienia, Zlecenie rozszerzenia, Zlecenie zwiększenia wartości lub Zlecenie obniżenia wartości.</span><span class="sxs-lookup"><span data-stu-id="abb16-123">Enter the calculation method and percentage details for the Cash margin, Issuance commission, Extension commission, Increase value commission, or Decrease value commission, as appropriate.</span></span>   
17. <span data-ttu-id="abb16-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="abb16-124">Click Save.</span></span>

## <a name="extend-bank-facility-agreement"></a><span data-ttu-id="abb16-125">Przedłużanie umowy instrumentu bankowego</span><span class="sxs-lookup"><span data-stu-id="abb16-125">Extend bank facility agreement</span></span>
1. <span data-ttu-id="abb16-126">Kliknij przycisk Rozszerz, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="abb16-126">Click Extend to open the drop dialog.</span></span>
2. <span data-ttu-id="abb16-127">W polu Nowy numer umowy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="abb16-127">In the New agreement number field, type a value.</span></span>
3. <span data-ttu-id="abb16-128">W polu Data końcowa wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="abb16-128">In the End date field, enter a date and time.</span></span>
4. <span data-ttu-id="abb16-129">Kliknij przycisk Rozszerz.</span><span class="sxs-lookup"><span data-stu-id="abb16-129">Click Extend.</span></span>
5. <span data-ttu-id="abb16-130">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="abb16-130">Click Save.</span></span>
6. <span data-ttu-id="abb16-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="abb16-131">Close the page.</span></span>

