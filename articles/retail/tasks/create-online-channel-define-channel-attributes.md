---
title: Tworzenie kanału online i definiowanie atrybutów kanału
description: Ta procedura zawiera instruktaż tworzenia nowego kanału online i dodawania go do hierarchii organizacyjnej.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: e066e9901a97bd5b72815a7af472247ef519ecb9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "312377"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="1d9ab-103">Tworzenie kanału online i definiowanie atrybutów kanału</span><span class="sxs-lookup"><span data-stu-id="1d9ab-103">Create online channel and define channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="1d9ab-104">Ta procedura zawiera instruktaż tworzenia nowego kanału online i dodawania go do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="1d9ab-105">Aby można było utworzyć nowy kanał online, należy najpierw utworzyć hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="1d9ab-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="1d9ab-107">Tworzenie nowego kanału online</span><span class="sxs-lookup"><span data-stu-id="1d9ab-107">Create a new online channel</span></span>
1. <span data-ttu-id="1d9ab-108">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy internetowe.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-108">Go to Retail and commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="1d9ab-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-109">Click New.</span></span>
3. <span data-ttu-id="1d9ab-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="1d9ab-111">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="1d9ab-112">W polu Strefa czasowa sklepu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="1d9ab-113">W polu Domyślny odbiorca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="1d9ab-114">W polu Książka adresowa odbiorców wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="1d9ab-115">W polu Warunki płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="1d9ab-116">W polu Metoda płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="1d9ab-117">W polu Profil powiadomienia pocztą e-mail wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="1d9ab-118">Rozwiń sekcję Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="1d9ab-119">W polu BusinessUnit wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="1d9ab-120">Podobnie można ustawić wartości dla wszystkich innych wymiarów domyślnych.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="1d9ab-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="1d9ab-122">Dodawanie kanału online do hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="1d9ab-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="1d9ab-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-123">Close the page.</span></span>
2. <span data-ttu-id="1d9ab-124">Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Hierarchie organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="1d9ab-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="1d9ab-126">Kliknij przycisk Wyświetl.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-126">Click View.</span></span>
5. <span data-ttu-id="1d9ab-127">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-127">Click Edit.</span></span>
    * <span data-ttu-id="1d9ab-128">Można wybrać dowolny węzeł hierarchii, aby wstawić w nim nowy kanał.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="1d9ab-129">Kliknij przycisk Wstaw.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-129">Click Insert.</span></span>
7. <span data-ttu-id="1d9ab-130">Kliknij opcję Kanał sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-130">Click Retail channel.</span></span>
8. <span data-ttu-id="1d9ab-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-131">Click OK.</span></span>
9. <span data-ttu-id="1d9ab-132">Kliknij przycisk Publikuj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="1d9ab-133">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="1d9ab-134">Kliknij przycisk Publikuj.</span><span class="sxs-lookup"><span data-stu-id="1d9ab-134">Click Publish.</span></span>

