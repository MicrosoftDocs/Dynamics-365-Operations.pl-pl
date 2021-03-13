---
title: Utwórz konto magazynu Azure i Magazyn kluczy
description: W tym temacie opisano sposób tworzenia konta magazynu Azure i magazynu kluczy.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: d076aa5230437d1ef90f6b46d49ee4dea526db24
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104236"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a><span data-ttu-id="a90d5-103">Utwórz konto magazynu Azure i Magazyn kluczy</span><span class="sxs-lookup"><span data-stu-id="a90d5-103">Create an Azure storage account and a key vault</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="a90d5-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="a90d5-104">Prerequisites</span></span>

<span data-ttu-id="a90d5-105">Zanim będzie można wykonać czynności opisane w tym temacie, należy upewnić się, że wykonano następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="a90d5-105">Before you can complete the steps in this topic, you must make sure that the following tasks have been completed:</span></span>

- <span data-ttu-id="a90d5-106">Tworzenie zasobu magazynu kluczy w Azure.</span><span class="sxs-lookup"><span data-stu-id="a90d5-106">Create a key vault resource in Azure.</span></span> <span data-ttu-id="a90d5-107">Aby uzyskać więcej informacji o tej funkcji, zobacz: [Informacje o usłudze Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span><span class="sxs-lookup"><span data-stu-id="a90d5-107">For more information, see [About Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span></span>
- <span data-ttu-id="a90d5-108">Utwórz konto magazynu Azure (magazyn obiektów BLOB).</span><span class="sxs-lookup"><span data-stu-id="a90d5-108">Create an Azure storage account (Blob storage).</span></span> <span data-ttu-id="a90d5-109">Aby uzyskać więcej informacji, przejrzyj temat [Obsługa konta magazynu Azure](https://docs.microsoft.com/azure/storage/blobs/).</span><span class="sxs-lookup"><span data-stu-id="a90d5-109">For more information, see [Maintaining Azure Storage Account](https://docs.microsoft.com/azure/storage/blobs/).</span></span>

## <a name="overview"></a><span data-ttu-id="a90d5-110">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a90d5-110">Overview</span></span>

<span data-ttu-id="a90d5-111">W tym temacie przedstawiono dwa główne kroki:</span><span class="sxs-lookup"><span data-stu-id="a90d5-111">In this topic, you will complete two main steps:</span></span>

- <span data-ttu-id="a90d5-112">Skonfiguruj konto magazynu Azure, aby uzyskać identyfikator URI konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="a90d5-112">Set up the Azure storage account to get the storage account URI.</span></span>
- <span data-ttu-id="a90d5-113">Skonfiguruj Magazyn kluczy do przechowywania identyfikatora URI konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="a90d5-113">Set up the key vault to store the storage account URI.</span></span>

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a><span data-ttu-id="a90d5-114">Skonfiguruj konto magazynu Azure, aby uzyskać identyfikator URI konta magazynu</span><span class="sxs-lookup"><span data-stu-id="a90d5-114">Set up the Azure storage account to get the storage account URI</span></span>

1. <span data-ttu-id="a90d5-115">Umożliwia otwarcie konta magazynu, które ma być używane z dodatkiem Faktury elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="a90d5-115">Open the storage account that you plan to use with the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="a90d5-116">Przejdź do **Usługa Blob** \> **Kontenery** i utwórz nowy kontener.</span><span class="sxs-lookup"><span data-stu-id="a90d5-116">Go to **Blob service** \> **Containers**, and create a new container.</span></span>
3. <span data-ttu-id="a90d5-117">Wprowadź nazwę kontenera i ustaw dla pola **Poziom dostępu publicznego** wartość **Prywatne (brak dostępu anonimowego)**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-117">Enter a name for the container, and set the **Public access level** field to **Private (no anonymous access)**.</span></span>
4. <span data-ttu-id="a90d5-118">Otwórz kontener i przejdź do **Ustawienia \> Polityka dostępu**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-118">Open the container, and go to **Settings \> Access policy**.</span></span>
5. <span data-ttu-id="a90d5-119">Wybierz opcję **Dodaj zasady**, aby dodać zapisane zasady dostępu.</span><span class="sxs-lookup"><span data-stu-id="a90d5-119">Select **Add policy** to add a stored access policy.</span></span>
6. <span data-ttu-id="a90d5-120">Odpowiednio określ **Identyfikator** i pola **Uprawnień**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-120">Set the **Identifier** and **Permissions** fields as appropriate.</span></span> <span data-ttu-id="a90d5-121">W polu **uprawnienia** zaznacz opcję wszystkie uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="a90d5-121">In the **Permissions** field, you should select all permissions.</span></span>

    ![Przyznawanie uprawnień do magazynu obiektów Blob](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. <span data-ttu-id="a90d5-123">Wprowadź daty rozpoczęcia i ważności.</span><span class="sxs-lookup"><span data-stu-id="a90d5-123">Enter the start and expiry dates.</span></span> <span data-ttu-id="a90d5-124">Data ważności powinna być w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="a90d5-124">The expiry date should be in future.</span></span>
8. <span data-ttu-id="a90d5-125">Wybierz przycisk **OK**, aby zapisać zasady, a następnie zapisz zmiany w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="a90d5-125">Select **OK** to save the policy, and then save your changes to the container.</span></span>
9. <span data-ttu-id="a90d5-126">Wróć do konta magazynu i otwórz **Eksplorator magazynu (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-126">Return to the storage account, and open **Storage Explorer (preview)**.</span></span>
10. <span data-ttu-id="a90d5-127">Kliknij prawym przyciskiem myszy kontener, a następnie wybierz polecenie **Pobierz podpis dostępu współdzielonego**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-127">Right-click the container, and then select **Get Shared Access Signature**.</span></span>
11. <span data-ttu-id="a90d5-128">W oknie dialogowym **Podpis dostępu współdzielonego** skopiuj i zapisz wartość w polu **Identyfikator URI**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-128">In the **Shared Access Signature** dialog box, copy and store the value in the **URI** field.</span></span> <span data-ttu-id="a90d5-129">Ta wartość będzie używana w następnej procedurze i jest określana jako *Identyfikator URI podpisu dostępu współdzielonego*.</span><span class="sxs-lookup"><span data-stu-id="a90d5-129">This value will be used in the next procedure and will be referred to as the *shared access signature URI*.</span></span>

    ![Wybieranie i kopiowanie wartości identyfikatora URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a><span data-ttu-id="a90d5-131">Skonfiguruj Magazyn kluczy do przechowywania identyfikatora URI konta magazynu</span><span class="sxs-lookup"><span data-stu-id="a90d5-131">Set up the key vault to store the storage account URI</span></span>

1. <span data-ttu-id="a90d5-132">Otwórz magazyn kluczy, którego zamierzasz używać z dodatkiem Faktury elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="a90d5-132">Open the key vault that you intend to use with the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="a90d5-133">Przejdź do **Ustawienia** \> **Wpis tajny**, a następnie wybierz opcję **Generuj/Importuj**, aby utworzyć nowy wpis tajny.</span><span class="sxs-lookup"><span data-stu-id="a90d5-133">Go to **Settings** \> **Secrets**, and then select **Generate/Import** to create a new secret.</span></span>
3. <span data-ttu-id="a90d5-134">Na stronie **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-134">On the **Create a secret** page, in the **Upload options** field, select **Manual**.</span></span>
4. <span data-ttu-id="a90d5-135">Pozwala wprowadzić nazwę wpisu tajnego.</span><span class="sxs-lookup"><span data-stu-id="a90d5-135">Enter the name of the secret.</span></span> <span data-ttu-id="a90d5-136">Ta nazwa będzie używana podczas instalacji usługi w usłudze Regulatory Configuration Service (RCS) i będzie nazywana *nazwą klucza tajnego magazynu kluczy*.</span><span class="sxs-lookup"><span data-stu-id="a90d5-136">This name will be used during setup of the service in Regulatory Configuration Service (RCS) and will be referred to as the *key vault secret name*.</span></span>
5. <span data-ttu-id="a90d5-137">W polu **Wartość** wybierz opcję **Identyfikator URI podpisu dostępu udostępnionego**, a następnie wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-137">In the **Value** field, select **Shared Access Signature URI**, and then select **Create**.</span></span>
6. <span data-ttu-id="a90d5-138">Skonfiguruj zasady dostępu, aby nadać dodatkowi Faktury elektroniczne odpowiedni poziom bezpiecznego dostępu do utworzonego klucza tajnego.</span><span class="sxs-lookup"><span data-stu-id="a90d5-138">Set up the access policy to grant the Electronic invoicing add-on the correct level of secure access to the secret you created.</span></span> <span data-ttu-id="a90d5-139">Przejdź do **Ustawienia \> Zasad dostępu** i wybierz pozycję **Dodaj zasady dostępu**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-139">Go to **Settings \> Access policy**, and select **Add Access Policy**.</span></span>
7. <span data-ttu-id="a90d5-140">Umożliwia ustawienie tajnych uprawnień dla operacji **Rozpocznij** i **Lista**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-140">Set the secret permissions for the **Get** and **List** operations.</span></span>

    ![Udzielanie dostępu do usługi](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. <span data-ttu-id="a90d5-142">Umożliwia ustawienie certyfikatu uprawnień dla operacji **Rozpocznij** i **Lista**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-142">Set the certificate permissions for **Get** and **List** operations.</span></span>

    ![Nadanie certyfikatu uprawnień](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. <span data-ttu-id="a90d5-144">W oknie dialogowym **Główne** wybierz podmiot zabezpieczeń, dodając **Dodatek Faktury elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-144">In the **Principal** dialog box, select the principal by adding **Electronic invoicing add-on**.</span></span>
10. <span data-ttu-id="a90d5-145">Wybierz opcję **Dodaj**, a następnie wybierz opcję **Zapisz zmiany magazynu kluczy**.</span><span class="sxs-lookup"><span data-stu-id="a90d5-145">Select **Add**, and then select **Save Key Vault changes**.</span></span>
11. <span data-ttu-id="a90d5-146">Na stronie **Przegląd** skopiuj wartość **Nazwa DNS** dla magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="a90d5-146">On the **Overview** page, copy the **DNS name** value for the key vault.</span></span> <span data-ttu-id="a90d5-147">Ta wartość będzie używana podczas instalacji usługi w RCS i będzie określana jako *Identyfikator URI magazynu kluczy*.</span><span class="sxs-lookup"><span data-stu-id="a90d5-147">This value will be used during setup of the service in RCS and will be referred as the *key vault URI*.</span></span>
