---
title: Dodawanie lokalizacji i typów relacji stron
description: W tym temacie opisano, jak dodać nową lokalizację i typ relacji stron.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 00810576d36339bf7ce0657b1577e1e322c36bf0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979096"
---
# <a name="add-location-and-party-relationship-types"></a><span data-ttu-id="11aed-103">Dodawanie lokalizacji i typów relacji stron</span><span class="sxs-lookup"><span data-stu-id="11aed-103">Add location and party relationship types</span></span> 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a><span data-ttu-id="11aed-104">Dodawanie ról lokalizacji</span><span class="sxs-lookup"><span data-stu-id="11aed-104">Add location roles</span></span>

<span data-ttu-id="11aed-105">Istnieją dwa sposoby dodawania nowych ról lokalizacji dla adresu i informacji kontaktowych:</span><span class="sxs-lookup"><span data-stu-id="11aed-105">There are two ways to add a new location roles for address and contact information:</span></span>

-  <span data-ttu-id="11aed-106">Dodanie za pośrednictwem strony **Cel informacji o adresie i osobie kontaktowej**.</span><span class="sxs-lookup"><span data-stu-id="11aed-106">Add it through the **Address and contact information purpose** page.</span></span> <span data-ttu-id="11aed-107">Nowa rola zostanie zapisana w tabeli **LogisticsLocationRole** z parametrem type = 0, co oznacza, że rola nie jest rolą systemową zdefiniowaną w wyliczeniu **LogisticsLocationRoleType** i jego rozszerzeniach.</span><span class="sxs-lookup"><span data-stu-id="11aed-107">The new role will be saved to the **LogisticsLocationRole** table with type = 0, which indicates that the role is not a system role defined in the **LogisticsLocationRoleType** enum and its extensions.</span></span> <span data-ttu-id="11aed-108">Użytkownik będzie mógł używać tej roli podczas tworzenia informacji adresowych lub kontaktowych.</span><span class="sxs-lookup"><span data-stu-id="11aed-108">A user will be able to use this role when creating address or contact information.</span></span>

    ![Przeznaczenie informacji o adresie i zawartości](media/Address-Contact.PNG)

-  <span data-ttu-id="11aed-110">Dodanie do rozszerzenia elementu stałotekstowego **LogisticsLocationRoleType**, a następnie rozpowszechnienie za pomocą procesu synchronizacji bazy danych.</span><span class="sxs-lookup"><span data-stu-id="11aed-110">Add it to the **LogisticsLocationRoleType** enum extension, and let it populate through the database sync process.</span></span>

    1.  <span data-ttu-id="11aed-111">Utwórz rozszerzenie do elementu stałotekstowego **LogisticsLocationRoleType** i dodaj nową rolę w rozszerzeniu.</span><span class="sxs-lookup"><span data-stu-id="11aed-111">Create an extension to the **LogisticsLocationRoleType** enum and add the new role in the extension.</span></span> 
  
        ![Rozszerzenie na wyliczenie LogisticsLocationRoleType](media/Logistics.PNG)

    2. <span data-ttu-id="11aed-113">Utwórz nowy plik zasobów dla nowej roli, a następnie przypisz wartość do jego właściwości.</span><span class="sxs-lookup"><span data-stu-id="11aed-113">Create a new resource file for the new role, and then assign a value for its properties.</span></span>
     
     ![Nowy plik zasobów](media/Resource.PNG)
        
    3.  <span data-ttu-id="11aed-115">Utwórz klasę wypełniania danymi i określ metodę programu obsługi w celu wypełnienia nowej roli.</span><span class="sxs-lookup"><span data-stu-id="11aed-115">Create a data population class and provide a handler method to populate the new role.</span></span> 

        ![Wypełnianie danymi](media/Dirdata.PNG)

    4.  <span data-ttu-id="11aed-117">Aby przeprowadzić test wypełniania nowej roli lokalizacji, można utworzyć klasę wykonywalną i wywołać DirDataPopulation::insertLogisticsLocationRoles() w Main().</span><span class="sxs-lookup"><span data-stu-id="11aed-117">To test populating the new location role, you can create a runnable class, and call DirDataPopulation::insertLogisticsLocationRoles() in Main().</span></span> <span data-ttu-id="11aed-118">Po zakończeniu tego procesu nowa rola powinna być widoczna w tabeli **LogisticsLocationRole** z typem \> 0.</span><span class="sxs-lookup"><span data-stu-id="11aed-118">After this process is complete, you should see the new role populated in the **LogisticsLocationRole** table with type \> 0.</span></span> <span data-ttu-id="11aed-119">Nowa rola będzie wyświetlana na stronie **Cel informacji o adresie i osobie kontaktowej**.</span><span class="sxs-lookup"><span data-stu-id="11aed-119">The new role will display on the **Address and contact information purpose** page.</span></span>

        ![Wstawianie nowej lokalizacji](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a><span data-ttu-id="11aed-121">Dodawanie typów relacji stron</span><span class="sxs-lookup"><span data-stu-id="11aed-121">Add party relationship types</span></span> 

<span data-ttu-id="11aed-122">Istnieją dwa sposoby dodawania nowego typu relacji:</span><span class="sxs-lookup"><span data-stu-id="11aed-122">There are two ways to add a new relationship type:</span></span>

-   <span data-ttu-id="11aed-123">Dodanie za pośrednictwem strony **Typy relacji**.</span><span class="sxs-lookup"><span data-stu-id="11aed-123">Add it through the **Relationship types** page.</span></span> <span data-ttu-id="11aed-124">Nowa relacja zostanie zapisana w tabeli **DirRelationshipTypeTable** z parametem systemtype = 0.</span><span class="sxs-lookup"><span data-stu-id="11aed-124">The new relationship will be saved to **DirRelationshipTypeTable** with systemtype = 0.</span></span>

    ![Typy relacji](media/Relationship.PNG)

-  <span data-ttu-id="11aed-126">Dodanie do rozszerzenia elementu stałotekstowego **DirSystemRelationshipType**, a następnie rozpowszechnienie za pomocą procesu synchronizacji bazy danych.</span><span class="sxs-lookup"><span data-stu-id="11aed-126">Add it to the extension of the **DirSystemRelationshipType** enum, and let it populate through database sync process.</span></span>

    1.  <span data-ttu-id="11aed-127">Utwórz rozszerzenie w elemencie stałotekstowym **DirSystemRelationshipType** i dodaj nowy typ relacji.</span><span class="sxs-lookup"><span data-stu-id="11aed-127">Create an extension to the **DirSystemRelationshipType** enum and add the new relationship type.</span></span>

    2. <span data-ttu-id="11aed-128">Utwórz inicjatora dla tego nowego typu.</span><span class="sxs-lookup"><span data-stu-id="11aed-128">Create an initializer for this new type.</span></span> <span data-ttu-id="11aed-129">Kilka przykładów można znaleźć w kodzie podstawowym. Jeden z nich to  **DirRelationshipTypeChildInitialize**.</span><span class="sxs-lookup"><span data-stu-id="11aed-129">You can find several examples in the core code, one of them is  **DirRelationshipTypeChildInitialize**.</span></span> <span data-ttu-id="11aed-130">Jest to klasa inicjatora dla typu relacji strony „Obiekt podrzędny”.</span><span class="sxs-lookup"><span data-stu-id="11aed-130">This is an initializer class for party relationship type “Child”.</span></span> <span data-ttu-id="11aed-131">Można zacząć od inicjatora poprzez skopiowanie i wklejenie tego kodu, a następnie zaktualizowanie wyróżnionych obszarów.</span><span class="sxs-lookup"><span data-stu-id="11aed-131">You can start with your initializer by copying and pasting this code and then update the highlighted areas.</span></span>
    
    ![Inicjator DirRelationshipChild](media/DirRelationship.PNG)

    3.  <span data-ttu-id="11aed-133">Aby przeprowadzić test wypełniania nowego typu relacji, można utworzyć klasę wykonywalną i wywołać DirDataPopulation::insertDirRelationshipTypes() w Main().</span><span class="sxs-lookup"><span data-stu-id="11aed-133">To test populating the new relationship type, you can create a runnable class, and call DirDataPopulation::insertDirRelationshipTypes() in Main().</span></span> <span data-ttu-id="11aed-134">Powinien zostać wyświetlony nowy typ relacji w **DirRelationshipTypeTable**. Będzie on widoczny na stronie **Typy relacji**.</span><span class="sxs-lookup"><span data-stu-id="11aed-134">You should see the new relationship type in the **DirRelationshipTypeTable**, and the new relationship type will be available on the **Relationship types** page.</span></span>

        ![Klasa możliwa do uruchomienia](media/Runnable.PNG)
