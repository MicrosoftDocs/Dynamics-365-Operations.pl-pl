--- 
title: "Dodawanie wariantów produktów do zamówienia zakupu przy użyciu wag wariantu"
description: "Ta procedura zawiera instruktaż używania wag wariantów do automatycznego wypełniania wierszy zamówień zakupu dla każdego wariantu produktu."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3db13646c82ea6dc6949aaa714a5769f9c5ad2a9
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="5035f-103">Dodawanie wariantów produktów do zamówienia zakupu przy użyciu wag wariantu</span><span class="sxs-lookup"><span data-stu-id="5035f-103">Add variant products to purchase orders using variant weights</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5035f-104">Ta procedura zawiera instruktaż używania wag wariantów do automatycznego wypełniania wierszy zamówień zakupu dla każdego wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="5035f-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="5035f-105">Po wybraniu ilości produktu, jaką chcesz kupić, dla wszystkich wariantów produktu są tworzone wiersze zamówienia zakupu z ilościami sugerowanymi na podstawie wag skonfigurowanych w wariantach produktu.</span><span class="sxs-lookup"><span data-stu-id="5035f-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="5035f-106">Ta procedura nie obejmuje kroków konfigurowania wartości wag w wymiarach produktu i wariantach produktu.</span><span class="sxs-lookup"><span data-stu-id="5035f-106">This procedure doesn’t include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="5035f-107">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="5035f-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5035f-108">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="5035f-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="5035f-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5035f-109">Click New.</span></span>
3. <span data-ttu-id="5035f-110">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5035f-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5035f-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5035f-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="5035f-112">Przełącz rozwinięcie sekcji Ogólne.</span><span class="sxs-lookup"><span data-stu-id="5035f-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="5035f-113">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5035f-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="5035f-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5035f-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5035f-115">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5035f-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="5035f-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5035f-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="5035f-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5035f-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="5035f-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5035f-118">Click OK.</span></span>
12. <span data-ttu-id="5035f-119">Przełącz rozwinięcie sekcji Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="5035f-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="5035f-120">Kliknij kartę Warianty.</span><span class="sxs-lookup"><span data-stu-id="5035f-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="5035f-121">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="5035f-121">Click Add line.</span></span>
15. <span data-ttu-id="5035f-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="5035f-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="5035f-123">W polu Numer towaru wpisz wartość „0140”.</span><span class="sxs-lookup"><span data-stu-id="5035f-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="5035f-124">W polu Ilość wpisz wartość 1000.</span><span class="sxs-lookup"><span data-stu-id="5035f-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="5035f-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5035f-125">Click Save.</span></span>


