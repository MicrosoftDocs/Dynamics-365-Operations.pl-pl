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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8e92e28c721692ed92fa931ed899c48678622349
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964801"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="26948-103">Tworzenie kanału online i definiowanie atrybutów kanału</span><span class="sxs-lookup"><span data-stu-id="26948-103">Create online channel and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26948-104">Ta procedura zawiera instruktaż tworzenia nowego kanału online i dodawania go do hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="26948-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="26948-105">Aby można było utworzyć nowy kanał online, należy najpierw utworzyć hierarchię organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="26948-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="26948-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="26948-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="26948-107">Tworzenie nowego kanału online</span><span class="sxs-lookup"><span data-stu-id="26948-107">Create a new online channel</span></span>
1. <span data-ttu-id="26948-108">Wybierz kolejno opcje Commerce > Kanały > Sklepy internetowe.</span><span class="sxs-lookup"><span data-stu-id="26948-108">Go to Retail and Commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="26948-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="26948-109">Click New.</span></span>
3. <span data-ttu-id="26948-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="26948-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="26948-111">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26948-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="26948-112">W polu Strefa czasowa sklepu wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="26948-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="26948-113">W polu Domyślny odbiorca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26948-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="26948-114">W polu Książka adresowa odbiorców wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26948-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="26948-115">W polu Warunki płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26948-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="26948-116">W polu Metoda płatności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26948-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="26948-117">W polu Profil powiadomienia pocztą e-mail wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26948-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="26948-118">Rozwiń sekcję Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="26948-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="26948-119">W polu BusinessUnit wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="26948-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="26948-120">Podobnie można ustawić wartości dla wszystkich innych wymiarów domyślnych.</span><span class="sxs-lookup"><span data-stu-id="26948-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="26948-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="26948-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="26948-122">Dodawanie kanału online do hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="26948-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="26948-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="26948-123">Close the page.</span></span>
2. <span data-ttu-id="26948-124">Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Hierarchie organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="26948-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="26948-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="26948-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="26948-126">Kliknij przycisk Wyświetl.</span><span class="sxs-lookup"><span data-stu-id="26948-126">Click View.</span></span>
5. <span data-ttu-id="26948-127">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="26948-127">Click Edit.</span></span>
    * <span data-ttu-id="26948-128">Można wybrać dowolny węzeł hierarchii, aby wstawić w nim nowy kanał.</span><span class="sxs-lookup"><span data-stu-id="26948-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="26948-129">Kliknij przycisk Wstaw.</span><span class="sxs-lookup"><span data-stu-id="26948-129">Click Insert.</span></span>
7. <span data-ttu-id="26948-130">Kliknij opcję kanał Commerce.</span><span class="sxs-lookup"><span data-stu-id="26948-130">Click Commerce channel.</span></span>
8. <span data-ttu-id="26948-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="26948-131">Click OK.</span></span>
9. <span data-ttu-id="26948-132">Kliknij przycisk Publikuj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="26948-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="26948-133">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="26948-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="26948-134">Kliknij przycisk Publikuj.</span><span class="sxs-lookup"><span data-stu-id="26948-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-real-time-notification"></a><span data-ttu-id="26948-135">Konfigurowanie zamówień w celu powiadamiania w czasie zbliżonym do rzeczywistego</span><span class="sxs-lookup"><span data-stu-id="26948-135">Configure orders for near real-time notification</span></span>
1. <span data-ttu-id="26948-136">Wybierz kolejno opcje Commerce > Ustawienia Headquarters > Parametry > Parametry Commerce.</span><span class="sxs-lookup"><span data-stu-id="26948-136">Go to Retail and Commerce  > Headquarters setup > Parameters > Commerce parameters.</span></span>
2. <span data-ttu-id="26948-137">Zmień ustawienie opcji Użyj usługi czasu rzeczywistego dla tworzenia zamówień handlu elektronicznego na „Tak”.</span><span class="sxs-lookup"><span data-stu-id="26948-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="26948-138">Wykonaj harmonogram dystrybucji 1070, aby zsynchronizować zmiany z bazą danych kanału.</span><span class="sxs-lookup"><span data-stu-id="26948-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 


