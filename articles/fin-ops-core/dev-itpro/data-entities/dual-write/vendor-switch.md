---
title: Przełączanie się między projektami dostawcy
description: W tym temacie opisano sposób przełączania integracji danych dostawcy między aplikacjami Finance and Operations i Dataverse.
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
ms.openlocfilehash: d2c22123d5f05945b34eb107c5b912852aec387a
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744472"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="a0b8c-103">Przełączanie się między projektami dostawcy</span><span class="sxs-lookup"><span data-stu-id="a0b8c-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="a0b8c-104">Przepływ danych dostawcy</span><span class="sxs-lookup"><span data-stu-id="a0b8c-104">Vendor data flow</span></span> 

<span data-ttu-id="a0b8c-105">W przypadku wybrania opcji używania tabeli **Konto** do przechowywania dostawców typu **Organizacja** i tabeli **Kontakt** do przechowywania dostawców typu **Osoba**, należy skonfigurować następujące przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-105">If you choose to use the **Account** table to store vendors of the **Organization** type and the **Contact** table to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="a0b8c-106">W przeciwnym razie ta konfiguracja nie jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="a0b8c-107">Użycie rozszerzonego projektu dostawcy dla dostawców typu Organizacji</span><span class="sxs-lookup"><span data-stu-id="a0b8c-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="a0b8c-108">Pakiet rozwiązania **Dynamics365FinanceExtended** zawiera następujące szablony procesów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="a0b8c-109">Zostanie utworzony przepływ pracy dla każdego szablonu.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="a0b8c-110">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="a0b8c-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="a0b8c-111">Tworzenie dostawców w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="a0b8c-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="a0b8c-112">Aktualizowanie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="a0b8c-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="a0b8c-113">Aktualizowanie dostawców w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="a0b8c-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="a0b8c-114">Aby stworzyć nowe procey przepływu pracy przy użyciu szablonów procesu przepływu pracy, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a0b8c-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="a0b8c-115">Utwórz nowy proces przepływu pracy dla tabeli **Dostawcy** i wybierz szablonu procesu przepływu pracy **Tworzenie dostawców w tabeli kont**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-115">Create a workflow process for the **Vendor** table, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="a0b8c-116">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-116">Then select **OK**.</span></span> <span data-ttu-id="a0b8c-117">Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla tabeli **konta**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-117">This workflow handles the vendor creation scenario for the **Account** table.</span></span>

    ![Proces przepływu pracy Tworzenie dostawców w tabeli kont](media/create_process.png)

2. <span data-ttu-id="a0b8c-119">Utwórz nowy proces przepływu pracy dla tabeli **Dostawcy** i wybierz szablonu procesu przepływu pracy **Aktualizowanie dostawców w tabeli kont**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-119">Create a workflow process for the **Vendor** table, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="a0b8c-120">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-120">Then select **OK**.</span></span> <span data-ttu-id="a0b8c-121">Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla tabeli **konta**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-121">This workflow handles the vendor update scenario for the **Account** table.</span></span>
3. <span data-ttu-id="a0b8c-122">Utwórz nowy proces przepływu pracy dla tabeli **Konto** i wybierz szablonu procesu przepływu pracy **Tworzenie dostawców w tabeli dostawców**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-122">Create a workflow process for the **Account** table, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="a0b8c-123">Utwórz nowy proces przepływu pracy dla tabeli **Konto** i wybierz szablonu procesu przepływu pracy **Aktualizowanie dostawców w tabeli dostawców**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-123">Create a workflow process for the **Account** table, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="a0b8c-124">Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="a0b8c-125">Aby skonfigurować przepływ pracy jako przepływ pracy w tle, wybierz opcję **Konwertuj na przepływ pracy w tle**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Przycisk Konwertuj na przepływ pracy w tle](media/background_workflow.png)

6. <span data-ttu-id="a0b8c-127">Umożliwia aktywowanie przepływów pracy utworzonych dla tabel **Konto** i **Dostawca** w celu rozpoczęcia używania tabeli **Konta** do przechowywania informacji o dostawcy dla typu **Organizacja**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** table to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="a0b8c-128">Użycie rozszerzonego projektu dostawcy dla dostawców typu Osoby</span><span class="sxs-lookup"><span data-stu-id="a0b8c-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="a0b8c-129">Pakiet rozwiązania **Dynamics365FinanceExtended** zawiera następujące szablony procesów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="a0b8c-130">Zostanie utworzony przepływ pracy dla każdego szablonu.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="a0b8c-131">Tworzenie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="a0b8c-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="a0b8c-132">Tworzenie dostawców typu Osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="a0b8c-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="a0b8c-133">Aktualizowanie dostawców typu Osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="a0b8c-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="a0b8c-134">Aktualizowanie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="a0b8c-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="a0b8c-135">Aby stworzyć nowe procey przepływu pracy przy użyciu szablonów procesu przepływu pracy, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="a0b8c-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="a0b8c-136">Utwórz nowy proces przepływu pracy dla tabeli **Dostawcy** i wybierz szablonu procesu przepływu pracy **Tworzenie dostawców typu Osoba w tabeli kontaktów**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-136">Create a workflow process for the **Vendor** table, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="a0b8c-137">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-137">Then select **OK**.</span></span> <span data-ttu-id="a0b8c-138">Ten przepływ pracy obsługuje scenariusz tworzenia dostawcy dla tabeli **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-138">This workflow handles the vendor creation scenario for the **Contact** table.</span></span>
2. <span data-ttu-id="a0b8c-139">Utwórz nowy proces przepływu pracy dla tabeli **Dostawcy** i wybierz szablonu procesu przepływu pracy **Aktualizowanie dostawców typu Osoba w tabeli kontaktów**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-139">Create a workflow process for the **Vendor** table, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="a0b8c-140">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-140">Then select **OK**.</span></span> <span data-ttu-id="a0b8c-141">Ten przepływ pracy obsługuje scenariusz aktualizacji dostawcy dla tabeli **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-141">This workflow handles the vendor update scenario for the **Contact** table.</span></span>
3. <span data-ttu-id="a0b8c-142">Utwórz nowy proces przepływu pracy dla tabeli **Kontakt** i wybierz szablonu procesu przepływu pracy **Tworzenie dostawców typu Osoba w tabeli dostawców**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-142">Create a workflow process for the **Contact** table, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="a0b8c-143">Utwórz nowy proces przepływu pracy dla tabeli **Kontakt** i wybierz szablon procesu przepływu pracy **Aktualizowanie dostawców typu Osoba w tabeli dostawców**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-143">Create a workflow process for the **Contact** table, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="a0b8c-144">Przepływy pracy można konfigurować jako przepływy pracy w czasie rzeczywistym lub w tle, zgodnie z wymaganiami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="a0b8c-145">Aby skonfigurować przepływ pracy jako przepływ pracy w tle, wybierz opcję **Konwertuj na przepływ pracy w tle**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="a0b8c-146">Umożliwia aktywowanie przepływów pracy utworzonych dla tabel **Kontakt** i **Dostawca** w celu rozpoczęcia używania tabeli **Kontakt** do przechowywania informacji o dostawcy dla typu **Osoba**.</span><span class="sxs-lookup"><span data-stu-id="a0b8c-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** table to store information for vendors of the **Person** type.</span></span>
