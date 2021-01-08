---
title: Dodawanie wariantów produktów do zamówienia zakupu przy użyciu wag wariantu
description: Ta procedura zawiera instruktaż używania wag wariantów do automatycznego wypełniania wierszy zamówień zakupu dla każdego wariantu produktu.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27ff3784074a36d073930ba68c8dec8b1121356e
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435627"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="a88a4-103">Dodawanie wariantów produktów do zamówienia zakupu przy użyciu wag wariantu</span><span class="sxs-lookup"><span data-stu-id="a88a4-103">Add variant products to purchase orders using variant weights</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a88a4-104">Ta procedura zawiera instruktaż używania wag wariantów do automatycznego wypełniania wierszy zamówień zakupu dla każdego wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="a88a4-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="a88a4-105">Po wybraniu ilości produktu, jaką chcesz kupić, dla wszystkich wariantów produktu są tworzone wiersze zamówienia zakupu z ilościami sugerowanymi na podstawie wag skonfigurowanych w wariantach produktu.</span><span class="sxs-lookup"><span data-stu-id="a88a4-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="a88a4-106">Ta procedura nie obejmuje kroków konfigurowania wartości wagowych w wymiarach produktu i wariantach produktu.</span><span class="sxs-lookup"><span data-stu-id="a88a4-106">This procedure doesn't include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="a88a4-107">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="a88a4-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="a88a4-108">Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="a88a4-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="a88a4-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a88a4-109">Click New.</span></span>
3. <span data-ttu-id="a88a4-110">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a88a4-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a88a4-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a88a4-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a88a4-112">Przełącz rozwinięcie sekcji Ogólne.</span><span class="sxs-lookup"><span data-stu-id="a88a4-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="a88a4-113">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a88a4-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="a88a4-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a88a4-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a88a4-115">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a88a4-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="a88a4-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a88a4-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="a88a4-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a88a4-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="a88a4-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a88a4-118">Click OK.</span></span>
12. <span data-ttu-id="a88a4-119">Przełącz rozwinięcie sekcji Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="a88a4-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="a88a4-120">Kliknij kartę Warianty.</span><span class="sxs-lookup"><span data-stu-id="a88a4-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="a88a4-121">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="a88a4-121">Click Add line.</span></span>
15. <span data-ttu-id="a88a4-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a88a4-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="a88a4-123">W polu Numer towaru wpisz wartość „0140”.</span><span class="sxs-lookup"><span data-stu-id="a88a4-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="a88a4-124">W polu Ilość wpisz wartość 1000.</span><span class="sxs-lookup"><span data-stu-id="a88a4-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="a88a4-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a88a4-125">Click Save.</span></span>

