---
title: Przełączanie się między projektami dostawcy
description: W tym temacie opisano sposób przełączania integracji danych dostawcy między aplikacjami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 0ecc401706911f8b92146b95bb6415185df8b451
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997559"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="5ec87-103">Przełączanie się między projektami dostawcy</span><span class="sxs-lookup"><span data-stu-id="5ec87-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="5ec87-104">Przepływ danych dostawcy</span><span class="sxs-lookup"><span data-stu-id="5ec87-104">Vendor data flow</span></span> 

<span data-ttu-id="5ec87-105">W przypadku wybrania opcji używania jednostki **Konto** do przechowywania dostawców typu **Organizacja** i jednostki **Kontakt** do przechowywania dostawców typu **Osoba** , należy skonfigurować następujące przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="5ec87-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="5ec87-106">W przeciwnym razie ta konfiguracja nie jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="5ec87-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="5ec87-107">Użycie rozszerzonego projektu dostawcy dla dostawców typu Organizacji</span><span class="sxs-lookup"><span data-stu-id="5ec87-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="5ec87-108">Pakiet rozwiązania **Dynamics365FinanceExtended** zawiera następujące szablony procesów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5ec87-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="5ec87-109">Zostanie utworzony przepływ pracy dla każdego szablonu.</span><span class="sxs-lookup"><span data-stu-id="5ec87-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="5ec87-110">Utwórz dostawców w jednostce kont</span><span class="sxs-lookup"><span data-stu-id="5ec87-110">Create Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="5ec87-111">Utwórz Dostawców w Jednostce dostawców</span><span class="sxs-lookup"><span data-stu-id="5ec87-111">Create Vendors in Vendors Entity</span></span>
+ <span data-ttu-id="5ec87-112">Aktualizuj dostawców w jednostce kont</span><span class="sxs-lookup"><span data-stu-id="5ec87-112">Update Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="5ec87-113">Aktualizuj Dostawców w Jednostce dostawców</span><span class="sxs-lookup"><span data-stu-id="5ec87-113">Update Vendors in Vendors Entity</span></span>

<span data-ttu-id="5ec87-114">Aby stworzyć nowe procey przepływu pracy przy użyciu szablonów procesu przepływu pracy, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="5ec87-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="5ec87-115">Utwórz nowy proces przepływu pracy dla jednostki **Dostawcy** i wybierz szablonu procesu przepływu pracy jednostki **Utwórz dostawców w jednostce kont**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="5ec87-116">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-116">Then select **OK**.</span></span> <span data-ttu-id="5ec87-117">Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla jednostki **konta**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Proces przepływu pracy Utwórz dostawców w jednostce kont](media/create_process.png)

2. <span data-ttu-id="5ec87-119">Utwórz nowy proces przepływu pracy dla jednostki **Dostawcy** i wybierz szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców w jednostce kont**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="5ec87-120">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-120">Then select **OK**.</span></span> <span data-ttu-id="5ec87-121">Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla jednostki **konta**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="5ec87-122">Utwórz nowy proces przepływu pracy dla jednostki **Konto** i wybierz szablonu procesu przepływu pracy jednostki **Utwórz dostawców w jednostce Dostawców**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Entity** workflow process template.</span></span>
4. <span data-ttu-id="5ec87-123">Utwórz nowy proces przepływu pracy dla jednostki **Konto** i wybierz szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców w jednostce Dostawców**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Entity** workflow process template.</span></span>
5. <span data-ttu-id="5ec87-124">Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5ec87-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="5ec87-125">Aby skonfigurować przepływ pracy jako przepływ pracy w tle, wybierz opcję **Konwertuj na przepływ pracy w tle**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Przycisk Konwertuj na przepływ pracy w tle](media/background_workflow.png)

6. <span data-ttu-id="5ec87-127">Umożliwia aktywowanie przepływów pracy utworzonych dla jednostek **Konto**  i **Dostawca** w celu rozpoczęcia używania jednostki **Konta** do przechowywania informacji o dostawcy dla typu **Organizacji**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-127">Activate the workflows that you created for the **Account** and **Vendor** entities to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="5ec87-128">Użycie rozszerzonego projektu dostawcy dla dostawców typu Osoby</span><span class="sxs-lookup"><span data-stu-id="5ec87-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="5ec87-129">Pakiet rozwiązania **Dynamics365FinanceExtended** zawiera następujące szablony procesów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5ec87-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="5ec87-130">Zostanie utworzony przepływ pracy dla każdego szablonu.</span><span class="sxs-lookup"><span data-stu-id="5ec87-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="5ec87-131">Tworzenie dostawców typu Osoba w jednostce dostawcy</span><span class="sxs-lookup"><span data-stu-id="5ec87-131">Create Vendors of type Person in Vendors Entity</span></span>
+ <span data-ttu-id="5ec87-132">Tworzenie dostawców typu Osoba w jednostce kontaktów</span><span class="sxs-lookup"><span data-stu-id="5ec87-132">Create Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="5ec87-133">Aktualizacja dostawców typu Osoba w jednostce kontaktów</span><span class="sxs-lookup"><span data-stu-id="5ec87-133">Update Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="5ec87-134">Aktualizacja dostawców typu Osoba w jednostce dostawcy</span><span class="sxs-lookup"><span data-stu-id="5ec87-134">Update Vendors of type Person in Vendors Entity</span></span>

<span data-ttu-id="5ec87-135">Aby stworzyć nowe procey przepływu pracy przy użyciu szablonów procesu przepływu pracy, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="5ec87-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="5ec87-136">Utwórz nowy proces przepływu pracy dla jednostki **Dostawcy** i wybierz szablonu procesu przepływu pracy jednostki **Tworzenie dostawców typu Osoba w jednostce kontaktów**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="5ec87-137">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-137">Then select **OK**.</span></span> <span data-ttu-id="5ec87-138">Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla jednostki **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="5ec87-139">Utwórz nowy proces przepływu pracy dla jednostki **Dostawcy** i wybierz szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców typu Osoba w jednostce kontaktów**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="5ec87-140">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-140">Then select **OK**.</span></span> <span data-ttu-id="5ec87-141">Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla jednostki **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="5ec87-142">Utwórz nowy proces przepływu pracy dla jednostki **Kontakt** i wybierz szablonu procesu przepływu pracy jednostki **Tworzenie dostawców typu Osoba w jednostce dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Entity** template.</span></span>
4. <span data-ttu-id="5ec87-143">Utwórz nowy proces przepływu pracy dla jednostki **Kontakt** i wybierz szablonu procesu przepływu pracy jednostki **Aktualizuj dostawców typu Osoba w jednostce dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Entity** template.</span></span>
5. <span data-ttu-id="5ec87-144">Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5ec87-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="5ec87-145">Aby skonfigurować przepływ pracy jako przepływ pracy w tle, wybierz opcję **Konwertuj na przepływ pracy w tle**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="5ec87-146">Umożliwia aktywowanie przepływów pracy utworzonych dla jednostek **Kontakt**  i **Dostawca** w celu rozpoczęcia używania jednostki **Kontakt** do przechowywania informacji o dostawcy dla typu **Osoby**.</span><span class="sxs-lookup"><span data-stu-id="5ec87-146">Activate the workflows that you created on the **Contact** and **Vendor** entities to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
