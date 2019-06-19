---
title: Tworzenie kanału online i definiowanie atrybutów kanału
description: Ta procedura zawiera instruktaż tworzenia nowego kanału online i dodawania go do hierarchii organizacyjnej.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4547731d7e3bc56b1ba5e0a35ff4746c6c0e9863
ms.sourcegitcommit: 901ec3b360303bb8b4d9a9dcfecc6d75d7f844a0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2019
ms.locfileid: "1618303"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="bc79a-103">Tworzenie kanału online i definiowanie atrybutów kanału</span><span class="sxs-lookup"><span data-stu-id="bc79a-103">Create online channel and define channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="bc79a-104">Ta procedura zawiera instruktaż tworzenia nowego kanału online i dodawania go do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="bc79a-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="bc79a-105">Aby można było utworzyć nowy kanał online, należy najpierw utworzyć hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="bc79a-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="bc79a-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="bc79a-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="bc79a-107">Tworzenie nowego kanału online</span><span class="sxs-lookup"><span data-stu-id="bc79a-107">Create a new online channel</span></span>
1. <span data-ttu-id="bc79a-108">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy internetowe.</span><span class="sxs-lookup"><span data-stu-id="bc79a-108">Go to Retail and commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="bc79a-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="bc79a-109">Click New.</span></span>
3. <span data-ttu-id="bc79a-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc79a-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="bc79a-111">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc79a-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="bc79a-112">W polu Strefa czasowa sklepu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="bc79a-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="bc79a-113">W polu Domyślny odbiorca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc79a-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="bc79a-114">W polu Książka adresowa odbiorców wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc79a-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="bc79a-115">W polu Warunki płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc79a-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="bc79a-116">W polu Metoda płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc79a-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="bc79a-117">W polu Profil powiadomienia pocztą e-mail wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc79a-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="bc79a-118">Rozwiń sekcję Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="bc79a-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="bc79a-119">W polu BusinessUnit wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc79a-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="bc79a-120">Podobnie można ustawić wartości dla wszystkich innych wymiarów domyślnych.</span><span class="sxs-lookup"><span data-stu-id="bc79a-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="bc79a-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="bc79a-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="bc79a-122">Dodawanie kanału online do hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="bc79a-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="bc79a-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bc79a-123">Close the page.</span></span>
2. <span data-ttu-id="bc79a-124">Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Hierarchie organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="bc79a-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="bc79a-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="bc79a-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="bc79a-126">Kliknij przycisk Wyświetl.</span><span class="sxs-lookup"><span data-stu-id="bc79a-126">Click View.</span></span>
5. <span data-ttu-id="bc79a-127">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="bc79a-127">Click Edit.</span></span>
    * <span data-ttu-id="bc79a-128">Można wybrać dowolny węzeł hierarchii, aby wstawić w nim nowy kanał.</span><span class="sxs-lookup"><span data-stu-id="bc79a-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="bc79a-129">Kliknij przycisk Wstaw.</span><span class="sxs-lookup"><span data-stu-id="bc79a-129">Click Insert.</span></span>
7. <span data-ttu-id="bc79a-130">Kliknij opcję Kanał sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="bc79a-130">Click Retail channel.</span></span>
8. <span data-ttu-id="bc79a-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="bc79a-131">Click OK.</span></span>
9. <span data-ttu-id="bc79a-132">Kliknij przycisk Publikuj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="bc79a-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="bc79a-133">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="bc79a-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="bc79a-134">Kliknij przycisk Publikuj.</span><span class="sxs-lookup"><span data-stu-id="bc79a-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-realtime-notification"></a><span data-ttu-id="bc79a-135">Konfigurowanie zamówień w celu powiadamiania w czasie zbliżonym do rzeczywistego</span><span class="sxs-lookup"><span data-stu-id="bc79a-135">Configure orders for near realtime notification</span></span>
1. <span data-ttu-id="bc79a-136">Kliknij kolejno opcje Sprzedaż detaliczna > Ustawienia centrali > Parametry > Parametry sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="bc79a-136">Go to Retail  > Headquarters setup > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="bc79a-137">Zmień ustawienie opcji Użyj usługi czasu rzeczywistego dla tworzenia zamówień handlu elektronicznego na „Tak”.</span><span class="sxs-lookup"><span data-stu-id="bc79a-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="bc79a-138">Wykonaj harmonogram dystrybucji 1070, aby zsynchronizować zmiany z bazą danych kanału.</span><span class="sxs-lookup"><span data-stu-id="bc79a-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 


