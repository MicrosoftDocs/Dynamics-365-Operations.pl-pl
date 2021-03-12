---
title: Tworzenie umów o świadczenie usług
description: W tym temacie opisano sposób korzystania z funkcji w modułach Zarządzanie serwisem oraz Zarządzanie projektami i ich księgowanie do tworzenia umów serwisowych.
author: ShylaThompson
manager: tfehr
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef5ca8cc9c80581b9f7ef69bd8c4403d3d0296e8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965980"
---
# <a name="create-service-agreements"></a><span data-ttu-id="56f7d-103">Tworzenie umów o świadczenie usług</span><span class="sxs-lookup"><span data-stu-id="56f7d-103">Create service agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56f7d-104">W tym temacie opisano sposób korzystania z funkcji w modułach Zarządzanie serwisem oraz Zarządzanie projektami i ich księgowanie do tworzenia umów serwisowych.</span><span class="sxs-lookup"><span data-stu-id="56f7d-104">This topic describes how to use features in the Service management and the Project management and accounting modules to create service agreements.</span></span>

## <a name="create-a-service-agreement-from-service-management"></a><span data-ttu-id="56f7d-105">Tworzenie umowy serwisowej z Zarządzania serwisem</span><span class="sxs-lookup"><span data-stu-id="56f7d-105">Create a service agreement from Service management</span></span>

1. <span data-ttu-id="56f7d-106">Przejdź do modułu **Zarządzanie serwisem**.</span><span class="sxs-lookup"><span data-stu-id="56f7d-106">Navigate to **Service management**.</span></span>
2. <span data-ttu-id="56f7d-107">Kliknij opcję **Umowy serwisowe**, aby utworzyć nowy wiersz umowy serwisowej w nagłówku strony.</span><span class="sxs-lookup"><span data-stu-id="56f7d-107">Click **Service agreements** to create a new service agreement line in the page header.</span></span> 
3. <span data-ttu-id="56f7d-108">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="56f7d-108">Click **New**.</span></span> <span data-ttu-id="56f7d-109">Wprowadź opis, wybierz odwołanie do projektu w polu **Identyfikator projektu** i uzupełnij pozostałe wiersze i pola dla umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="56f7d-109">Enter a description, select a reference to a project in the **Project ID** field, and fill in the rest of the fields and lines for the service agreement.</span></span> <span data-ttu-id="56f7d-110">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="56f7d-110">Click **Save**.</span></span>
4. <span data-ttu-id="56f7d-111">Na karcie **Relacje** wybierz opcję **Przedmioty serwisu** lub **Zadania serwisowe**, aby utworzyć relacje przedmiotów serwisu lub relacje zadań serwisowych dla umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="56f7d-111">On the **Relations** tab, select **Service objects** or **Service tasks** to create service object relations or service task relations for the service agreement.</span></span> <span data-ttu-id="56f7d-112">Przedmioty serwisu i zadania serwisowe, dla których zostały utworzone relacje, można dołączać do wierszy umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="56f7d-112">The service objects and tasks that you have created relations for can be attached on the lines of the service agreement.</span></span>
5. <span data-ttu-id="56f7d-113">W dolnej połowie strony utwórz wiersze umowy serwisowej, kopiując je z szablonu serwisu lub innej umowy serwisowej albo tworząc je ręcznie.</span><span class="sxs-lookup"><span data-stu-id="56f7d-113">In the lower half of the page, create service agreement lines by copying lines from a service template, another service agreement, or manually creating the service-agreement lines.</span></span>

> [!NOTE]
> <span data-ttu-id="56f7d-114">W przypadku kopiowania wierszy do umowy serwisowej z innej umowy można wskazać, czy mają być również kopiowane relacje przedmiotów serwisu i relacje zadań serwisowych.</span><span class="sxs-lookup"><span data-stu-id="56f7d-114">If you copy lines into the service agreement from another service agreement, you can indicate whether you also want to copy service object and service task relations.</span></span> <span data-ttu-id="56f7d-115">W przypadku skopiowania tych relacji są one dodawane do ewentualnych relacji istniejących w umowie serwisowej.</span><span class="sxs-lookup"><span data-stu-id="56f7d-115">If you copy these relations, they are added to any existing relations on the service agreement.</span></span> <span data-ttu-id="56f7d-116">W przypadku kopiowania wierszy umowy serwisowej z szablonu serwisu relacje przedmiotów serwisu i relacje zadań serwisowych są automatycznie kopiowane jako relacje w nowych wierszach umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="56f7d-116">If you copy service-agreement lines from a service template, the service-object and service-task relations are automatically copied as service-object relations and service-task relations on the new service-agreement lines.</span></span>

## <a name="create-service-agreement-lines-manually"></a><span data-ttu-id="56f7d-117">Ręczne tworzenie wierszy umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="56f7d-117">Create service agreement lines manually</span></span>

1. <span data-ttu-id="56f7d-118">Na stronie **Umowy serwisowe** dodaj wiersz umowy serwisowej w siatce wierszy.</span><span class="sxs-lookup"><span data-stu-id="56f7d-118">From the **Service agreements** page, add a service agreement line in the lines grid.</span></span> 
2. <span data-ttu-id="56f7d-119">Wprowadź odpowiednie informacje w wierszu umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="56f7d-119">Enter the appropriate information for the service agreement line.</span></span> 
3. <span data-ttu-id="56f7d-120">Naciśnij klawisze **CTRL+S**, aby zapisać wiersz, a następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="56f7d-120">Press **CTRL+S** to save the line, and then close the page.</span></span>

## <a name="create-a-service-agreement-from-project"></a><span data-ttu-id="56f7d-121">Tworzenie umowy serwisowej z modułu Projekt</span><span class="sxs-lookup"><span data-stu-id="56f7d-121">Create a service agreement from Project</span></span>

1. <span data-ttu-id="56f7d-122">Kliknij opcję **Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="56f7d-122">Click **Project management and accounting**.</span></span>
2. <span data-ttu-id="56f7d-123">Kliknij opcję **Wszystkie projekty**.</span><span class="sxs-lookup"><span data-stu-id="56f7d-123">Click **All projects**.</span></span>
3. <span data-ttu-id="56f7d-124">Wybierz projekt z listy.</span><span class="sxs-lookup"><span data-stu-id="56f7d-124">Select the project from the list.</span></span>
4. <span data-ttu-id="56f7d-125">W **okienku akcji** kliknij pozycję **Zarządzaj**.</span><span class="sxs-lookup"><span data-stu-id="56f7d-125">On the **Action Pane**, click **Manage**.</span></span> <span data-ttu-id="56f7d-126">W grupie akcji **Nowy** kliknij opcję **Serwis**, a następnie opcję **Umowa serwisowa**.</span><span class="sxs-lookup"><span data-stu-id="56f7d-126">In the **New** Action group, click **Service** and select **Service agreement**.</span></span>
5. <span data-ttu-id="56f7d-127">Wykonaj kroki opisane w sekcji zatytułowanej **Tworzenie umowy serwisowej** wcześniej w tym temacie, aby wprowadzić odwołanie do projektu.</span><span class="sxs-lookup"><span data-stu-id="56f7d-127">Follow the steps in the section titled **Create a service agreement** as described earlier in this topic to enter the project reference.</span></span>


## <a name="related-topics"></a><span data-ttu-id="56f7d-128">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="56f7d-128">Related topics</span></span>

[<span data-ttu-id="56f7d-129">Omówienie opracowania i ustanawiania przeglądów umów serwisowych</span><span class="sxs-lookup"><span data-stu-id="56f7d-129">Develop and establish service agreements overview</span></span>](service-agreements.md)


