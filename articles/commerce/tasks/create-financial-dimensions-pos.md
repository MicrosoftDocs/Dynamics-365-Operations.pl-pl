---
title: Tworzenie wymiarów finansowych dla rejestrów punktu sprzedaży i konfigurowanie wartości wymiarów z rejestrów
description: Ta procedura prowadzi przez proces tworzenia wymiarów finansowych dla kas w punkcie sprzedaży (POS) i pokazuje, jak konfigurować wartości wymiarów finansowych w kasach.
author: jashanno
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4042fb9da0fe38de50ad7e0c8e64b98925ea1188
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5265966"
---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="13f33-103">Tworzenie wymiarów finansowych dla rejestrów punktu sprzedaży i konfigurowanie wartości wymiarów z rejestrów</span><span class="sxs-lookup"><span data-stu-id="13f33-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13f33-104">Ta procedura prowadzi przez proces tworzenia wymiarów finansowych dla kas w punkcie sprzedaży (POS) i pokazuje, jak konfigurować wartości wymiarów finansowych w kasach.</span><span class="sxs-lookup"><span data-stu-id="13f33-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="13f33-105">Procedura nie ma innych czynności pokrewnych, takich jak tworzenie zestawów wymiarów i struktur kont.</span><span class="sxs-lookup"><span data-stu-id="13f33-105">This procedure doesn't include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="13f33-106">Te zadania znajdują się w innych artykułach.</span><span class="sxs-lookup"><span data-stu-id="13f33-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="13f33-107">To nagranie wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="13f33-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="13f33-108">Wybierz kolejno opcje Księga główna > Plan kont > Wymiary > Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="13f33-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="13f33-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="13f33-109">Click New.</span></span>
3. <span data-ttu-id="13f33-110">W polu Użyj wartości z wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="13f33-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="13f33-111">W polu Wymiar menu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="13f33-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="13f33-112">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="13f33-112">Click Activate.</span></span>
6. <span data-ttu-id="13f33-113">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="13f33-113">Click Close.</span></span>
7. <span data-ttu-id="13f33-114">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="13f33-114">Click Activate.</span></span>
8. <span data-ttu-id="13f33-115">Kliknij opcję Wartości wymiarów.</span><span class="sxs-lookup"><span data-stu-id="13f33-115">Click Dimension values.</span></span>
9. <span data-ttu-id="13f33-116">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13f33-116">Close the page.</span></span>
10. <span data-ttu-id="13f33-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13f33-117">Click Save.</span></span>
11. <span data-ttu-id="13f33-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13f33-118">Close the page.</span></span>
12. <span data-ttu-id="13f33-119">Wybierz kolejno opcje Retail i Commerce > Ustawienia kanału > Ustawienia punktu sprzedaży > Rejestry.</span><span class="sxs-lookup"><span data-stu-id="13f33-119">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="13f33-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="13f33-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="13f33-121">Przełącz rozwinięcie sekcji Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="13f33-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="13f33-122">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="13f33-122">Click Edit.</span></span>
16. <span data-ttu-id="13f33-123">W polu Terminal kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="13f33-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="13f33-124">Na liście znajdź i wybierz wartość wymiaru dla aktualizowanej kasy.</span><span class="sxs-lookup"><span data-stu-id="13f33-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="13f33-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13f33-125">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]