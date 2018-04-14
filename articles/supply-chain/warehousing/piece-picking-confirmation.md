---
title: Potwierdzenie pobrania sztuk
description: "W tym temacie opisano sposób konfigurowania i stosowania potwierdzenia pobrania sztuk z urządzenia przenośnego."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5109bc180cedfb21dfb8b2920d71d54812e7e6cf
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="piece-picking-confirmation"></a><span data-ttu-id="969fc-103">Potwierdzenie pobrania sztuk</span><span class="sxs-lookup"><span data-stu-id="969fc-103">Piece picking confirmation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="969fc-104">Funkcja pobrania sztuk umożliwia potwierdzanie każdego artykułu w zapasach za pomocą pracy pobrania lub inwentaryzacji na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="969fc-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="969fc-105">Dla pobrań można potwierdzić ilość pracy do przetworzenia aż do ilości wymienionej w pracy, która ma zostać pobrana.</span><span class="sxs-lookup"><span data-stu-id="969fc-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="969fc-106">Dla pracy inwentaryzacji pracy można skanować inwentaryzowane zapasy oraz śledzić łączną ilość.</span><span class="sxs-lookup"><span data-stu-id="969fc-106">For counting work, you can scan the inventory that you are counting and track the total amount.</span></span>

<span data-ttu-id="969fc-107">Włączenie funkcji pobrania sztuk powoduje automatyczne zaznaczenie opcji Potwierdzenie produktu.</span><span class="sxs-lookup"><span data-stu-id="969fc-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="969fc-108">Dla pobrań będących pracą jest włączana maksymalna liczba towarów.</span><span class="sxs-lookup"><span data-stu-id="969fc-108">For work-type picks, a maximum number of pieces is enabled.</span></span> <span data-ttu-id="969fc-109">Pozwala to ustawić wartość maksymalną w postaci liczby artykułów, które muszą zostać potwierdzone w trakcie procesu pracy.</span><span class="sxs-lookup"><span data-stu-id="969fc-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="969fc-110">Ilość maksymalna zależy od aktualnie przetwarzanej jednostki roboczej.</span><span class="sxs-lookup"><span data-stu-id="969fc-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="969fc-111">W pracy typu Inwentaryzacja nie można ustawić wartości maksymalnej.</span><span class="sxs-lookup"><span data-stu-id="969fc-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="969fc-112">Można również użyć ilości i jednostki miary (JM) skojarzonej z zeskanowanym kodem kreskowym.</span><span class="sxs-lookup"><span data-stu-id="969fc-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="969fc-113">Ta funkcjonalność będzie działać w przyjęciach w przepływach przychodzących, w tym przyjęciach spod mieszanych numerów identyfikacyjnych oraz towarów z zamówień zakupu, zamówienia przeniesienia i ładunków.</span><span class="sxs-lookup"><span data-stu-id="969fc-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="969fc-114">Działa także dla pobrań sztuk, gdzie zeskanowanie kodu kreskowego powoduje dodanie ilości do łącznej liczby potwierdzonych sztuk konwertowanych między jednostką miary kodu kreskowego a jednostką roboczą.</span><span class="sxs-lookup"><span data-stu-id="969fc-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="969fc-115">Jeśli podczas zliczania w jednostce miary kodu kreskowego potwierdzi się, że ilość jest dozwolona dla inwentaryzacji w grupie sekwencji, ilość zostanie dodana do łącznej liczby.</span><span class="sxs-lookup"><span data-stu-id="969fc-115">If, when counting the UOM on the bar code, it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="969fc-116">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="969fc-116">Where it applies</span></span>

<span data-ttu-id="969fc-117">Pobranie sztuk działa dla wszystkich prac inwentaryzacji oraz dla pierwszego pobrania w każdym typie pracy.</span><span class="sxs-lookup"><span data-stu-id="969fc-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="969fc-118">Pobranie sztuk nie ma zastosowania, gdy towar jest kontrolowany przez numery seryjne lub gdy jest pobraniem do produkcji lub karty Kanban z lokalizacji oznaczonej numerem identyfikacyjnym, a ma ustawiony atrybut lokalizacji tymczasowej.</span><span class="sxs-lookup"><span data-stu-id="969fc-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="969fc-119">Konfigurowanie funkcji pobrania sztuk</span><span class="sxs-lookup"><span data-stu-id="969fc-119">Set up piece picking</span></span>

1.  <span data-ttu-id="969fc-120">Na urządzeniu przenośnym w menu otwórz formularz ustawień potwierdzenia pracy: Zarządzanie magazynem > **Zarządzanie magazynem** > **Ustawienia** > **Urządzenie przenośne** > **Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="969fc-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="969fc-121">Na urządzeniu przenośnym w menu otwórz pozycję Konfiguracja potwierdzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="969fc-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="969fc-122">W przypadku pracy typu Pobranie lub Inwentaryzacja są dostępne następujące opcje do wyboru.</span><span class="sxs-lookup"><span data-stu-id="969fc-122">The following options become available for selection when the work type is pick or counting.</span></span>


|           <span data-ttu-id="969fc-123">Opcja</span><span class="sxs-lookup"><span data-stu-id="969fc-123">Option</span></span>           |                                                                            <span data-ttu-id="969fc-124">opis</span><span class="sxs-lookup"><span data-stu-id="969fc-124">Description</span></span>                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="969fc-125">Potwierdzenie pobrania sztuk</span><span class="sxs-lookup"><span data-stu-id="969fc-125">Piece picking confirmation</span></span> | <span data-ttu-id="969fc-126">Dostępne dla typów prac Pobranie i Inwentaryzacja.</span><span class="sxs-lookup"><span data-stu-id="969fc-126">Available for pick and counting work types.</span></span> <span data-ttu-id="969fc-127">Opcja Potwierdzenie produktu jest automatycznie zaznaczona.</span><span class="sxs-lookup"><span data-stu-id="969fc-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="969fc-128">Umożliwia potwierdzenie każdego artykułu w zapasach z urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="969fc-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> |
|  <span data-ttu-id="969fc-129">Maksymalna liczba sztuk</span><span class="sxs-lookup"><span data-stu-id="969fc-129">Maximum number of pieces</span></span>  |                   <span data-ttu-id="969fc-130">Dostępne dla pracy pobrania, jeśli włączono funkcję potwierdzania pobrania sztuk.</span><span class="sxs-lookup"><span data-stu-id="969fc-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="969fc-131">Ustawia limit liczby sztuk, które należy potwierdzić.</span><span class="sxs-lookup"><span data-stu-id="969fc-131">Sets a limit to the number of pieces that you must confirm.</span></span>                   |


