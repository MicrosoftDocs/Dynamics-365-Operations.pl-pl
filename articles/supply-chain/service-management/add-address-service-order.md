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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41497eacae8bcc0e57df8062f7f318a39c2b4909
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435406"
---
# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="6e3e1-103">Dodawanie adresu do zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="6e3e1-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6e3e1-104">W tym temacie opisano sposób dodawania adresu odbiorcy do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="6e3e1-105">Podczas tworzenia zlecenia serwisowego informacje adresowe są przenoszone z projektu, do którego jest dołączone zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="6e3e1-106">Jednak można wybrać alternatywną lokalizację z adresów, które zostały już wprowadzone w Microsoft Dynamics AX dla odbiorców, dostawców, oddziałów, magazynów, zleceń serwisowych i projektów.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="6e3e1-107">Można również utworzyć nowy adres.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-107">You can also create a new address.</span></span> <span data-ttu-id="6e3e1-108">Domyślnie nowy adres zostanie przeniesiony do projektu.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="6e3e1-109">Można jednak określić, że nowy adres jest odpowiedni tylko dla tego wystąpienia usługi.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="6e3e1-110">W takim przypadku nowy adres nie zostanie przeniesiony do projektu.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="6e3e1-111">Tworzenie adresu odbiorcy dla zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="6e3e1-111">Create a customer address for a service order</span></span>

<span data-ttu-id="6e3e1-112">Aby dodać adres do zlecenia serwisowego, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6e3e1-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="6e3e1-113">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="6e3e1-114">Otwórz zlecenie serwisowe, dla którego chcesz utworzyć adres.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="6e3e1-115">W **okienku akcji** kliknij przycisk **Edytuj**, a następnie kliknij opcję **Widok nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="6e3e1-116">Na skróconej karcie **Adres** kliknij przycisk **Dodaj adres**.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="6e3e1-117">W formularzu **Nowy adres** wprowadź niepowtarzalną nazwę dla adresu i wypełnij pozostałe pola.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="6e3e1-118">Jeśli wprowadzisz taką samą nazwę jak istniejący adres, informacje wprowadzone w pozostałych polach zastąpią informacje istniejącego adresu.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="6e3e1-119">Kliknij **OK**, aby skopiować nowy adres do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="6e3e1-120">Określanie adresu alternatywnego dotyczącego zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="6e3e1-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="6e3e1-121">Aby dodać inny adres do zlecenia serwisowego, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6e3e1-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="6e3e1-122">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="6e3e1-123">Otwórz zlecenie serwisowe, dla którego chcesz wprowadzić inny adres.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="6e3e1-124">W **okienku akcji** kliknij przycisk **Edytuj**, a następnie kliknij opcję **Widok nagłówka**.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="6e3e1-125">Na skróconej karcie **Adres** kliknij przycisk **Inny adres**.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="6e3e1-126">W formularzu **Wybór adresu** w polu **Typ rekordu** zaznacz **Zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="6e3e1-127">Wybierz adres i kliknij **OK**, aby skopiować go do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="6e3e1-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  


