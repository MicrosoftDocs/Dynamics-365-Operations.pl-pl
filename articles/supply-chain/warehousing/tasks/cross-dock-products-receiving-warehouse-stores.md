---
title: Przeładunek kompletacyjny z magazynu przyjmującego do sklepów
description: Ta procedura prowadzi przez kolejne kroki tworzenia i przetwarzania przeładunku kompletacyjnego w celu dostarczenia produktów z lokalizacji przyjęcia podanej w zamówieniu zakupu do jednego lub wielu sklepów.
author: ShylaThompson
manager: tfehr
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f17585359d93030d7830eb60ce07af7c48f5d49f
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979582"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a><span data-ttu-id="d2f4b-103">Przeładunek kompletacyjny z magazynu przyjmującego do sklepów</span><span class="sxs-lookup"><span data-stu-id="d2f4b-103">Cross-dock products from receiving warehouse to stores</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d2f4b-104">Ta procedura prowadzi przez kolejne kroki tworzenia i przetwarzania przeładunku kompletacyjnego w celu dostarczenia produktów z lokalizacji przyjęcia podanej w zamówieniu zakupu do jednego lub wielu sklepów.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-104">This procedure walks through the steps to create and process a Cross-dock to distribute products from the receiving location of a purchase order to one or many stores.</span></span> <span data-ttu-id="d2f4b-105">Użytkownik może zdefiniować wiele konfiguracji i otrzymywać z systemu sugestie rozdziału produktów albo ręcznie wpisać, gdzie produkty mają być dostarczane i ile towaru trafi do każdego sklepu.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="d2f4b-106">Procedura nie obejmuje konfigurowania danych, które mogą być używane w przeładunku kompletacyjnym, takich jak reguły uzupełnienia, hierarchie organizacyjne i wagi sklepów.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-106">The procedure doesn't include setup of data that can be used in the Cross-dock, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="d2f4b-107">Procedura wykorzystuje firmę demonstracyjną USRT.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-107">The procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="d2f4b-108">Przejdź do okna Wszystkie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-108">Go to All purchase orders.</span></span>
2. <span data-ttu-id="d2f4b-109">Na liście zaznacz zamówienie zakupu i kliknij łącze, aby je otworzyć.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-109">Select a purchase order in the list and click the link to open the order.</span></span>
3. <span data-ttu-id="d2f4b-110">W okienku akcji kliknij opcję Retail i Commerce.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-110">On the Action Pane, click Retail and Commerce.</span></span>
4. <span data-ttu-id="d2f4b-111">Kliknij opcję Przeładunek kompletacyjny.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-111">Click Cross docking.</span></span>
5. <span data-ttu-id="d2f4b-112">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-112">Click Edit.</span></span>
    * <span data-ttu-id="d2f4b-113">Kategoria może służyć do filtrowania towarów w sekcji Wiersze.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-113">The category can be used to filter the items in the Lines section.</span></span>  
6. <span data-ttu-id="d2f4b-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d2f4b-115">W polu Ilość do przeładunku kompletacyjnego wpisz wartość, aby określić, jaka część nabywanej ilości wybranego produktu powinny zostać rozdzielona.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-115">In the Cross docking quantity field, type a value to specify how much of the quantity being purchased of the selected product should be distributed.</span></span>
8. <span data-ttu-id="d2f4b-116">W polu Ilość do dodatkowego przeładunku kompletacyjnego wprowadź wartość określającą ilość dostępnych kupowanych produktów, jaka ma zostać rozesłana.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-116">In the Additional cross docking quantity field, enter a value to specify the quantities to distribute for the available products being purchased</span></span>
9. <span data-ttu-id="d2f4b-117">W polu Dystrybucja wpisz „Waga lokalizacji”.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-117">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="d2f4b-118">Można wybrać różne typy, aby używać różnych reguł dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-118">You can select the other types to use different rules for the distribution.</span></span>  
10. <span data-ttu-id="d2f4b-119">W polu Hierarchia uzupełnienia wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-119">In the Replenishment hierarchy field, select a value.</span></span>
11. <span data-ttu-id="d2f4b-120">W polu Uwzględnianie asortymentów wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-120">Select Yes in the Respect assortments field.</span></span>
12. <span data-ttu-id="d2f4b-121">Kliknij opcję Oblicz ilości.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-121">Click Calculate quantities.</span></span>
13. <span data-ttu-id="d2f4b-122">Kliknij opcję Utwórz zamówienie.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-122">Click Create order.</span></span>
14. <span data-ttu-id="d2f4b-123">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-123">Click Yes.</span></span>
15. <span data-ttu-id="d2f4b-124">Na liście znajdź i zaznacz magazyn, który przyjął produkty.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-124">In the list, find and select a warehouse that received products</span></span>
16. <span data-ttu-id="d2f4b-125">Kliknij opcję Zamówienie, aby wyświetlić zamówienia, które zostały utworzone dla wybranego magazynu.</span><span class="sxs-lookup"><span data-stu-id="d2f4b-125">Click Order to view the orders that got created for the selected warehouse</span></span>

