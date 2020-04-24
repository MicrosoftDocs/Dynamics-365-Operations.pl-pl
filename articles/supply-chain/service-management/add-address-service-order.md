---
title: Dodawanie adresu do zlecenia serwisowego
description: W tym temacie opisano sposób dodawania adresu odbiorcy do zlecenia serwisowego.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5b1c0e300edc45ae3f4be9eae8afa56e06cccd6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203096"
---
# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="26da2-103">Dodawanie adresu do zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="26da2-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="26da2-104">W tym temacie opisano sposób dodawania adresu odbiorcy do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="26da2-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="26da2-105">Podczas tworzenia zlecenia serwisowego informacje adresowe są przenoszone z projektu, do którego jest dołączone zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="26da2-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="26da2-106">Jednak można wybrać alternatywną lokalizację z adresów, które zostały już wprowadzone w Microsoft Dynamics AX dla odbiorców, dostawców, oddziałów, magazynów, zleceń serwisowych i projektów.</span><span class="sxs-lookup"><span data-stu-id="26da2-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="26da2-107">Można również utworzyć nowy adres.</span><span class="sxs-lookup"><span data-stu-id="26da2-107">You can also create a new address.</span></span> <span data-ttu-id="26da2-108">Domyślnie nowy adres zostanie przeniesiony do projektu.</span><span class="sxs-lookup"><span data-stu-id="26da2-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="26da2-109">Można jednak określić, że nowy adres jest odpowiedni tylko dla tego wystąpienia usługi.</span><span class="sxs-lookup"><span data-stu-id="26da2-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="26da2-110">W takim przypadku nowy adres nie zostanie przeniesiony do projektu.</span><span class="sxs-lookup"><span data-stu-id="26da2-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="26da2-111">Tworzenie adresu odbiorcy dla zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="26da2-111">Create a customer address for a service order</span></span>

<span data-ttu-id="26da2-112">Aby dodać adres do zlecenia serwisowego, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="26da2-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="26da2-113">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="26da2-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="26da2-114">Otwórz zlecenie serwisowe, dla którego chcesz utworzyć adres.</span><span class="sxs-lookup"><span data-stu-id="26da2-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="26da2-115">W **okienku akcji** kliknij przycisk **Edytuj**, a następnie kliknij opcję **Widok nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="26da2-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="26da2-116">Na skróconej karcie **Adres** kliknij przycisk **Dodaj adres**.</span><span class="sxs-lookup"><span data-stu-id="26da2-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="26da2-117">W formularzu **Nowy adres** wprowadź niepowtarzalną nazwę dla adresu i wypełnij pozostałe pola.</span><span class="sxs-lookup"><span data-stu-id="26da2-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="26da2-118">Jeśli wprowadzisz taką samą nazwę jak istniejący adres, informacje wprowadzone w pozostałych polach zastąpią informacje istniejącego adresu.</span><span class="sxs-lookup"><span data-stu-id="26da2-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="26da2-119">Kliknij **OK**, aby skopiować nowy adres do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="26da2-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="26da2-120">Określanie adresu alternatywnego dotyczącego zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="26da2-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="26da2-121">Aby dodać inny adres do zlecenia serwisowego, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="26da2-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="26da2-122">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="26da2-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="26da2-123">Otwórz zlecenie serwisowe, dla którego chcesz wprowadzić inny adres.</span><span class="sxs-lookup"><span data-stu-id="26da2-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="26da2-124">W **okienku akcji** kliknij przycisk **Edytuj**, a następnie kliknij opcję **Widok nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="26da2-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="26da2-125">Na skróconej karcie **Adres** kliknij przycisk **Inny adres**.</span><span class="sxs-lookup"><span data-stu-id="26da2-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="26da2-126">W formularzu **Wybór adresu** w polu **Typ rekordu** zaznacz **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="26da2-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="26da2-127">Wybierz adres i kliknij **OK**, aby skopiować go do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="26da2-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  


