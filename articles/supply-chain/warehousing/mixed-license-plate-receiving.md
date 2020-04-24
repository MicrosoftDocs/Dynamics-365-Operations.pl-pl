---
title: Przyjęcie mieszanego numeru identyfikacyjnego
description: W tym temacie opisano sposób używania funkcji przyjęć z mieszanych numerów identyfikacyjnych do rejestrowania i tworzenia pracy dla wielu towarów na urządzeniu komórkowym.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15c058887da33b522c5d9a1a8d2c45a5d1566a5d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215776"
---
# <a name="mixed-license-plate-receiving"></a><span data-ttu-id="0832d-103">Przyjęcie mieszanego numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="0832d-103">Mixed license plate receiving</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0832d-104">Przyjęcie z mieszanych numerów identyfikacyjnych umożliwia zbudowanie numeru identyfikacyjnego zawierającego wiele towarów, zanim zarejestrujesz i utworzysz pracę odłożenia.</span><span class="sxs-lookup"><span data-stu-id="0832d-104">Mixed license plate receiving allows you to build a license plate consisting of multiple items before you register and create put-away work.</span></span> 

<span data-ttu-id="0832d-105">Numer identyfikacyjny obejmujący wiele towarów nie musi być rozdzielany w doku rozładunkowym w celu zarejestrowania osobno każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="0832d-105">A license plate that consists of multiple items does not have to be split at the receiving dock for you to register each item.</span></span> 

<span data-ttu-id="0832d-106">Jeśli wiersze dokumentu źródłowego są identyfikowane na podstawie przepływu towarów, można skanować kody kreskowe na etapie kontroli towarów.</span><span class="sxs-lookup"><span data-stu-id="0832d-106">When using an item-related flow to identify the source document lines, you can scan bar codes on the item control.</span></span> <span data-ttu-id="0832d-107">Jeśli w kodzie kreskowym są skonfigurowane ilość i jednostka miary (JM), towar i ilość zostaną automatycznie dodane do mieszanego numeru identyfikacyjnego, po czym nastąpi powrót do ekranu umożliwiającego zeskanowanie następnego towaru.</span><span class="sxs-lookup"><span data-stu-id="0832d-107">If the bar code has a quantity and a unit of measure (UOM) configured on it, the item and quantity will automatically be added to the mixed license plate, and you will be returned to the screen to scan another item.</span></span> <span data-ttu-id="0832d-108">Umożliwia to szybkie przeskanowanie wszystkich towarów bez konieczności potwierdzania każdego kroku.</span><span class="sxs-lookup"><span data-stu-id="0832d-108">This allows you to quickly scan all the items without having to make a confirmation at each step.</span></span> 

<span data-ttu-id="0832d-109">W przepływie przyjęcia z mieszanych numerów identyfikacyjnych można wyświetlić listę towarów, które już zostały zeskanowane do numeru identyfikacyjnego, i z tego okna zmodyfikować lub skorygować ilość towaru.</span><span class="sxs-lookup"><span data-stu-id="0832d-109">In the flow for mixed license plate receiving, you can display the list of items that are already scanned to the license plate and from here you can modify or correct the quantity of an item.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="0832d-110">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="0832d-110">Where it applies</span></span>

<span data-ttu-id="0832d-111">Przyjęcie z mieszanych numerów identyfikacyjnych to przepływ przyjęcia na urządzeniu komórkowym służący do rejestrowania i tworzenia pracy dla wielu wierszy/towarów równocześnie.</span><span class="sxs-lookup"><span data-stu-id="0832d-111">Mixed license plate receiving is a mobile device receiving flow to register and create work for multiple lines/items at the same time.</span></span> <span data-ttu-id="0832d-112">Jest to przydatne, jeśli przyjmujesz z przychodzących numerów identyfikacyjnych zawierających wiele towarów.</span><span class="sxs-lookup"><span data-stu-id="0832d-112">This is useful if you receive inbound license plates with multiple items.</span></span> 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a><span data-ttu-id="0832d-113">Konfigurowanie przyjęcia z mieszanych numerów identyfikacyjnych</span><span class="sxs-lookup"><span data-stu-id="0832d-113">How to set up mixed license plate receiving</span></span>
<span data-ttu-id="0832d-114">Przyjęcie z mieszanych numerów identyfikacyjnych jest konfigurowane jako element menu w urządzeniu komórkowym.</span><span class="sxs-lookup"><span data-stu-id="0832d-114">Mixed license plate receiving is set up as a mobile device menu item.</span></span>

<span data-ttu-id="0832d-115">Należy utworzyć nowy element menu z trybem Praca, który nie wykorzystuje istniejącej pracy, i ustawić jedną z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="0832d-115">You need to create a new menu item with mode work that does not use existing work and use one of the following methods:</span></span>

- <span data-ttu-id="0832d-116">Przyjęcie mieszanego numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="0832d-116">Mixed license plate receiving</span></span>
- <span data-ttu-id="0832d-117">Przyjęcie i odłożenie mieszanego numeru identyfikacyjnego</span><span class="sxs-lookup"><span data-stu-id="0832d-117">Mixed license plate receiving and put away</span></span>

<span data-ttu-id="0832d-118">Dostępne są następujące opcje identyfikujące wiersze dokumentu źródłowego: pozycja zamówienia zakupu, wiersz zamówienia zakupu, zamówienia zwrotu, pozycja zamówienia przeniesienia i wiersz zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="0832d-118">The options to identify the source document lines are purchase order item, purchase order line, return order, transfer order item, and transfer order line.</span></span> <span data-ttu-id="0832d-119">Te opcje mogą zmieniać kolejność przyjęcia dla pojedynczego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="0832d-119">These options can change the receiving order on a single license plate.</span></span> <span data-ttu-id="0832d-120">Ostatnia opcja to według pozycji ładunku.</span><span class="sxs-lookup"><span data-stu-id="0832d-120">The last option is by load item.</span></span> <span data-ttu-id="0832d-121">Do numeru identyfikacyjnego można dodać wiele towarów, ale nie można się przełączać między różnymi ładunkami.</span><span class="sxs-lookup"><span data-stu-id="0832d-121">You can add multiple items to a license plate, but you cannot switch between multiple loads.</span></span>
